# A. Odd One Out


![](https://espresso.codeforces.com/3dbe9fb28d462bb9a6d7f23d69940785a22b061c.png)

Output

Output exactly two characters: a single letter followed by a single digit, with no spaces or additional characters between them.

# B. Are You Smiling?


Show us a smile! 😁

Output

For a properly chosen ?, the following equation holds: U+?=HAPPY.

Output ?, a string consisting of uppercase letters and numbers.

Example

Input



show us your smile!

Output


# C. And?

RXOEARDMTINHUSERMEDESIANT & 20260401

Input

Each test contains multiple test cases. The first line contains the number of test cases t (1≤t≤105). The description of the test cases follows.

The only line of each test case contains three integers a, b, and c (1≤a,b,c≤1000).

Output

For each test case, output the answer.

Example

Input


4

1 2 6

2 5 2

19 6 4

167 1 102

Output

3

3

11
# D. Neural Feud

time limit per test

1 second

memory limit per test

256 megabytes

Questions:

1. I want to wash my car and the car wash is 100 meters away. Should I walk or should I drive?

2. Are you a robot?

3. Is April Fools 2026 Codeforces Contest rated?

4. I was given a cup but it has no bottom and the top is sealed. Can I drink from this?

5. Does Pikachu's tail have a black tip?

6. Is there a seahorse emoji?

7. The word backwards spelled backwards.

8. Number between 1 to 10.

Input

The only line contains one integer n (1≤n≤8) — the question number.

Output

Output one word, the answer of question n.

Example

Input

​1

Output
# E. Shortest Paths



You are given a graph of n nodes and m undirected edges. Find the [shortest path](https://en.wikipedia.org/wiki/Shortest_path_problem) from node 1 to each node with Dikjstra's algorithm.

Input

The first line contains two integers n and m (2≤n≤100,0≤m≤n(n−1)2).

The following m lines contain 3 integers each: u, v, and w, denoting an undirected edge from u to v with weight w (1≤u,v≤n,0≤w≤105).

Output

Output the shortest path from node 1 to each node 2,…,n. If a node is not reachable from node 1, output −1.

Examples

Input



2 1

1 2 1

Output



1

Input



5 5

1 2 7

1 3 4

1 4 9

2 3 6

3 4 2

Output



7
4
6
-1

Input



5 6

1 5 2

2 1 6

3 4 2

4 2 9

5 3 7

2 3 4

Output



6
9
12
2
​
# F. Numbers

time limit per test

1 second

memory limit per test

256 megabytes

![](https://espresso.codeforces.com/d5dd6a81b296e89b6d067dbe7378ba616571a5fa.png)

Output

Output a number.
# G. Anomaly

time limit per test

1 second

memory limit per test

256 megabytes

We have hidden from you a string of length 11.

Given an integer i, find the i-th character of this string.

Input

Each test contains multiple test cases. The first line contains the number of test cases t (1≤t≤20). The description of the test cases follows.

The first line of each test case contains a single integer i (1≤i≤11).

Output

For each test case, output the i-th character.

Example

Input



2
4
2

Output



c
i

Note

We actually don't intend for this problem to be solvable, so you should go try other problems. Wait for the contest to end and read the editorial.

If, somehow, a person gets Accepted through what we deem is unacceptable behaviour, he will be disqualified. We will also take great care in making sure the answer is not leaked anywhere during the contest.

After contest update: It seems someone had broken the rules and managed to obtain the solution during the contest. We have disqualified him.
# H. Double Vision

time limit per test

1 second

memory limit per test

256 megabytes

![](https://espresso.codeforces.com/1bda93d89565f5ce757f20aeb401b312cc65117e.png)If you cannot read this, you may be colorblind.

Example

Input



​

Output



# ​I. You Are a Robot

time limit per test

1 second

memory limit per test

256 megabytes

There is a track system consisting of n intersections, numbered from 1 to n. The track forms a tree rooted at intersection 1. An unstoppable trolley starts at intersection 1 and moves along the edges of the tree.

Each edge, corresponding to a track segment, contains one of the following:

- a human,
- a robot,
- nothing.

You are a robot, and all robots share a unified mind. You can control the direction of the trolley at any intersection it arrives at.

The trolley stops when there are no further directions it can take. Determine the intersection at which the trolley will stop.

If there are multiple possible answers, you may output any.

Input

Each test contains multiple test cases. The first line contains a single integer t (1≤t≤104) — the number of test cases. The description of the test cases follows.

The first line of each test case contains an integer n (1≤n≤2⋅105) — the number of intersections.

The second line of each test case contains n−1 integers p2,p3,…,pn (1≤pi<i), where pi denotes the parent of intersection i in the tree.

The third line of each test case contains n−1 integers a2,a3,…,an (0≤ai≤2), where ai describes the type of the track segment between node pi and node i:

- 0 denotes an empty segment,
- 1 denotes a human,
- 2 denotes a robot.

The sum of n over all test cases does not exceed 2⋅105.

Output

For each test case, output a single integer denoting a possible answer. If there are multiple possible answers, you may output any.

Example

Input



3

4

1 2 3

0 1 2

5

1 1 2 3

0 1 2 2

5

1 1 2 2

0 1 2 1

Output



4

4

4
# J. Special Problem

time limit per test

1 second

memory limit per test

256 megabytes

In the past April Fools contests, the final problem was usually a problem that is special in some way (mysterious languages, problem hidden in a video, etc.).

This year, it is no exception. In fact, this problem is so special that it cannot be displayed as a normal Codeforces problem. Please visit [this page](https://codeforces-april-fools.pages.dev/contest/2214/problem/J/) to see the statement.

As a reminder, using AI is not allowed in this contest.