# Daily-Leetcode-problem-solution5

PROBLEM

Design an algorithm that accepts a stream of integers and retrieves the product of the last k integers of the stream.
Implement the ProductOfNumbers class:
ProductOfNumbers() Initializes the object with an empty stream.
void add(int num) Appends the integer num to the stream.
int getProduct(int k) Returns the product of the last k numbers in the current list. You can assume that always the current list has at least k numbers.
The test cases are generated so that, at any time, the product of any contiguous sequence of numbers will fit into a single 32-bit integer without overflowing.

Intuition

Here’s an efficient implementation of the ProductOfNumbers class using a prefix product approach. Instead of storing all numbers, we maintain a list of cumulative products, allowing us to compute the product of the last k numbers in constant time O(1).

Approach

Maintain a prefixProduct list where prefixProduct[i] stores the product of all elements from index 0 to i-1.
When adding a number:
If the number is 0, reset the prefix list (as anything multiplied by 0 results in 0).
Otherwise, compute the new cumulative product and store it in the list.
When retrieving the product of the last k numbers:
If k exceeds the available stored products (due to a reset from 0), return 0.
Otherwise, use the division property of prefix products:
Product of last k elements= prefixProduct[n−k]/prefixProduct[n]
​

Complexity

Time complexity:
O(1)

Space complexity:
O(n)

 
