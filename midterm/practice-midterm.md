# University of Excellence
## Midterm COMP 4802
## March 5, 2025

* All questions must be answered on the scantron sheet.
* Write your name and student number on the scantron sheet.
* You do not have to hand in this examination paper.
* Calculators are allowed.

**Marking scheme**: Each of the 17 questions is worth 1 mark.

### Some useful facts:
1. 1 + 2 + 3 + · · · + n = n(n + 1)/2.
2. For any real number x > 0, x = 2^(log x).
3. For any real number x ≠ 1 and any integer k ≥ 1,
   1 + x + x^2 + · · · + x^(k−1) = (x^k − 1)/(x − 1).
4. For any real number 0 < α < 1,
   ∑^∞_{i=0} α^i = 1/(1 − α).

**Master Theorem**:
1. Let a ≥ 1, b > 1, d ≥ 0, and
   T(n) = {
     1 if n = 1,
     a · T(n/b) + Θ(n^d) if n ≥ 2.
   }
2. If d > log_b a, then T(n) = Θ(n^d).
3. If d = log_b a, then T(n) = Θ(n^d log n).
4. If d < log_b a, then T(n) = Θ(n^(log_b a)).

### Questions:

1. Recall that N = {1, 2, 3, . . .} denotes the set of all positive integers. Let f : N → N and g : N → N be two functions such that f(n) = Ω(g(n)). Is it true that, for any two such functions f and g, log(f(n)) = Ω(log(g(n)))?  
   (a) This is true.   
   **(b) This is not true.** 

2. Consider the recurrence
   T(n) = 2T(n/4) + √n.
   Which of the following is true?  
   (a) T(n) = Θ(√n).  
   **(b) T(n) = Θ(√n log n).**
   (c) T(n) = Θ(n^(1/2)).  
   **(d) T(n) = Θ(n^(1/2) log n).**

3. Consider the recurrence
   T(n) = 3T(n/4) + n log n.
   Which of the following is true?  
   (a) T(n) = Θ(n log n).  
   (b) T(n) = Θ(n^(log_4 3)).  
   (c) T(n) = Θ(n^(log_4 3) log n).  
   (d) T(n) = Θ(n log^2 n).  

4. Consider the following recursive algorithm Multiply(a, b), which takes as input two integers a ≥ 1 and b ≥ 1, and returns a × b:
   ```
   Algorithm Multiply(a, b):
     if b = 1
       then return a
     else if b is even
       then return Multiply(2*a, b/2)
     else 
       return a + Multiply(2*a, (b-1)/2)
     endif
   ```
   Assume that each addition, multiplication, and division in this algorithm takes O(1) time. What is the running time of algorithm Multiply(a, b)?  
   (a) T(n) = Θ(log a).  
   (b) T(n) = Θ(log b).  
   (c) T(n) = Θ(log(a+b)).  
   (d) T(n) = Θ(log(a*b)).  

5. You are given n unsorted arrays A_1, A_2, ..., A_n, each containing n elements. You want to merge them into a single sorted array of length n^2. Consider the following approach:
   * First sort each array A_i individually using merge sort.
   * Then use the standard merge algorithm repeatedly: first merge A_1 and A_2, then merge the result with A_3, and so on.
   
   What is the running time of this algorithm?  
   (a) Θ(n^2 log n).  
   (b) Θ(n^3).  
   (c) Θ(n^2 log n^2).  
   (d) Θ(n^3 log n).  

6. You are given n sorted arrays A_1, A_2, ..., A_n, each containing n elements. Consider the following divide-and-conquer algorithm MergeArrays that merges these arrays into one single sorted array of length n^2:
   
   Base case: If n = 1, return the single array.
   
   Non-base case: If n ≥ 2:
   * Recursively merge the first n/2 arrays into a sorted array B_1.
   * Recursively merge the last n/2 arrays into a sorted array B_2.
   * Merge B_1 and B_2 using the standard merge algorithm.
   
   Let T(n) denote the running time of this algorithm. Which of the following is correct?  
   (a) T(n) = 2T(n/2) + Θ(n^2).  
   (b) T(n) = 2T(n/2) + Θ(n).  
   (c) T(n) = T(n/2) + Θ(n^2).  
   (d) T(n) = T(n-1) + Θ(n).  

7. Professor Quickfingers has designed a new data structure that stores any sequence of numbers, and supports the following two operations:
   * Insert(x): Add the number x to the data structure. This operation takes Θ(log n) time, where n is the current number of elements.
   * ExtractMax: Delete, and return, the largest element stored in the data structure. This operation takes Θ(n^(1/3)) time, where n is the current number of elements.
   
   You use Professor Quickfingers' data structure (and nothing else) to design a sorting algorithm. What is the running time of this sorting algorithm on an input of n numbers?  
   (a) Θ(n log n).  
   (b) Θ(n^(4/3)).  
   (c) Θ(n^(5/3)).  
   (d) Θ(n^2).  

8. Let S be a set of n distinct numbers. Assume this set S is stored in a max-heap A[1...n]. How much time does it take to use this heap to find the second-largest number of S?  
   (a) Θ(1).  
   (b) Θ(log n).  
   (c) Θ(n).  
   (d) Θ(n log n).  

9. Let G = (V, E) be a directed graph. What is the maximum number of strongly connected components that this graph can have?  
   (a) |V|.  
   (b) |E|.  
   (c) |V| * |E|.  
   (d) 2^|V|.  

10. Let G = (V, E) be a connected undirected graph that is given using adjacency lists. You want to determine if G is bipartite. What is the running time of the fastest algorithm for this problem?  
    (a) Θ(|V|).  
    (b) Θ(|E|).  
    (c) Θ(|V| + |E|).  
    (d) Θ(|V| * |E|).  

11. Let G = (V, E) be an undirected graph. We say that a subset S ⊆ V is an independent set if no two vertices in S are adjacent. What is the running time of the fastest algorithm to determine if G has an independent set of size k?  
    (a) Θ(|V| + |E|).  
    (b) Θ(|V|^k).  
    (c) This problem is NP-hard.  
    (d) Θ(2^|V|).  

12. Let G = (V, E) be a directed graph, and assume that this graph is stored using adjacency lists. What is the running time of the fastest algorithm to determine if G contains a directed cycle?  
    (a) Θ(|V|).  
    (b) Θ(|V| + |E|).  
    (c) Θ(|V| * |E|).  
    (d) Θ(|V|^2).  

13. Let G = (V, E) be an undirected graph, and let s and t be two distinct vertices of V. What is the running time of the fastest algorithm that computes the length of the shortest path in G from s to t?  
    (a) Θ(|V|).  
    (b) Θ(|E|).  
    (c) Θ(|V| + |E|).  
    (d) Θ(|V| log |V| + |E|).  

14. Let G = (V, E) be a connected undirected graph. We run breadth-first search on G starting at a vertex s. Let T be the resulting BFS tree.
    Is the following true or false?
    For any vertex v in V, the path from s to v in T is a shortest path from s to v in G.  
    (a) True.  
    (b) False.  

15. Let G = (V, E) be a directed graph. We run depth-first search on G, i.e., algorithm DFS(G).
    Is the following true or false? 
    If the graph G has no back edges, then G is acyclic.  
    (a) True.  
    (b) False.  

16. Let G = (V, E) be a directed graph and, for each edge (u, v) in E, let wt(u, v) denote its non-negative weight. Let s be a source vertex. You want to find the shortest paths from s to all other vertices.
    What is the running time of Dijkstra's algorithm when implemented with a Fibonacci heap?  
    (a) Θ(|V| log |V| + |E|).  
    (b) Θ(|V|^2).  
    (c) Θ(|V|^2 log |V|).  
    (d) Θ(|V| + |E| log |V|).  

17. After this midterm, you go to a Data Science Club and run the following randomized algorithm CountingStars(n), which takes as input an integer n ≥ 1:
    ```
    Algorithm CountingStars(n):
      count = 0
      for i = 1 to n^2:
        choose a random integer j from {1, 2, ..., n}
        count = count + j
      return count
    ```
    What is the expected value of the return value of CountingStars(n)?  
    (a) Θ(n^2).  
    (b) Θ(n^3).  
    (c) Θ(n^4).  
    (d) Θ(n^(5/2)).  
