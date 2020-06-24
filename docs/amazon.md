#### <b> Top N Competitors/Buzzwords </b>
#### <b> Zombie in Matrix aka Min hours to send file to all available serversp </b>
#### <b> Critical Routers </b>
#### <b> Product Suggestions  </b>
#### <b> Number of Clusters </b>
<details>
<summary>Solution</summary>
```python
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        count=0 #to count number of islands
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j]=='1':
                    self.dfs(grid, i, j)
        return count

    def dfs(self, grid, i, j):
        #skip the dfs check if the current element is water or previosuly marked land
        if i<0 or j<0 or i>=len(grid) or j>=len(grid[0]) or grid[i][j]!='1': return
	#mark this newly visited land element
	grid[i][j]='0'

	#check all the adjacent elements to find land
	self.dfs(grid, i+1, j)
	self.dfs(grid, i-1, j)
	self.dfs(grid, i, j+1)
	self.dfs(grid, i, j-1)
```
</details>

#### <b> Reorder Data in Log Files </b>
<details>
<summary>Solution</summary>
```python
class Solution(object):
    def reorderLogFiles(self, logs):
        """
        :type logs: List[str]
        :rtype: List[str]
        """
        let_logs = []
        dig_logs = []
        for log in logs:
            log_key, log_val = log.split(" ", 1)
            if log_val[0].isalpha():
                let_logs.append(log_val + " " + log_key)
            else:
                dig_logs.append(log)

        let_logs.sort()
        let_logs_sorted = []

        for let_log in let_logs:
            log = let_log.split(" ")
            log = log[-1] + " " + " ".join(log[:-1])
            let_logs_sorted.append(log)
        return let_logs_sorted + dig_logs
```
</details>

#### <b> Optimal Utilization </b>
#### <b> Min Cost to Connect ropes/ Min Time to Merge Files </b>
<details>
<summary>Solution</summary>
```python
import unittest
import heapq


def solution(ropes):
    if len(ropes) < 2:
        return 0

    heapq.heapify(ropes)
    res = 0

    while len(ropes) > 1:
        sum = heapq.heappop(ropes) + heapq.heappop(ropes)
        res += sum
        heapq.heappush(ropes, sum)

    return res
```
</details>

#### <b> Treasure Island / Min Distance to Remove the Obstacle (BFS) </b>
<details>
<summary>Solution</summary>
```python
def solution(matrix):
    if (not matrix) or (not matrix[0]):
            return -1
        # store the index of matrix and steps in queue
        queue = deque()
        queue.append([0, 0, 0])
        while queue:
            i, j, steps = queue.popleft() # if the treasure island is found, return the steps 
            if matrix[i][j] == 'X':
                return steps
            # mark visited index
            matrix[i][j] = 'D'
            # check all the adjacent indexes
            for x, y in [(i-1, j), (i+1, j), (i, j-1), (i, j+1)]:
                if (0 <= x < len(matrix)) and (0 <= y < len(matrix[0])) and (matrix[x][y] != 'D'):
                    queue.append([x, y, steps+1])
        # if the treasure island is not found, return -1
        return -1
```
</details>

#### <b> Treasure Island II </b>

#### <b> Find Pair With Given Sum </b>
<details>
<summary>Solution</summary>
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        d = {}
        for i, n in enumerate(nums):
            val = target - n
            if val in d:
                return d[val], i
            d[n] = i
```
</details>
#### <b> Copy List with Random Pointer </b>
#### <b> Merge Two Sorted Lists </b>
<details>
<summary>Solution</summary>
```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l1 and not l2:
            return None

        if not l1 and l2:
            return l2

        if not l2 and l1:
            return l1

        if l1.val <= l2.val:
            l3 = ListNode(l1.val)
            l1 = l1.next
        else:
            l3 = ListNode(l2.val)
            l2 = l2.next
        head = l3

        while l1 and l2:
            if l1.val <= l2.val:
                l3.next = l1
                l1 = l1.next
            else:
                l3.next = l2
                l2 = l2.next
            l3 = l3.next

        if l1:
            l3.next = l1
        else:
            l3.next = l2

	return head

```
</details>

#### <b> Subtree of Another Tree </b>
<details>
<summary>Solution</summary>
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def isSubtree(self, s, t):
        """
        :type s: TreeNode
        :type t: TreeNode
        :rtype: bool
        """

        if s and not t:
            return True
        if not s and t:
            return False
        if self.isSameTree(s,t):
            return True

        return (self.isSubtree(s.left, t) or self.isSubtree(s.right, t))


    def isSameTree(self, s, t):
        if not s and not t:
            return True

        if not s or not t:
            return False

        if s.val != t.val:
            return False

        return self.isSameTree(s.left, t.left) and self.isSameTree(s.right, t.right)
```
</details>

#### <b> Search a 2D Matrix II </b>
<details>
<summary>Solution</summary>
```python
class Solution(object):
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        if not matrix:
            return False
        row = 0
        col = len(matrix[0]) -1
        while row < len(matrix) and col >= 0:
            if matrix[row][col] == target:
                return True
            elif matrix[row][col] > target:
                col -= 1
            elif matrix[row][col] < target:
                row += 1
        return False
```
</details>

####<b> Critical Connections </b>
####<b> Favorite Genres </b>
####<b> Two Sum - Unique Pairs </b>
####<b> Spiral Matrix </b>
####<b> Count substrings with exactly K distinct chars </b>
####<b> Max Of Min Altitudes </b>
####<b> Longest Palindromic Substring </b>
####<b> Substrings of size K with K distinct chars </b>
####<b>  Most Common Word </b>
<details>
<summary>Solution</summary>
```python
class Solution(object):
    def mostCommonWord(self, paragraph, banned):
        """
        :type paragraph: str
        :type banned: List[str]
        :rtype: str
        """
        for c in paragraph:
            if c in "!?',;.":
                paragraph = paragraph.replace(c, " ")
        words = [word for word in paragraph.lower().split()]

        d = {}
        for word in words:
            if word not in banned:
                if word in d:
                    d[word] += 1
                else:
                    d[word] = 1

        d = sorted(d, key=(lambda key:d[key]), reverse=True)
        return (d[0])
```
</details>

#### <b> K Closest Points to Origin </b>
<details>
<summary>Solution</summary>
```python
class Solution(object):
    def kClosest(self, points, K):
        import math, itertools
        """
        :type points: List[List[int]]
        :type K: int
        :rtype: List[List[int]]
        """
        d = {}

        for x,y in points:
            distance = math.sqrt(x**2 + y**2)
            d[(x,y)] = distance
        sorted_d =  sorted(d.items(), key=lambda x: x[1])
        result = [[x,y] for x,y in (dict(itertools.islice(sorted_d, K)))]
        return result
```
</details>

#### <b> Generate Parentheses </b>
#### <b> Min Cost to Connect All Nodes (a.k.a. Min Cost to Add New Roads) </b>
#### <b> Min Cost to Repair Edges (MST) </b>
#### <b> Prison Cells After N Days </b>
#### <b> Partition Labels </b>
#### <b> Subtree with Maximum Average </b>

