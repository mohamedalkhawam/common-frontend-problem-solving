# Problem Solving Solutions

This repository contains solutions to various problem-solving questions organized by category. Click on a problem to jump to its solution. Each solution includes a back-to-top link for easy navigation.

## Table of Contents

### Arrays
- [Two Sum](#two-sum)
- [Product of Array Except Self](#product-of-array-except-self)
- [Maximum Subarray](#maximum-subarray)
- [Contains Duplicate](#contains-duplicate)
- [Move Zeroes](#move-zeroes)
- [Rotate Array](#rotate-array)
- [Intersection of Two Arrays](#intersection-of-two-arrays)
- [Maximum Product Subarray](#maximum-product-subarray)
- [Longest Consecutive Sequence](#longest-consecutive-sequence)
- [Spiral Matrix](#spiral-matrix)
- [Set Matrix Zeroes](#set-matrix-zeroes)

### Strings
- [Valid Parentheses](#valid-parentheses)
- [Valid Anagram](#valid-anagram)
- [Longest Substring Without Repeating Characters](#longest-substring-without-repeating-characters)
- [Group Anagrams](#group-anagrams)
- [Word Search](#word-search)
- [Generate Parentheses](#generate-parentheses)
- [Longest Palindromic Substring](#longest-palindromic-substring)
- [Valid Palindrome](#valid-palindrome)
- [FizzBuzz](#fizzbuzz)

### Linked Lists
- [Merge Two Sorted Linked Lists](#merge-two-sorted-linked-lists)
- [Reverse a Linked List](#reverse-a-linked-list)
- [Detect Cycle in a Linked List](#detect-cycle-in-a-linked-list)
- [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
- [Add Two Numbers](#add-two-numbers)
- [Flatten a Multilevel Doubly Linked List](#flatten-a-multilevel-doubly-linked-list)
- [Reverse Nodes in k-Group](#reverse-nodes-in-k-group)
- [Remove Duplicates from Sorted List II](#remove-duplicates-from-sorted-list-ii)

### Trees and Graphs
- [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)
- [Binary Tree Level Order Traversal](#binary-tree-level-order-traversal)
- [Number of Islands](#number-of-islands)
- [Lowest Common Ancestor of a Binary Tree](#lowest-common-ancestor-of-a-binary-tree)
- [Binary Tree Zigzag Level Order Traversal](#binary-tree-zigzag-level-order-traversal)
- [Binary Tree Maximum Path Sum](#binary-tree-maximum-path-sum)
- [Graph Depth-First Search (DFS)](#graph-depth-first-search-dfs)
- [Shortest Path in a Grid](#shortest-path-in-a-grid)

### Dynamic Programming
- [Climbing Stairs](#climbing-stairs)
- [Min Stack](#min-stack)
- [Combination Sum](#combination-sum)
- [Coin Change](#coin-change)
- [Maximal Square](#maximal-square)

### Searching and Sorting
- [Binary Search](#binary-search)
- [Search Insert Position](#search-insert-position)
- [Find Minimum in Rotated Sorted Array](#find-minimum-in-rotated-sorted-array)
- [Kth Largest Element in an Array](#kth-largest-element-in-an-array)
- [Top K Frequent Elements](#top-k-frequent-elements)
- [Sort Colors](#sort-colors)
- [Search in Rotated Sorted Array](#search-in-rotated-sorted-array)
- [Merge Intervals](#merge-intervals)
- [Count of Smaller Numbers After Self](#count-of-smaller-numbers-after-self)

### Design
- [Design a Hit Counter](#design-a-hit-counter)
- [LRU Cache](#lru-cache)
- [Implement Queue using Stacks](#implement-queue-using-stacks)
- [Implement Trie (Prefix Tree)](#implement-trie-prefix-tree)

---

## Arrays

### Two Sum

**Problem:**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

**Plan:**
1. Initialize a hash map to store the numbers and their indices.
2. Iterate through the array.
3. For each number, calculate its complement by subtracting it from the target.
4. Check if the complement exists in the hash map.
5. If it does, return the current index and the index of the complement.
6. If it doesn’t, add the current number and its index to the hash map.

**Steps:**
1. Create an empty hash map `map`.
2. Loop through the array with index `i` and value `nums[i]`.
3. Compute the complement `target - nums[i]`.
4. If `complement` is in `map`, return `[map[complement], i]`.
5. Otherwise, set `map[nums[i]] = i`.
6. If no solution is found, return an empty array.

**Pseudo Code:**
```pseudo
function twoSum(nums, target):
    map = {}
    for i from 0 to length(nums) - 1:
        complement = target - nums[i]
        if complement in map:
            return [map[complement], i]
        map[nums[i]] = i
    return []
```

**Solution:**
```typescript
function twoSum(nums: number[], target: number): number[] {
    const map = new Map<number, number>();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (map.has(complement)) {
            return [map.get(complement)!, i];
        }
        map.set(nums[i], i);
    }
    return [];
}
```


**Time Complexity:**

* Step-by-step:
  * Initializing the hash map takes O(1).
  * Iterating through the array of n elements takes O(n).
  * Hash map operations (insertion and lookup) are O(1) on average.

* Overall:
  * The overall time complexity is O(n) because we only iterate through the array once.


##### [Back to Top](#table-of-contents)



### Product of Array Except Self


**Problem:**
Given an array nums of n integers where n > 1,
return an array output such that output[i] is equal to the product of all the elements of nums except nums[i].



**Plan:**
1. Create two arrays, `left` and `right`, to store the product of all the elements to the left and right of each index, respectively.
2. Compute the `left` products.
3. Compute the `right` products.
4. Multiply the `left` and `right` products to get the final result.




**Steps:**
Initialize arrays `left` and `right` with length equal to `nums` and all elements set to 1.
Compute the `left` array:
Set `left[0]` = 1.
For each index i from 1 to n-1, set left[i] = left[i-1] * nums[i-1].
Compute the `right` array:
Set `right[n-1]` = 1.
For each index `i` from `n-2` to 0, set `right[i] = right[i+1] * nums[i+1]`.
Compute the result array by multiplying `left` and `right`.

**Pseudo Code:**
```pseudo
function productExceptSelf(nums):
    n = length(nums)
    left = array of 1s with length n
    right = array of 1s with length n
    result = array of 1s with length n
    
    for i from 1 to n-1:
        left[i] = left[i-1] * nums[i-1]
    
    for i from n-2 to 0:
        right[i] = right[i+1] * nums[i+1]
    
    for i from 0 to n-1:
        result[i] = left[i] * right[i]
    
    return result
```

**Solution:**
```typescript
function productExceptSelf(nums: number[]): number[] {
    const n = nums.length;
    const left = new Array(n).fill(1);
    const right = new Array(n).fill(1);
    const result = new Array(n).fill(1);

    for (let i = 1; i < n; i++) {
        left[i] = left[i - 1] * nums[i - 1];
    }

    for (let i = n - 2; i >= 0; i--) {
        right[i] = right[i + 1] * nums[i + 1];
    }

    for (let i = 0; i < n; i++) {
        result[i] = left[i] * right[i];
    }

    return result;
}
```
**Time Complexity:**

* Step-by-step:
    * Initializing the `left`, `right`, and `result` arrays takes O(n).
    *  Filling the `left` array takes O(n).
    *  Filling the `right` array takes O(n).
    *  Creating the `result` array takes O(n).

* Overall:
    * The overall time complexity is O(n) because we only iterate through the array once.

##### [Back to Top](#table-of-contents)

