---
{"dg-publish":true,"permalink":"/content/digital-garden-content/artificial-intelligence-content/first-order-logic-logical-agents-and-prepositional-logic/","updated":"2025-04-08T20:06:31.726+05:30"}
---

#DIgitalGarden 

## Logical Agents

>[!important]
>A logical agent is an artificial intelligence system that makes decisions based on formal logic, they rely on knowledge representations and inference to make rational and logical decisions 

A logical agent relies of the use of formal logic in order to make rational decision, formal logic being a type of structured language which utilizes a systematic way of reasoning to achieve a goal or follow rules through a structured set of symbols, etc. There are two main types of formal logic:

### 1. Propositional logic

- In other words, this is simply Boolean logic as to where there are true and false statements that may be placed together sequentially
- E.g:
	- P - Its raining
	- Q - The ground is wet
	- Rule: `P->Q`, if its raining then the ground is wet
### 2. First-Order Logic

- This is an extension to propositional logic as to where the use of quantifiers is introduced, inclusive of predicates.
- E.g:
	- ∀x(Bird(x)→CanFly(x))
	- The example above states that "For all x, if x is a bird, then x can fly"

In terms of what **knowledge representation** means to a logical agent, it refers to the process of structuring information so that a computer can process it logically and make decisions. 

**Inference** on the other hand refers to the process of deriving new facts from existing knowledge using logical reasoning. This is what enables an AI system to derive and make new facts from existing knowledge bases.

A **knowledge base** is a store of facts and rules about the world using formal representation through the use of propositional or first order logic. It is used by agents to infer new facts by simply regarding the logics in its knowledge base.

## What is a knowledge based agent?

>[!important]
>It is a type of agent that is based on a set of sentences in formal language defining the rules and components of a this agent. It regards the use of these rules in order to make decisions

The sentences stored in a knowledge based agent are expressed using a knowledge based language. To define a knowledge based agent, you would need to define the components it requires to derive new facts from existing ones in its knowledge base (achieved through inference). 

A **declarative approach** may be taken to achieve this, this approach simply means that the knowledge base is initialized without any knowledge at first, it is up to us to define its core components and properties. There are two functions to this approach:

- **TELL** - add new sentences to the knowledge base 
- **ASK** - ask what is known from the knowledge base

The main components of a knowledge based agent are the following:

- **Knowledge base** - Stores the rules, facts and world knowledge the agent knows in a structured form such that it will abide by them
- **Inference Engine** - The engine in the agent that is responsible for logical reasoning and deriving new facts from existing knowledge
- **Perception Sensors** - Devices and means taken by the agent to perceive data from its task environments
- **Query Mechanism** - Enables users to query the agent and assess it
- **Actuators** - Means taken by the agent to react to its environment by responding to it (e.g. a path finding agent may use its wheels to react and move around a maze, hence making the wheels its actuators)
	- **Percept** - Term used to define the information taken in by an agent at any given time (these could be from sensors, cameras, etc) 

In terms of the main features and structure of a knowledge based agent, regard the following image:

![Pasted image 20250320172351.png](/img/user/pngs/Pasted%20image%2020250320172351.png)

- **Domain Independent Algorithms** - a type of algorithm that does not reply on a single domain or source of knowledge to solve a problem (this is connected to the inference engine as it states that it does not need to rely on a single knowledge base to solve an answer hence making it an optimal connection to an inference engine)
- **Inference Engine** - components of knowledge based agent that derives new facts with existing knowledge
- **Knowledge Base** - component that stores facts, rules and structured knowledge for the agent
- **Domain Specific Content** - specialized knowledge for a particular field 

To conclude what a knowledge based agent (**KBA**) is, its simply an agent that perceives the world around it based on its knowledge base. Any percept it receives will be used in an inference engine to generate logic based decisions that are treated as new facts. You can say that a KBA infers hidden characters in its current state through the process of logically mapping its decisions through its knowledge base. 

## What is Wumpus World?

>[!important]
>Wumpus world is an example/implementation of a knowledge based agent which could demonstrate how an agent as such perceives the world around it. It represents the actions, percept's, etc that the agent is capable of utilizing
>

In other words, Wumpus world is a game set in a task environment with 16 grids (4x4) where each grid is connected to each other horizontally or vertically. Here are the main takeaway points:

- The game is in a 16 (4x4) grid task environment
- The agent starts at position (1,1)
- Some grids have "pits" and others have "treasures" or a beast called "Wumpus"
- The goal of the agent is to move through the maze and find the treasure without falling into a pit or getting eaten 
- To assist the agent, some grids may have a "stench" to hint at the beast being in a room adjacent to it
- The agent is given an arrow to kill Wumpus if found (or assumed to be found)

The layout of the grid with all the mentioned features may be laid out like so:

![Pasted image 20250321203200.png](/img/user/pngs/Pasted%20image%2020250321203200.png)

Regarding a **peas** based approach, these are the components to Wumpus world:

- **Performance** - Reinforcement based goals provided to ensure that the agent reaches the goal:
	- Moving through a grid = -1 point
	- Finding the treasure = 1000 points
	- Agent using arrow = -100 points
	- Agent dies = -100 points
	- The agent is penalized for making a negative move hence encouraging it to take the better option 
- **Environment** - The task environment is:
	- **Partially Observable** - Agent cannot see every room but can see grids adjacent to its current position
	- **Deterministic** - There is a finite number of moves it can take to reach a treasure
	- **Static** - The environment does not change while the agent does not move
	- **Discrete** - The number of possible outcomes for the grid will always be countable
	- **Single-Agent** - There is only one moving agent in the environment
	- **Episodic** - Each move made in the environment does not affect the next as it is independant of affecting the next move, hence making each move an "episode"
	- **Benign** - There are no external factors that can affect the games outcome
	- **Known** - The rules are known by the agent
- **Actuators** - The means in which the agent are to traverse the grid include:
	- Moving up
	- Moving down
	- Moving left
	- Moving right
	- Shoot Arrow
	- Grab Treasure
	- Release 
- **Sensors** - The means in which the agent will take to perceive its environment:
	- Breeze (adjacent room to pit)
	- Stench (adjacent room to monster has stench)
	- Glitter (room that has treasure is glittery)
	- Scream (When the Wumpus is killed)
	- Bump (when the agent hits a wall)

## Propositional Logic

>[!important]
>Propositional logic is the most fundamental form of logic that could represent an algorithm. A proposition is basically a declarative statement that could either be true or false

There are two types of propositions you should know about:

- **Atomic Propositions**: A type of proposition that states if a statement made is either true or false (e.g. The sky is blue), these statements can only ever be true or false
- **Compound Proposition:** This is a combination of atomic propositions through the use of conjunctions and logical connectives:
	- **Conjunction**: A and B = A ∧ B (AND)
	- **Disjunction**: A or B = A ∨ B (OR)
	- **Negation**: ¬A = Not A
	- **Implication**: A→B, If A then B (XOR - different values = TRUTH)
	- **IFF**: If and only if A then B, A↔B statement that goes both ways (XAND - same values = TRUTH)

Compound propositions are quite similar to basic Boolean logic as to where there are truth tables and simple connectives, however it is only limited to basic conjunctions hence making it an oversimplified manner of approaching an issue.

## First Order Logic (predicate logic)

>[!important]
>FOL is an extension to propositional logic as to where it is capable of representing more propositions through the use of an extended list of statements, It in other words, is another simplified way of representing knowledge bases

Propositional logic assumes that the world contains facts (e.g. The sky is blue, a fact that already pre-exists) whereas first order logic assumes that the world contains:

- **Objects**: Entity within a domain (e.g. A person)
- **Relations**: Associations between objects (e.g. A hand | " is a part of "| a body)
- **Functions**: Operations that map objects to other objects (e.g. There is more than one hand)

Unlike basic propositional logic, FOL has multiple components to it that regard the following attributes:

- **Constants**: Values that do not change and remain the same
- **Variables**: Values that change as per request of a function or initializer
- **Predicates**: True or false functions that indicate if a property or relationship between objects are true or false (e.g `A=2, B=3, greaterThan(2,3) = TRUE` since $3\gt2$)
- **Functions**: Map objects to other objects (e.g. `MotherOf(x) = y`)
- **Connectives**: ∧, ∨, ¬, ⇒, ⇔
- **Equalities:** ==
- **Quantifiers**: Specifies the scope of a variable through implying the following:
	- **Universal Quantifier (∀)**: This quantifier applies to all predicates in a statement like so, $∀x(Humans(x)⇒Mortal(x))$, this states that all humans are mortal
	- **Existential Quantifiers (∃)**: This quantifier states that the predicate in the statement is true for at least one individual, $∃x (Person(x) ∧ Likes(x, IceCream))$, this statement states that "at least one person likes ice cream" unlike a universal quantifier which would state that all persons like ice cream

The structure of an atomic sentence (sentence that cannot be simplified any further) can be broken down like so:

![Pasted image 20250328173121.png](/img/user/pngs/Pasted%20image%2020250328173121.png)

- The predicate is the precursor to the statement as it is what defines the logic of what is to happen inside the its function
- The contents inside are the either the term or the constant

## What are the properties of FOL?

- **Validity**: This property states that a formula is valid if it holds true for all possible interpretations of itself
- **Satisfiability:** If a formula can be satisfied or made true in some manner or interpretation then it may be considered satisfiable
- **Un-satisfiability**: If a formula cannot be satisfied in any manner at all it is then considered as to being un-satisfiable 
- **Entailment**: If a formula implies another formula, then it means that the truth of the premise implies the truth of the conclusions (e.g. ∀x (P(x) → Q(x)) and ∀x P(x) , we can logically infer ∀x Q(x), it states here that for all x, the P(x) of x will imply the Q(x) of x hence producing the statement that for all X, P(x) is True and like wise for all of Q(x))