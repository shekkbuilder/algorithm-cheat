# Motivation

Links and short descriptions of beautiful problems in computer science.

The beauty of computer science lies mainly on:

- its huge usefulness
- a few theoretical questions with deep implications
- the endless race for *the* ultimate algorithm that solves each problem

## Sources

-   <https://en.wikipedia.org/wiki/List_of_algorithms>

    Large list of important algorithms ranged by category.

    Good place to look for cool algorithms.

## Applications

### Manipulate information for humans

- learn: websites, books
- have fun: games, music

Programs can help to:

- view: web browsers, PDF viewers
- edit: text editors, image editors
- transmit: web

### Solve models

See [this](https://github.com/cirosantilli/text/blob/1.1/src/tech.md).

## Theoretical questions

### P vs NP

<https://en.wikipedia.org/wiki/P_versus_NP_problem>

Easy to state, hard to prove.

Many other analogous questions like PSPACE vs NP.

### Undecidability

<http://en.wikipedia.org/wiki/Undecidable_problem>

Mysterious feeling: there are problems that you can state, but not solve in general.

### FPTAS

1/0 knapasack can be solved in polynomial time in $n$ and $\epsilon$
if solutions that are $1 - \epsion$ of the optimum are acceptable.

<http://en.wikipedia.org/wiki/FPTAS>

## Algorithms

This is a list of cool problems and algorithms that solve those problems.

It is cool to understand how the following calculations can be implemented:

-   factorial

-   Fibonacci series.

    Specially interesting to look at efficient different implementations and their efficienty:

    - simple recursive:               $O(2^n)$ time!

    - dynamic programming with array: $O(n)$ time, $O(n)$ memory.

    - dynamic programming storing border only: $O(n)$ time, $O(1)$ memory.

-   MCD, MCM.

-   Primality testing: given a number, is it prime or not?

    For a long time it was an open question if a polynomial algorithm existed.

    Note that the naive algorithm of trying division by every number below $\sqrt(n)$
    is polynomial on the value of $n$, but *not* on the number of digits of the input,
    which is what is considered in complexity analysis.

    The question was solved positively in 2002 by the [AKS primality tesst](https://en.wikipedia.org/wiki/AKS_primality_test).
    Before AKS, there were many algorithms which were either probabilistic,
    or dependent on the truth of unproven conjectures, at the time of their proposal,
    such as the Miller test which depends on the generalized Riemann hypothesis.

    Many variants of AKS were created, and one of them is known to run in $O(log^6(n))$.

-   Combinatorial optimization and satisfiability:

    -   Knapsack.

    -   [Coin problem](http://en.wikipedia.org/wiki/Coin_problem).

        A monetary system has 3 types of coins: 3, 5 and 7. What is the largest ammount that cannot be attained?

        NP-complete in the number of types of coins.

    -   [Change making problem](http://en.wikipedia.org/wiki/Change-making_problem).

        What is the smallest number of coins needed to make a given value exactly?

        NP-complete in the number of types of coins.

        Belongs to the knapsack family.

-   Sorting.

    Compare all the sorting algorithms! Which is the *best*?

-   Heaps: the search for the ultimate heap: <http://en.wikipedia.org/wiki/Heap_%28data_structure%29#Comparison_of_theoretic_bounds_for_variants>

-   Graph algorithms.

    -   BFS vs DFS. See queue vs stack duality of non recursive implementation.

    -   Single source shortest path:

        - [dijikstra](http://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) 1959 $O(|E| + |V| log |V|)$. Positive weights only.

        - [A*](http://en.wikipedia.org/wiki/A*_search_algorithm) 1968. Heuristic improvement over dijikstra if a distance function exists.

        - [bellman-ford](http://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm) 1965. $O(|V|^2 log |V|)$, but also accepts negative weights.

    -   All pairs shortest path:

        - [floyd warshall](http://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm) 1959 / 1962. $O(|V|^3)$, negative weights ok.

        - [johnson's algorithm](http://en.wikipedia.org/wiki/Johnson%27s_algorithm) 1977 $O( |V|^2 log |V| + |V||E|)$, therefore better than floyd marchal for sparse graphs. Negative weights ok.

    -   [Hamiltonian Path Problem](http://en.wikipedia.org/wiki/Hamiltonian_path). Is there a path that visits all vertices? NP-complete.

    -   [Traveling Salesman Problem](http://en.wikipedia.org/wiki/Travelling_salesman_problem). Edges have weights. Find shortest path that visits all vertexes. NP-hard.

    -   [Route Inspection Problem](http://en.wikipedia.org/wiki/Route_inspection_problem). Find the shortest path that covers all edges of an **undirected** graph, possibly passing more than once over the same edge. $O(n^3)$. If an [Eulerian Path](http://en.wikipedia.org/wiki/Eulerian_path) exists, it is the trivial solution.

        If the graph is mixed, NP-complete! Beautiful, small problem difference, huge complexity difference. aka Chinese Postman Problem.

    -   [Vehicle Routing Problem](http://en.wikipedia.org/wiki/Vehicle_routing_problem). Generalization of Route Inspection, but edges have one or more weights, and multiple constraints are possible.

    -   [Four Color Theorem](http://en.wikipedia.org/wiki/Four-color_theorem)

        You can color a map with 4 colors in a way that no two countries share a border with same color.

        Graph statement: every planar graph can be colored in a way that no two neighbours have the same color.

        Conjectured in 1852, proven in 1976.

        Proof uses a computer to check each 1936 base cases, first of its type.

        Proof for the 5 color case much easier and completed in 1890.

        Simple to state, hard to prove.

        Complexity of finding a coloring: $O(n^2)$.

    -   Self balancing search trees. RB-tree, AVL tree, B-tree.

        Allow searches, insertions and other operations in $O(log(n))$.

        A sorted array only allows $O(log(n))$ search, but not insertion.

-   Dynamic programming:

    -   [Maximum subarray problem](https://en.wikipedia.org/wiki/Maximum_subarray_problem).

        Solvable in $O(n)$.

    -   [Change-making problem](https://en.wikipedia.org/wiki/Change-making_problem).

        Solvable in $O(n log n)$.

-   [Tower of Hanoi](https://en.wikipedia.org/wiki/Tower_of_Hanoi).

    Cool graph visualization that becomes a Sierpinski triangle, and which make crystal clear:

    - uniqueness
    - length of the optimal path: $2^n - 1$. This path is simple to compute.

    Variations are also interesting:

    -   Go from any initial configuration to any final configuration.

        -   the graph shows that there can be only either 1 or 2 optimal paths.

        -   the original problem of moving all pegs from one configuration to another
            is the problem that takes the longest time possible.

            This time is also attained by any other problem on the opposite side of the sierpinski triangle.

            Any starting position on the interior will lead to shortesr optimal paths to anywhere.

        -   there is an explicit formula by Hinz and Chan Hat-Tung for the average optimal solution length
            if initial and states are chosen at random which is assymptotically: $466/885 * 2^n - 1/3 + o(1)$

    -   Any increase the number of pegs.

        For 4 pegs, the problem is known as *Reve's puzzle*.

        It is possible to do a brute-force solution by representing the problem as a graph and doing BFS, but this is of course exponential in memory and time.

        There is no polynomial algorithm proven to compute the solution although the Frame-Stewart algorithm is conjectured to do so.

        As a consequence, exact bounds for a given number of disks and pegs are unknown.

-   Pseudo random number generation.

-   Branch and bound with relaxation.

    Relaxation means to suppose the problem can have fractional solutions.

    It becomes then a continuous linear programming problem, and can therefore be solved in polynomial time.

    We know that the actual solution cannot be better than the relaxed one,
    since the relaxed solution has many more possibilities, so we can bound what is the best possible solution.

    This allows for more efficient cutting.

- [karp's 21 NP complete problems](http://en.wikipedia.org/wiki/Karp%27s_21_NP-complete_problems)

    Very famous list of NP complete problems you should know about.

- [string searching algorithms](https://en.wikipedia.org/wiki/String_searching_algorithm)

    Obvious practical applications.

    Let:

    - $p$ be the pattern length
    - $t$ be the text    length

    Naive algorithm does $O(pt)$ worst case.

    [Boyer–Moore](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_string_search_algorithm)
    does $O(t)$ worst case.

### Integer multiplication

-   Unknown sup of lower bounds.

-   Naive: $n^2$.

-   Karatsuba: <http://en.wikipedia.org/wiki/Karatsuba_algorithm>

    Multiplication in $O(n^{\log_{2}3})$.

-   Tom-cook.

    Generalization of Karatsuba.

    <http://en.wikipedia.org/wiki/Toom%E2%80%93Cook_multiplication>

    Algorithm family, hard to analyse, Toom-3 does $O(n^{\log_{3}5})$,
    about $O(n^{1.465})$

-   Schonhage–Strassen

    $O(log n log log n)$

    FFT based.

### Matrix multiplication

<http://en.wikipedia.org/wiki/Matrix_multiplication#Algorithms_for_efficient_matrix_multiplication>

Is there an $O(n^2)$ matrix multiplication algorithm?
If not, how fast can we get?

This is practically important because matrix multiplications
are done millions and millions of times
to approximate solutions to physical problems.

Naive school algorithm: $O(n^3)$.

First improvement: [1969 Strassen](http://en.wikipedia.org/wiki/Strassen_algorithm).
Easy to understand, and better in practice for large enough matrices.

Current best: [1987 Volker-Strassen](http://en.wikipedia.org/wiki/Coppersmith%E2%80%93Winograd_algorithm).
More complicated and not yet useful on practical matrix sizes found on current problems.

### Numerical analysis

These algorithms / problems may require analysis background to understand.

They are fun and important to implement solutions using computers.

-   Exponential.

-   Integration and derivation.

-   Taylor series.

-   Solve $f(x) = 0$:

    - divide by two
    - newtons method

-   Matrices.

-   FFT.

-   Differential equations: ordinary/partial.

-   Finite elements.