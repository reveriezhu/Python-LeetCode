# LeetCode 1-50

1 [Two Sum](https://leetcode.com/problems/two-sum/description/)
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        dicts = {}
        for k, v in enumerate(nums):
            if target - v in dicts:
                return [dicts.get(target-v), k]
            dicts[v] = k
```

2 [Add Two Numbers](https://leetcode.com/problems/add-two-numbers/description/)
```Python
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        a = b = 0
        carry = 0
        while l1:
            a += l1.val * 10 ** carry
            carry += 1
            l1 = l1.next
        carry = 0
        while l2:
            b += l2.val * 10 ** carry
            carry += 1
            l2 = l2.next
        ret = a + b
        h = m = ListNode(0)
        if not ret:
            return h
        while ret:
            m.next = ListNode(ret % 10)
            ret /= 10
            m = m.next
        return h.next
```

