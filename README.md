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
[Back to Top](#table-of-contents)

**Problem:**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

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
