---
{"dg-publish":true,"permalink":"/content/digital-garden-content/ifs/leetcode/find-the-majority-element-ii/","updated":"2026-07-08T08:24:37.452+05:30","dg-note-properties":{}}
---

#### Problem Description

- Concept wise, the problem here is similar to the find the majority element 1 problem. However, there is a caveat. In this case, we need to find the element that occurs $\frac{n}{3}$ times in the array `n` being the number of elements in the array).
- Once again we are given a challenge, the space complexity of this algorithm must be no more than `O(1)`, so just like before we need to achieve constant time.

#### Solution Explanation

- For this solution, it is similar to what we did in the first problem (Majority Element I), however here we want to utilize a HashMap. So, if we were to brute force our way through this we could create a recursive loop that populates the HashMap with each occurrence of an element and then we find out which elements occur more that $\frac{n}{3}$ of the time. 
- However, to minimize the time complexity from `O(n)` to `O(1)` we can introduce a limitation. **Given that we may find  2 or 1 elements that meet the criteria, we can introduce a limit to the HashMap so that it does not exceed 2 elements.**
- What we mean here is that, only 2 elements can be in the HashMap at a time and it must in no way be exceeded.

#### Implementation

```python
```
