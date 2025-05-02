---
{"dg-publish":true,"permalink":"/content/digital-garden-content/artificial-intelligence-content/planning/","updated":"2025-04-08T20:28:57.000+05:30"}
---

#DigitalGarden 

## What is planning?

>[!important]
>Planning regards the process of computing multiple steps in a process before executing the task such that it's planned out. These steps in a plan take into regard a sequence of actions to achieve a given goal

Some of the main issues in carrying out a "standard search" to solve an issue is that its very time consuming and tends to propose a lot of problem/issues before reaching the goal. Besides that, finding a good heuristic function can be difficult.

Take the following illustration as an example:
![Pasted image 20250315163002.png](/img/user/pngs/Pasted%20image%2020250315163002.png)

You can derive the following for the image:

- Too many options to consider if using a standard search
- Finding a heuristic function to find the most optimal path could take a lot of time 
- Multiple branches to consider

The main difference between planning and problem solving is that a planning agent is capable of representing goals, states and actions while using explicit logical representations. Hence, this makes planning more powerful given its ability to utilize representation and methods.

![Pasted image 20250315163505.png](/img/user/pngs/Pasted%20image%2020250315163505.png)

Now when it comes to defining your planning system your going to need a:

- Domain Description - Basically defines the context of the issue
- Action Description - Defines the actions that may be taken to reach the goal (e.g. In an informed search algorithm there may be a heuristic)
- Goal Description - Defines what the goal is and should be

There are two approaches to take if you want to plan a algorithm:

- Classical Planning approach where:
	- Environment is fully observable
	- Deterministic (outcome of any move is predictable, e.g. game of chess)
	- Static (while agent is not moving task environment does not change around them hence it does not affect the overall outcome of the agent)
	- Can be represented through STRIPS
- Non-classical Planning:
	- Partially Observable
	- Stochastic (Environment has an unpredictable number of moves hence making the agents move in a task environment unpredictable e.g. rolling a dice, in other words the outcome is unpredictable and cannot be proven with certainty)
	- Can be represented through MDP (Markov Decision Process Planning), POMDP (Partially Observable Markov Decision Process Planning)

## STRIPS

>[!Definition]
>The Standford Research Institute Problem Solver is an automated planning technique that uses a classical approach which enables users to create a plan to move an agent from one state to another in an algorithm. **STRIPS defines problems as a state space search where an agent transitions between different states using a set of predefined actions**.

In other words, STRIPS is a planning language used in the development of an AI, it treats the problem as a "state space search" as to where the agent present in the task environment transitions from one state to another through the use of pre-defined actions. There are three main states in a STRIPS approach to creating a plan for an AI:

- Initial State - Starting condition of the system
- Goal State - Desired final condition of the system
- Actions (Operators) - Set of actions that may be used to move an agent from one state to another

Now each action in a plan has three main parts:

- Precondition - Conditions that must be met before an action is performed 
- Add List - Facts that become true after executing an action
- Delete List - Facts that are removed after completing an action 

STRIPS is a restrictive way to express states, actions and goals, but leads to more efficiency. 

Refer to the following image to see an example of how STRIPS can be implemented:

![Pasted image 20250315184851.png](/img/user/pngs/Pasted%20image%2020250315184851.png)

- States - description of the current situation in terms of facts, consisting of grounded, function free, positive literals (concrete facts that do not involve functions or negative statements)
	- The states above state that:
		- `At(Home)`: The agent **is at home**.
		- `Have(Bananas)`: The agent **has bananas**.
		- `At(X)`: The agent **is at location X** (if `X` is a variable, it means the agent could be at some unspecified location).
		- `Sells(X, Bananas)`: There exists a place `X` that **sells bananas**.
	- What **closed-world** means is that anything not explicitly stated is assumed to be false
		-  In the example above the example states that the agent is **AT HOME AND DOES NOT HAVE BANANAS**, it was denoted that the agent does not have bananas through the symbol `¬`
		- The second example states that the agent is **AT LOCATION `X` WHERE THERE EXISTS A PLACE `X` THAT SELLS BANANAS** 
- Goal - This states the success state the agent is expected to achieve
	- Goals can include conjunctions of literals representing more than one state
	- Goals can involve **conjunctions of literals**, and may contain **variables** (existential quantification).
	- Example Goals:
	    - $At(Home)∧¬Have(Banana)$  
	        (Be at home and **not** have a banana)
	    - $At(x)∧Sells(x, Bananas)$
	        (Be at some location **x** where bananas are sold)
- Actions - define what can be done to change a state, they consist of:
	- Preconditions - Condition that must be true before an action can be executed
	- Effects - Changes that happen after the action is executed 
	- An example of an action may be:
		- $Buy(Banana)$
			- Precondition - $At(Store) ∧ Sells(Store, Banana)$
			- Effect - $Have(Banana)$

## STRIPS Action Schema

>[!important]
>An action schema is simply a blueprint that defines the parameters and effects of an action. It includes the preconditions, effects and name of the action

Here's an example of an action schema:

- **Action** - $Sell(X,P)$
	- **Preconditions** - $At(X)∧Have(P)$
	- **Effect** - $Sold(P)∧Have(Money)$

The schema here specifies that in order to sell P at location X, the agent must be at X and have P (conjunction of two sub actions), thereafter the after effect of selling P at X leads to P being sold and the agent having Money (another conjunction)

An example of an implementation of STRIPS may be seen in the following image:

![Pasted image 20250316100759.png](/img/user/pngs/Pasted%20image%2020250316100759.png)

Here you can see the following is specified:

- Goal State - $ON(A,B)$
	- Preconditions - $ON(X, TABLE); EMPTYTOP(Y)$ 
- Start State - $ON(A, TABLE); ON(B,TABLE); EMPTYTOP(A); EMPTYTOP(B)$
- Actions - $Move(X,Y)$

The goal here is to place block A on block B using the moves $Move(X,Y)$. However, in order to use this move there should be a precondition where when moving onto the next block it must be empty and the table that the block moved out of has an after effect of being empty. 

The goal can be achieved like so:

1. $Move(A,B)∧EMPTYTOP(B)$ - Move A onto B with the precondition empty top
2. $ON(A,B)∧ON(B,TABLE)∧EMPTYTOP(A)∧¬EMPTYTOP(B)$
	1. States that A is On B
	2. B is on Table
	3. Top of A is empty
	4. Top of B is not empty (represented through negation sign `¬`)

If you wanted to treat the start conditions as a goal state the preconditions that must me met are like so:
 
 $EMPTYTOP(A)∧EMPTYTOP(B)∧ONTABLE(A,TABLE)∧ONTABLE(B,TABLE)$
 Thereafter ensuring that he conditions are met the add table and delete table may look like this:

  - Add table -  $EMPTYTOP(A)∧EMPTYTOP(B)∧ONTABLE(A,TABLE)∧ONTABLE(B,TABLE)$
  - Delete table - $ON(A,B)∧ON(B,TABLE)∧EMPTYTOP(A)∧¬EMPTYTOP(B)$

In terms of adding data to the add and delete list, you should put the new statements and conditions into the add list and the old no longer true conditions into the delete list. So:

- **Preconditions:**  
    $ON(A,TABLE), EMPTYTOP(B)$
    
- **Add List:**  
    $ON(A,B), EMPTYTOP(A)$
    
- **Delete List:**  
    $ON(A,TABLE), EMPTYTOP(B)$

## What is a state space?

>[!important] 
>A state space is a representation of all the possible combinations of a system representing all the possible states an algorithm may exist in

### **Key Components of a State Space:**

1. **States** – Each state represents a unique configuration of the system at a given point.
2. **Initial State** – The starting point in the state space.
3. **Goal State(s)** – The desired outcome(s) that the system aims to reach.
4. **Actions (Operators)** – The set of valid transitions that move from one state to another.
5. **State Transition Function** – Defines how actions change the current state to a new state.

There are two methods to create state spaces:

- Forward State Space Planning (FSSP):
	- Includes a start/initial state and a goal state
	- Often used in **forward search algorithms** like breadth-first search (BFS) or depth-first search (DFS)
	- New state includes positive literals of effect; the negated literals of effect are deleted
	- Also known as progression planning
- Backword State Space Planning (BSSP):
	- Same as FSSP except here you deconstruct your way backwords to achieve the initial start state
	- Its preconditions must hold in the previous situation, and these become subgoals which might be satisfied by the initial conditions
	- Search tree is expanded by considering actions that could have led to current state
	- Also known as regression planning

There is another planning method known as Partial Order Planning. Here, there is an option to achieve a state with any means possible assuming that the pre-conditions were already satisfied.