---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/leetcode/gas-station-problem/","updated":"2026-07-08T07:59:22.667+05:30","dg-note-properties":{}}
---

#### Problem Description

- The gas station problem follows a divide and conquer pattern. It states that there are n gas stations across a circular route that comes back to whatever gas station we started at. You have a car with an unlimited gas tank and it costs `cost[i]` of gas to travel from the `ith` station to its next `(i + 1)th` station. You begin the journey with an empty tank at one of the gas stations. Given two integer arrays, `fuel` and `cost`, return the starting point/gas stations index if a full trip around the circle is possible or just return -1.
- To break it down simply, we need to find the optimal gas station that we can start at, given that in order to move from one gas station to another there is a cost and a gain in terms of fuel. So, we need to determine how much it would cost to go from one point to another and if the fuel in the car can be kept greater that 0. 
- A caveat we are going to come across here is that we need to attain an optimal time complexity as well as an optimal space complexity.

#### Solution Explanation

- So, we have two integer arrays that have a negative correlations to each other. The indexes of each array represent the current gas station we are in and what the cost and gain is going to be when moving into the next `i+1` station. Given this, we can pick up on the idea of a score like before.
- Aside from that we would need to note down some rules:
	- The starting positions fuel must be greater than 0
	- The `sum(gas) >= sum(cost)`
	- We would need to assume a greedy first approach where you consider the first `gas_cost` that is greater than 0 to work. Also `gas_cost = gas[i] - cost[i]`
- So, what we are going to want to do is initialize an overall cost delta and iterate through each value and see what the cost is. Thereafter, we can go on this loop where we figure out what the value we can start from is. The gimmick here is that we start from the first value where the delta is `>=` 0, making it the first positive integer that we start at given that this is a greedy approach we are assuming. With this greedy approach we can assume a time complexity of `O(n)` and memory complexity of `O(1).
- So, the baseline for this approach is that we have a recursive loop that goes through the deltas of each `gas_cost` and then settles on the first `gas_cost` that produces a positive value. 
![Pasted image 20260708075840.png](/img/user/Pasted%20image%2020260708075840.png)
- Thereafter, as you can see we then have a total of `+6` gas towards the end of the array, and then when looping back it may be seen that we can make a full circuit back to position `3`.

#### Implementation

```python
class Solution:

    def canCompleteCircuit(self, gas: List[int], cost: List[int]) -> int:

        if sum(gas)<sum(cost):

            return -1

        total = 0

        starting_position = 0

        for i in range(len(gas)):

            total += (gas[i] - cost[i])

            if total < 0:

                total = 0

                starting_position = i + 1 # switch to the next starting pos

        return starting_position
```

- Whenever the total goes under 0 we move the starting index to the next position and repeat the loop.
