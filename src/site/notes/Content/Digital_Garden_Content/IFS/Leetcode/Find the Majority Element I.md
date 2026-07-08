---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/leetcode/find-the-majority-element-i/","updated":"2026-07-08T08:18:19.840+05:30","dg-note-properties":{}}
---

#### Problem Description

- Here we are given an integer array of `n` number of elements, our task is to find the element that occurs over $\frac{n}{2}$ times. We are additionally told that we may always expect a majority element in the array.
- So, we can first denote that the majority element here must occur $\frac{n}{2}$ times in the array, given this we may then denote that there is only one majority element.
- The challenge here is to maintain a space complexity of `O(1)` without using something like a HashMap for every value in the array just to see what has the highest occurrence count.

#### Solution Explanation

- For the solution to this problem, we need to ensure that the space complexity is constant. What we can do to achieve this is utilize something called the *Bayer Moore* theory. How it works is that we are given a list of numbers, so we loop through each one and maintain a score of what the current majority number is. 
- Each time the score hits zero, we change the majority number to whatever the value we were currently in is, hence updating the majority value.
- Through the use of this theory, we can settle on the fact that the majority element can be found only if there actually is one, otherwise this theory is useless. Refer to the example of how the algorithm works below:

![Pasted image 20260708080826.png](/img/user/Pasted%20image%2020260708080826.png)

#### Implementation

```python
class Solution:

    def majorityElement(self, nums: List[int]) -> int:

        res, count = 0, 0 # we initialize the result, count

        for n in nums:

            if count == 0: # If the count becomes 0 we change the result

                res = n

            count += (1 if n == res else -1) 
            # increment only if n is the same as res 

        return res
```
