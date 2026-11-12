# Project Leetcode

## Problem 1 [25 points]

### Problem Information

Problem Name: *Tribonacci*

[https://leetcode.com/problems/n-th-tribonacci-number/submissions/2193500402/]()

*Insert your screenshot here, named `problem-1.png`.*
![p1](problem-1.png)

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 2 [25 points]

### Problem Information

Problem Name: *Combination Sum*

[Submission Link](https://leetcode.com/problems/combination-sum/submissions/2193576214/)

*Insert your screenshot here, named `problem-2.png`.*
![p2](problem-2.png)

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 3 [25 points]

### Problem Information

Problem Name: *Flower Planting*

[Submission Link](https://leetcode.com/problems/flower-planting-with-no-adjacent/submissions/2194243294/)

![p3](problem-3.png)

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 4 [10 points]

### Problem Information

Problem Name: *Triangle*

[Submission Link](https://leetcode.com/problems/triangle/submissions/2194254374/)

![p4](problem-4.png)

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 5 [10 points]

### Problem Information

Problem Name: *Number of provinces*

[Submission Link](https://leetcode.com/problems/number-of-provinces/)

![p5](problem-5.png)

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 6 [5 points]

### Problem Information

Problem Name: *Course Schedule*

[Submission Link](https://leetcode.com/problems/course-schedule/submissions/2194271699/)

[p6](problem-6.png)

### Time Complexity

```py
from collections import defaultdict


class Solution:
    def canFinish(self, numCourses: int, prerequisites: list[list[int]]) -> bool:
        connectedCourses = defaultdict(list)                            # O(1) initialization is constant
        for a, b in prerequisites:                                      # O(N) each prereq is added to dictionary
            connectedCourses[b].append(a)                               # O(1) Appending is constant
        visited = set()                                                 # O(1) initialization is constant
        inProgress = set()                                              # O(1) initialization is constant

        def search(i):                                                  # O(N*E) each node and all its edges are visited
            visited.add(i)                                              # O(1) adding is constant
            inProgress.add(i)                                           # O(1) initialization is constant
            for j in connectedCourses[i]:                               # O(E) Each edge of node is considered
                if j in inProgress:                                     # O(1) Comparison is constant
                    return False                                        # O(1) Return is constant
                if j not in visited:                                    # O(1) Comparison is constant
                    if not search(j):                                   # O(1) Comparison is constant
                        return False                                    # O(1) Return is constant
            inProgress.remove(i)                                        # O(1) Removal is constant
            return True                                                 # O(1) initialization is constant

        for i in range(numCourses):                                     # O(N) Each course is hit
            if i not in visited:                                        # O(1) Set check is constant
                if not search(i):                                       # O(1) Comparison is constant
                    return False                                        # O(1) Return is constant
        return True                                                     # O(1) initialization is constant

```
Time complexity is **O(N*E)** due to the DFS search algorithm.
### Space Complexity
```py
from collections import defaultdict


class Solution:
    def canFinish(self, numCourses: int, prerequisites: list[list[int]]) -> bool:
        connectedCourses = defaultdict(list)                        # O(1) initialization is constant
        for a, b in prerequisites:                                  # O(N) Each node is added
            connectedCourses[b].append(a)                           # O(1) Each append is constant
        visited = set()                                             # O(1) initialization is constant
        inProgress = set()                                          # O(1) initialization is constant

        def search(i):
            visited.add(i)                                          # O(N) Eventually all are visited
            inProgress.add(i)                                       # O(E) All nodes are added, but then removed.
            for j in connectedCourses[i]:                   
                if j in inProgress:
                    return False
                if j not in visited:
                    if not search(j):
                        return False
            inProgress.remove(i)                                    # O(1) Removal is constant
            return True

        for i in range(numCourses):
            if i not in visited:
                if not search(i):
                    return False
        return True

```
Time complexity is **O(2N * E)** due to storing courses and their prereqs.

----

## Problem 7 [5 extra credit points]

### Problem Information

Problem Name: *fill me in*

[Submission Link]()

*Insert your screenshot here, named `problem-7.png`.*

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 8 [5 extra credit points]

### Problem Information

Problem Name: *fill me in*

[Submission Link]()

*Insert your screenshot here, named `problem-8.png`.*

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 9 [5 extra credit points]

### Problem Information

Problem Name: *fill me in*

[Submission Link]()

*Insert your screenshot here, named `problem-9.png`.*

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

----

## Problem 10 [5 extra credit points]

### Problem Information

Problem Name: *fill me in*

[Submission Link]()

*Insert your screenshot here, named `problem-10.png`.*

### Time Complexity

*Fill me in*

### Space Complexity

*Fill me in*

## Project Review

*Fill me in*