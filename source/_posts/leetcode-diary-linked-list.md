---
title: Leetcode Diary - Linked List Templates
date: 2022-07-20 22:04:55
tags:
  - leetcode
  - interview
---

# Linked List Templates

A lot of the linked list solutions will depend on two things:

1. finding the mid point
2. reversing the linked list

It is useful to have these two methods handy.

## Finding midpoint via slow and fast pointers (hare and tortoise)

```python
def find_midpoint(head):
    slow,fast = head,head
    while fast is not None and fast.next is not None:
        slow = slow.next
        fast = fast.next.next
    return slow
```

## Reversing linked list

Often times you will see things like finding the mid point first, and then reverse the second halve (e.g. testing whether linked list is a palindrome).

```python
def reverse_linkedlist(head):
    prev = None
    while head is not None:
        temp = head.next
        head.next = prev
        prev = head
        head = temp
    return head
```
