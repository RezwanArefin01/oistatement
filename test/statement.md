# Powerful Tree
Alice has found a strange rooted tree on $n$ vertices where each vertex contains a certain value. The vertices are numbered from $1$ to $n$ and the root is numbered $1$. Vertex $i$ contains the integer value $a_i$. She decided to do an experiment on it via the following process.

* Some definitions first. A vertex $u$ is an **ancestor** a vertex $v$ if and only if $u$ belongs to the path from the vertex $v$ to the root. In particular, a vertex is $u$ an ancestor of itself. The **subtree** of a vertex $u$ is the set of vertices $v$ such that $u$ is an ancestor of $v$.
* Alice chooses a set $S$ of vertices from the tree that satisfies the following condition: for any two different vertices $u, v$ in $S$ &ndash; $u$ is not an ancestor of $v$, and $v$ is not an ancestor of $u$.
* Then Alice removes the subtrees of each vertex in $S$ from the tree.
* Finally, Alice adds up the values at all the remaining vertices in the tree and then computes the $k$-th power of the sum. This is the result of her experiment.

The problem is, Alice is too lazy to do all that. So she asks for your help. You need to consider all different possible ways that Alice can run her experiment, and then tell her the sum of results of all those experiments. We don’t want stuff to get too large, so it would suffice to print the value **modulo** $10^9 + 7$.

Two ways are considered different if and only if the set $S$ of vertices chosen for the experiment are different. Notice that order of vertices in the set doesn’t matter, and the same vertex cannot appear twice in the set.

## Input
* The first line of input contains two space separated integers $n$ and $k$, the number of vertices in the tree and the power used in the experiment.
* The second line contains $n$ space separated integers $a_1,\, a_2,\, \ldots,\, a_n$ &ndash; the values on vertices.
* Each of the following $n - 1$ lines contains two different integers $u$ and $v$, meaning there’s an edge between the vertices $u$ and $v$. This description of edges constitute a tree on $n$ vertices.

## Output
On a single line, print the sum of results of all different possible experiments on the tree, modulo $10^9+7$.

## Constraints
* $1 \leq n \leq 1000$. 
* $1 \leq k \leq 100$. 
* $1 \leq u, v \leq n$. 
* $1 \leq a_i \leq 10^9$. 

## Subtasks 
1. (9 points): there's an edge between vertices $i$ and $i+1$ for all $1 \leq i < n$. 
1. (9 points): $1 \leq n \leq 10$, $1 \leq k \leq 2$. 
1. (11 points): $1 \leq n \leq 100$, $k = 0$. 
1. (17 points): $1 \leq n \leq 100$, $k = 1$. 
1. (19 points): $1 \leq n \leq 500$, $k = 2$. 
1. (35 points): no further constraints. 


## Examples
### Example 1
For the input:
```
3 2
1 2 3
1 2 
2 3
```
The correct output is: 
```
46
```
Here the tree is a chain, so we can choose atmost one vertex. So, the desired answer is $0^2 + 1^2 + (1 + 2)^2 + (1 + 2 + 3)^2 = 46$, if we choose to select $\lbrace 1\rbrace, \lbrace 2\rbrace, \lbrace 3\rbrace, \lbrace \rbrace$ as $S$ respectively. 

### Example 2
For the input:
```
3 0 
1 2 3
1 2 
1 3
```
The correct output is: 
```
5
```
The valid choises for $S$ in this case are $\lbrace \rbrace, \lbrace 1\rbrace, \lbrace 2\rbrace, \lbrace 3\rbrace, \lbrace 1, 3\rbrace$ each of which contributes 1 to the sum, since the exponent is $k = 0$. Thus the answer is $5$. Note that we conisder the whole tree and the empty tree, and we consider $0^0$ to be $1$.
