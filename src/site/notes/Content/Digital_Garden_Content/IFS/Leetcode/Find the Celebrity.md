---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/leetcode/find-the-celebrity/","updated":"2026-07-08T07:48:23.002+05:30","dg-note-properties":{}}
---

### Find the celebrity

#### Problem Description

- Task here is to find out who the celebrity is from `n` number of people. The predicates that need to be considered is that:
	- **A celebrity knows no one**
	- **A celebrity is known by everyone but themselves**
	- **A time complexity of O(n) needs to be achieved**
- Additionally we are given a function called `knows` that will tell us if `a` knows `b` through a unidirectional manner.
- Additionally, one key challenge here is that we minimize the number of times we call the knows API, such that we do not utilize it similar to how we would in the brute force approach.

#### Solution Explanation

- There are two distinct solutions to this problem, one way is by brute forcing it whereas the other is by simply following a strategic algorithm.
- If we were to brute force the problem it would mean that we consider all the possible knows between each person to formulate a graph that shows us how many people know each other. However, the down side to this is that it will have a time complexity of **O(n$^2$)**.
- So, the more ideal solution would be the following:
![Pasted image 20260707231058.png](/img/user/pngs/Pasted%20image%2020260707231058.png)
- We can setup an algorithm where we create a search pattern that works on these two negative predicates:
	- If a person is not known by someone, they are outed as a potential candidate
	- If a person knows someone else, they are outed as a potential candidate
- Knowing this we can go ahead and carry out a linear search where we go through each person, check to see if they know the person ahead of them, if they do we switch to them as the potential candidate, then we move to the next and if we do not know them, we do not switch candidates given that that person is not known by us hence making them something we do not consider.
- We can implement the solution through the following pattern:
#### Implementation

```python
# The knows API is already defined for you.

# return a bool, whether a knows b

# def knows(a: int, b: int) -> bool:

  

class Solution:

    numberOfPeople = 0

    def findCelebrity(self, n: int) -> int:

        self.numberOfPeople = n

        celebrityCandidate = 0 # start with 0

        for i in range(n):

            if (knows(celebrityCandidate, i)): # if 0 knows someone else

                celebrityCandidate = i # switch to them

        if self.isCelebrity(celebrityCandidate):

            return celebrityCandidate # check to see if celeb

        return -1

    def isCelebrity(self,i: int) -> bool: # brute force approach per person

        for j in range(self.numberOfPeople):

            if (i==j):

                continue

            if (knows(i,j) or not knows(j,i)):

                return False

        return True
```
