---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/leetcode/find-the-town-judge/","updated":"2026-07-08T07:48:50.458+05:30","dg-note-properties":{}}
---

#### Problem Description

- This problem is similar to the find the celebrity problem context wise, however in this problem we are given an array of edges that represent a combination of who trusts who. For example: trust$[i]$ = $[a_i$ , $b_i]$, this states that person a trusts person b. So, with this concept we must implement an algorithm that will find who is the town judge.
- The predicates to adhere to include:
	- **The town judge knows no one**
	- **The town judge is known by everyone except themself**

#### Solution Explanation

- As a solution to this, there are two approaches. One follows a brute force like approach whereas the other follows a more algorithmic approach. Through the brute force approach we may assume a time complexity of O(n$^2$) whereas if we were to utilize the algorithmic approach it would constitute a complexity of O(n) which is linear.
- So, what we need to understand here is that we have a series of inbound and outgoing trust messages that we can turn into variables.
	- In order for someone to be a town judge, the incoming trust messages would at most be `n-1`, n being the total number of people in the town. The reason this is the case is due to it being a requirement that the judge is trusted by everyone **but themselves**.
	- Besides that, the judge may have 0 outgoing trust messages given that they can trust no one else.
- Now, given these predicates we can have a trust score that increments through a loop every time the town judge gets a trust message and decrement the trust score every time the judge trusts someone else.
- So, we finally give a hard rule that the `trust_score == n-1` given that it is then impossible to get a value below that if you want to be the judge since trusting someone else would deduct a point.
	- The verdict here is that if you trust nobody else, you loose 0 points, and if everyone trusts you, your final score should equal n-1
- The implementation is simple:
#### Implementation

```python
class Solution:

    def findJudge(self, n: int, trust: List[List[int]]) -> int:

        delta = defaultdict(int) # use a default dict 

        for src, dst in trust:

            delta[src] -= 1

            delta[dst] += 1

  

        for i in range(1, n + 1):

            if delta[i] == n - 1:

                return i

        return -1
```

- So, a breakdown for the implementation is that we initialize a dictionary called delta which represents the score line. We increment it whenever the destination receives a trust and decrement whenever the source receives one. 
- This default dict will increment this for every person in the town and in the end, we will do a check to see who had a score of `n-1`. Whoever that person is, becomes the judge.
