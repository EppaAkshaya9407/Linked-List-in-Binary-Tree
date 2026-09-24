# Linked-List-in-Binary-Tree
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSubPath(self, head: Optional[ListNode], root: Optional[TreeNode]) -> bool:
        if head is None:
            return True
        if root is None:
            return False
        def path(root,temp):
            if temp is None:
                return True
            if root is None:
                return False
            if root.val==temp.val:
               return  path(root.left,temp.next) or path(root.right,temp.next)
            return False
        if path(root,head):
            return True
        return self.isSubPath(head,root.left) or self.isSubPath(head,root.right)
    
