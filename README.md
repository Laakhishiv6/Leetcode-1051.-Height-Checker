# Leetcode-1051.-Height-Checker
# Description
A school is trying to take an annual photo of all the students. The students are asked to stand in a single file line in non-decreasing order by height. Let this ordering be represented by the integer array expected where expected[i] is the expected height of the ith student in line.

You are given an integer array heights representing the current order that the students are standing in. Each heights[i] is the height of the ith student in line (0-indexed).

Return the number of indices where heights[i] != expected[i].

# Solution
In the given question we have been given an array which contains the heights of students . The students are asked to stand in increasing order . In order to do this we have to see in which indices are the children not in the correct place .

We will create another array expected which contains the heights in increasing order and we will be using this expected array to compare it with the original heights array . If we find there is not matching in for the ith index of both the arrays we will increment the count by 1.

Example :

Input: heights = [1,1,4,2,1,3]

heights:  [1,1,4,2,1,3]

expected: [1,1,1,2,3,4]

Since the indices 2,4 and 5 do not match so return 3 as the answer

Output: 3

# Algorithm
1. Take the input list heights.
2. Create a sorted version of heights and store it in expected.
3. Initialize a counter count = 0.
4. Loop through each index i from 0 to len(heights) - 1.
5. If heights[i] != expected[i], increment count by 1.
6. Return the value of count.

# Code
class Solution:

    def heightChecker(self, heights: List[int]) -> int:
        count=0
        expected=sorted(heights)
        for i in range(len(heights)):
            if heights[i]!=expected[i]:
                count+=1
            
        return count
# Time complexity
Sorting: sorted(heights) takes O(n log n) time.

Comparison loop: Comparing elements takes O(n) time.

👉 Total Time Complexity:
O(n log n)
