# Linked-List-Cycle
Given head, the head of a linked list, determine if the linked list has a cycle in it.  There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Return true if there is a cycle in the linked list. Otherwise, return false.

class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None

class Solution:
    def hasCycle(self, head):
        if not head or not head.next:
            return False
        
        slow = head
        fast = head

        while fast.next and fast.next.next:
            fast = fast.next.next
            slow = slow.next

            if slow == fast:
                return True

        return False
