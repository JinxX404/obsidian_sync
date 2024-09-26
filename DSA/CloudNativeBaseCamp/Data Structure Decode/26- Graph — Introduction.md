---
share_link: https://share.note.sx/7necq3o1#ff9aat6WC5W3gnERt/dVmSQSY80sMip0nX3mzGOYv20
share_updated: 2024-09-24T17:48:30+03:00
---
****Graph Data Structure**** is a collection of ****nodes**** connected by ****edges****. It’s used to represent relationships between different entities. ****Graph algorithms**** are methods used to manipulate and analyze graphs.

## What is Graph Data Structure?

Graph is a non-linear data structure consisting of vertices and edges. The vertices are sometimes also referred to as nodes and the edges are lines or arcs that connect any two nodes in the graph. More formally a [Graph](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/) is composed of a set of vertices( ****V**** ) and a set of edges( ****E**** ). The graph is denoted by ****G(V, E).****

Graph data structures are a powerful tool for representing and analyzing complex relationships between objects or entities. They are particularly useful in fields such as social network analysis, recommendation systems, and computer networks. In the field of sports data science, graph data structures can be used to analyze and understand the dynamics of team performance and player interactions on the field.

داتا ستراكشر غير خطي بيتكون من vertices و edges 
![[Pasted image 20240924151625.png]]
الvertices هي الentites دي

الي بيربط الvertices مع بعضها هو الedges 

![[Pasted image 20240924151728.png]]


## Components of a Graph:

- ****Vertices:**** Vertices are the fundamental units of the graph. Sometimes, vertices are also known as vertex or nodes. Every node/vertex can be labeled or unlabeled.
- ****Edges:**** Edges are drawn or used to connect two nodes of the graph. It can be ordered pair of nodes in a directed graph. Edges can connect any two nodes in any possible way. There are no rules. Sometimes, edges are also known as arcs. Every edge can be labelled/unlabelled.



## Operations on Graphs:

- Insertion of Nodes/Edges in the graph – Insert a node into the graph.
- Deletion of Nodes/Edges in the graph – Delete a node from the graph.
- Searching on Graphs – Search an entity in the graph.
- Traversal of Graphs – Traversing all the nodes in the graph.
- Shortest Paths : From a source to a destination, a source to all other nodes and between all pairs.
- Minimum Spanning Tree : In a weighted, connected undirected graph, finding the minimum weight edges to connect all.

## Types Of Graphs:

1. Null Graph:
![[Pasted image 20240924152258.png]]
عباره عن nodes من غير edges 
-A **null graph** is a type of graph in which there are **no edges** between any vertices. In other words, it’s a graph that has **only isolated nodes** (vertices) without any connections between them.
 
-A null graph can also be referred to as an edgeless graph, an isolated graph, or a discrete graph.

-A null graph with n vertices is a disconnected graph consisting of n components. Each component consists of one vertex and no edge.


- **Vertices**: It can have any number of vertices (including 0).
- **Edges**: It has **zero edges**.
-Usage:
- **Theoretical cases**: It's often used in graph theory as a **base case** or **starting point** for certain problems. Since it's the simplest possible graph, it helps in proofs or when defining certain properties.
- **Modeling disconnected components**: In practical situations, it can model systems or networks where entities (vertices) exist but have no relationships (edges) yet. For example, **users in a social network who haven't made any friends yet.**

2. Directed Graph:
![[Pasted image 20240924154046.png]]
A graph in which edges have a direction, i.e., the edges have arrows indicating the direction of traversal. Example: A web page graph where links between pages are directional.



3. Undirected Graph:
![[Pasted image 20240924154509.png]]
A graph in which edges have no direction, i.e., the edges do not have arrows indicating the direction of traversal. Example: A social network graph where friendships are not directional.
ملهاش اتجاهات ف نعتبر انها رايح جاي 
ال1 يقدر يوصل ل2 والعكس


4. Connected Graph  
![[Pasted image 20240924154744.png]]
لو بدات من اي نقطه اقدر اوصل لاي بوينت تانيه حتي لو مش بشكل مباشر 
Graph G is said to be connected if any pair of vertices (Vi, Vj) of a graph G is reachable from one another. Or a graph is said to be connected if there exists at least one path between each and every pair of vertices in graph G, otherwise, it is disconnected.

5. Disconnected Graph 
![[Pasted image 20240924154829.png]]
ممكن نعتبره اكتر من جراف فبعض وممكن اي نقطه متقدرش توصل لكل النقط الي فالجراف سواء بشكل مباشر او غير مباشر

6. Complete Graph 
![[Pasted image 20240924160236.png]]
كل بوينت متصله بباقي البوينتس بشكل مباشر 
يعني كل فيرتكس طالع منها عدد edges بيساوي no of vertex - 1

A graph in which each vertex is connected to every other vertex. Example: A tournament graph where every player plays against every other player.

7. Pseudo Graph
![[Pasted image 20240924160523.png]]
جراف بيتكون من خاصيتين parallel edge(multiple edges) + self loop
ما بين 1 و 4 طريقين حققت الخاصيه الاولي parallel edge 
وفي 2 حققت خاصيه الself loop (طريق بينها وبين نفسها)

A graph G with a self-loop and some multiple edges is called a pseudo graph. A pseudograph is a type of graph that allows for the existence of self-loops (edges that connect a vertex to itself) and multiple edges (more than one edge connecting two vertices). In contrast, a simple graph is a graph that does not allow for loops or multiple edges.

8. Weighted Graphs:
A graph in which edges have weights or costs associated with them. Example: A road network graph where the weights can represent the distance between two cities.

9. Unweighted Graphs: 
A graph in which edges have no weights or costs associated with them. Example: A social network graph where the edges represent friendships.

10. Multi Graph:
Any graph which contains some parallel edges but doesn’t contain any self-loop is called a multigraph. For example a Road Map.

## Representation of Graphs:

الجراف هو رسمه وعلشان اطبق عليها الجوريزمات ف لازم اخزنها في داتا ستراكشرز اقدر اخزنها 
اشهر طريقتين Adjacency Matrix و Adjacency List 

#### 1. Adjacency Matrix

 بنخزن فيها الجراف ك 2d array 
 ![[Pasted image 20240924162247.png]]
 بنحط الvertices ك columns , rows 
 بنقراها من الrow لل col 
 لو فيه ريلايشن بنحط 1 لو مفيش بنحط 0 
 لو weighted graph بنحط الlabels الي بتعبر عن العلاقه مكان ال0 1 
 يعني من A(row) ل B(col) فيه 1 معناها انه فيه علاقه من A ل B (فيه بينهم edge)


![[Pasted image 20240924162858.png]]
في حالة ال undirected graph الداتا بتتضاعف 
لان كل فيرتكس ليها علاقه مع الي قبلها


- The size of the matrix is determined by the number of vertices (or nodes) in a graph.
- The edges in the graph are represented as values in the matrix. In case of unweighted graphs, the values are 0 or 1. In case of weighted graphs, the values are weights of the edges if edges are present, else 0.
- If the graph has few edges, the matrix will be sparse.



How to build an Adjacency Matrix:

It is very easy and simple to construct an adjacency matrix for a graph there are certain steps given below that you need to follow:

- Create an ****n x n**** matrix where ****n**** is the number of vertices in the graph.
- Initialize all elements to 0.
- For each edge (u, v) in the graph, if the graph is undirected mark a\[u]\[v] and a\[v]\[u] as 1, and if the edge is directed from ****u**** to ****v****, mark a\[u]\[v] as the 1. (Cells are filled with edge weight if the graph is weighted)

Applications of the Adjacency Matrix:

- [Graph algorithms:](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/) Many graph algorithms like [Dijkstra’s algorithm](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/), [Floyd-Warshall algorithm](https://www.geeksforgeeks.org/floyd-warshall-algorithm-dp-16/), and [Kruskal’s algorithm](https://www.geeksforgeeks.org/kruskals-algorithm-simple-implementation-for-adjacency-matrix/) use adjacency matrices to represent graphs.
- [Image processing](https://www.geeksforgeeks.org/digital-image-processing-basics/)****:**** Adjacency matrices are used in image processing to represent the adjacency relationship between pixels in an image.
- [Finding the shortest path between two nodes:](https://www.geeksforgeeks.org/shortest-path-unweighted-graph/) By performing matrix multiplication on the adjacency matrix, one can find the shortest path between any two nodes in a graph. 

Advantages of using Adjacency Matrix:

- An adjacency matrix is simple and easy to understand.
- Adding or removing edges from a graph is quick and easy.
- It allows constant time access to any edge in the graph.
- Time complexity for checking if there is an edge between two nodes: `O(1)` (constant time).

Disadvantages of using Adjacency Matrix:

- It is inefficient in terms of space utilization for sparse graphs because it takes up O(N^2) space.
- Computing all neighbors of a vertex takes O(N) time.

When to use it:

- Graphs with dense connections (lots of edges).
- When you need **fast access** to check if an edge exists between two nodes (constant-time edge lookup).


#### 2. Adjacency List 
عباره عن Array of Linked Lists
كل عنصر من الاراي هو vertex اساسيه فالجراف هنعبر عنها 
وكل لينكد ليست بعدها بتشاور علي vertex هي رايحالها
![[Pasted image 20240924163321.png]]

يعني هنا A هيكون مرتبط بيها كل الي هي بتشاور عليهم 
عند A فيه بعدها B بتشاور علي C وده مش معناه ان فيه علاقه بين B , C 

كل عنصر فالاراي هيكون مرتبط بيه كل العناصر الي هو مرتبط بيها (مش هيعبر عن علاقات كل عنصر من دول ببعضهم)


- The size of the matrix is determined by the number of nodes in the network.
- The number of graph edges is easily computed.
- The adjacency list is a [****jagged array****](https://www.geeksforgeeks.org/jagged-arrays-in-cpp/).

How to build an Adjacency List?

It is very easy and simple to construct an adjacency list for a graph there are certain steps given below that you need to follow:

- Create an array of linked lists of size ****N****, where N is the number of vertices in the graph.
- Create a linked list of adjacent vertices for each vertex in the graph.
- For each edge ****(u, v)**** in the graph, add ****v**** to the linked list of ****u****, and add ****u**** to the linked list of ****v**** if the graph is undirected otherwise add ****v**** to the list of ****u**** if it is directed from ****u**** to ****v****. (In case of weighted graphs store the weight along with the connections).

Applications of the Adjacency List:

- [Graph algorithms](https://www.geeksforgeeks.org/introduction-to-graphs-data-structure-and-algorithm-tutorials/): Many graph algorithms like [Dijkstra’s algorithm](https://www.geeksforgeeks.org/introduction-to-dijkstras-shortest-path-algorithm/), [Breadth First Search](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/), and [Depth First Search](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/) use adjacency lists to represent graphs.
- [Image Processing](https://www.geeksforgeeks.org/digital-image-processing-basics/): Adjacency lists can be used to represent the adjacency relationships between pixels in an image.
- [Game Development](https://www.geeksforgeeks.org/how-to-get-started-with-game-development/): These lists can be used to store information about the connections between different areas or levels the game developers use graphs to represent game maps or levels.

Advantages of using an Adjacency list:

- An adjacency list is simple and easy to understand.
- Adding or removing edges from a graph is quick and easy.
- Space-efficient for sparse graphs: Only stores edges that actually exist.
- Efficient for exploring neighbors: Iterating through neighbors is fast because only actual edges are stored.

Disadvantages of using an Adjacency list:

- In adjacency lists accessing the edges can take longer than the adjacency matrix.
- It requires more memory than the adjacency matrix for dense graphs.
* Slower edge lookup: To check if an edge exists between two vertices, you may need to iterate through the list, making it `O(V)` in the worst case.

When to use it:
- **Graphs with sparse connections (few edges)**.
- When you need to **iterate over all the neighbors** of a node efficiently.
-----

- **Space complexity**: `O(V + E)`, where `V` is the number of vertices, and `E` is the number of edges.
- **Time complexity for checking if an edge exists**: `O(V)` (you need to scan through the list of neighbors).
- **Time complexity to find neighbors of a node**: `O(k)`, where `k` is the number of neighbors of the node (usually much less than `V`).

 **Adjacency Matrix vs Adjacency List Comparison Table**

|Aspect|**Adjacency Matrix**|**Adjacency List**|
|---|---|---|
|**Space Complexity**|`O(V^2)`|`O(V + E)`|
|**Best for**|**Dense graphs** (lots of edges)|**Sparse graphs** (few edges)|
|**Edge Lookup**|`O(1)`|`O(V)`|
|**Iterating over neighbors**|`O(V)`|`O(k)` (k = number of neighbors)|
|**Edge Insertion/Removal**|`O(1)`|`O(1)` (adding/removing edges)|
|**Memory Usage**|High|Low (for sparse graphs)|
|**Common Use Cases**|**Dense networks** like social networks|**Roadmaps**, **friendship networks**|

**Dense Graph vs. Sparse Graph**

**Dense graphs** and **sparse graphs** are terms used to describe the **number of edges** in a graph relative to the number of vertices (nodes). These concepts are important when choosing the right data structure (like adjacency matrix or adjacency list) and algorithms for solving problems efficiently.


**1. Dense Graph**

**Definition**:

A **dense graph** is a graph in which there are a **lot of edges** between the vertices. In mathematical terms, a dense graph has **close to the maximum number of edges**.

- For an **undirected graph**, the **maximum number of edges** is V(V−1)/2​, where V is the number of vertices.
- For a **directed graph**, the **maximum number of edges** is V(V−1)

A graph is considered **dense** if it has **close to this maximum number of edges**.

**Example**:

For a graph with 5 vertices, the maximum number of edges in an undirected graph would be:

5(5−1)2=10 edges

If a graph has, say, 8 or 9 edges out of these 10, it would be considered **dense**.

**Properties**:

- **Number of edges**: Close to V^2 (almost all possible connections are present).
- **Space complexity**: Dense graphs typically use more memory because of the large number of edges.
    - **Adjacency Matrix** is usually better for storing dense graphs because you can quickly check if an edge exists.

**Common Use Cases**:

- **Social Networks**: Large networks like Facebook or LinkedIn, where users are connected to many other users.
- **Fully Connected Networks**: In networking, a fully connected mesh topology is a dense graph where every node is directly connected to every other node.

**Why it Matters**:

- In a dense graph, algorithms that iterate over all edges will be slower because there are more edges to process.
- Memory usage is higher when storing a dense graph.

---

**2. Sparse Graph**

**Definition**:

A **sparse graph** is a graph in which there are **very few edges** relative to the number of vertices. In a sparse graph, most vertices are not directly connected to many others.

A graph is typically called **sparse** if it has **far fewer than the maximum number of possible edges**.

**Example**:

For a graph with 5 vertices, the maximum number of edges is 10, but if the graph only has 3 edges, it would be considered **sparse**.

**Properties**:

- **Number of edges**: Closer to V, meaning far fewer than the maximum possible number.
- **Space complexity**: Sparse graphs are more memory efficient.
    - **Adjacency List** is typically used for storing sparse graphs, as it only stores the existing edges and avoids wasting memory on non-existent edges.

#### **Common Use Cases**:

- **Road Networks**: A real-world road network where each city (vertex) is connected to only a few neighboring cities.
- **Tree-like Structures**: A tree is a type of sparse graph where there are exactly V−1V - 1V−1 edges for V nodes.

#### **Why it Matters**:

- In a sparse graph, algorithms that process edges (like DFS, BFS) tend to run faster since there are fewer edges to explore.
- Memory usage is lower because only existing edges are stored.

---

**Comparison Table**

|Aspect|**Dense Graph**|**Sparse Graph**|
|---|---|---|
|**Number of Edges**|Close to V2V^2V2 (almost every pair of nodes is connected)|Closer to VVV (most pairs of nodes are not connected)|
|**Space Complexity**|Higher (uses more memory, especially with an adjacency matrix)|Lower (more efficient with adjacency lists)|
|**Edge Lookup**|Fast with **Adjacency Matrix** (`O(1)` edge check)|Better with **Adjacency List** (`O(k)` neighbors check)|
|**Example Graphs**|**Social Networks**, **fully connected networks**, **mesh topologies**|**Road Networks**, **tree-like structures**, **friendship networks**|
|**Memory Usage**|High (due to many edges)|Low (due to fewer edges)|
|**Algorithms**|Some algorithms may take longer due to the large number of edges|Algorithms can run faster as there are fewer edges to process|


## Real-World Usage 

1. **Social Networks**

- **Facebook** or **LinkedIn**: People are vertices, and friendships or connections are edges. You can use graphs to find common friends, recommend new connections, or detect communities.
- **Twitter** or **Instagram**: Here, the graph might be directed, meaning one user follows another but not necessarily the other way around.

2. **Google Maps and GPS Navigation**

- Cities or locations are vertices, and roads are edges. The graph helps in finding the **shortest path** between two points (like how Google Maps gives you directions), using algorithms like **Dijkstra** or __A_ search_*.

3. **Webpage Ranking (Google PageRank)**

- The internet can be modeled as a graph where each **webpage is a vertex** and each hyperlink between pages is a directed edge. Google's PageRank algorithm uses graphs to rank pages based on their importance by looking at the links between them.

4. **Recommendation Systems**

- Graphs are used in **recommendation systems** like Netflix or Amazon. Users and items (like movies or products) are vertices, and the edges represent interactions (such as ratings or purchases). This helps in recommending similar items based on what other users with similar tastes have interacted with.

5. **Network Communication**

- The internet or any **computer network** is a graph where **devices (like routers, switches)** are vertices, and the physical or virtual **connections (wires, wireless links)** are edges. Graph algorithms help optimize data transfer routes, detect network failures, etc.

6. **Biological Networks**

- **Genes, proteins, and cells** can be modeled as vertices in graphs, with interactions between them (such as protein-protein interactions) being the edges. This is useful in **bioinformatics** for understanding biological processes, disease spread, or drug design.

7. **Flight Networks**

- Airports are vertices, and **flights between them are edges**. Airlines use graphs to plan routes, optimize schedules, or handle disruptions by finding alternate paths (e.g., connecting flights).

8. **Electrical Circuits**

- **Electrical components** (like resistors, capacitors, etc.) are vertices, and the connections between them (wires) are edges. This helps analyze how current flows through circuits.

9. **Game Development (Pathfinding)**

- In games like **chess** or **real-time strategy games**, the board or the game world can be modeled as a graph where each position is a vertex and valid moves are edges. Graph algorithms like **BFS** or **DFS** help characters or NPCs navigate through the game environment.

10. **Task Scheduling (Dependency Graphs)**

- In projects or task scheduling, tasks can be vertices, and dependencies between them are directed edges. This is useful in building schedules, detecting bottlenecks, or ensuring tasks are completed in the correct order (like in **build systems** or **software development pipelines**).

11. **Artificial Intelligence**

- Graphs are used in **AI and machine learning**, especially in **knowledge graphs** where entities (concepts, objects, etc.) are vertices, and relationships between them (is-a, part-of, etc.) are edges. This helps with understanding context or making better decisions.

12. **Blockchain**

- Blockchain networks can be viewed as graphs where **nodes** (computers participating in the blockchain) are vertices, and the **transactions or relationships** between them are edges. Graphs are used to analyze and maintain the decentralized network efficiently.

13. **Search Engines**

- **Crawling the web** is another graph problem. A web crawler visits web pages, which are vertices, and follows links (edges) to discover and index new content.

14. **Fraud Detection**

- Graphs help in **detecting fraud** in financial systems by representing users as vertices and transactions between them as edges. Unusual patterns in the graph (like large clusters or frequent transfers) can indicate fraud or money laundering.

15. **Robot Navigation**

- Robots use graphs to navigate through physical spaces. The environment is represented as a graph, where nodes represent locations and edges represent possible movements. Algorithms like **A*** are used to find the optimal path from one point to another.
## Advantages and Disadvantages 

Advantages of Graph Data Structure:
- Graph Data Structure used to represent a wide range of relationships as we do not have any restrictions like previous data structures (Tree cannot have loops and have to be hierarchical. Arrays, Linked List, etc are linear)
- They can be used to model and solve a wide range of problems, including pathfinding, data clustering, network analysis, and machine learning.
- Any real world problem where we certain set of items and relations between them can be easily modeled as a graph and a lot of standard graph algorithms like BFS, DFS, Spanning Tree, Shortest Path, Topological Sorting and Strongly Connected
- Graph Data Structure can be used to represent complex data structures in a simple and intuitive way, making them easier to understand and analyze.

Disadvantages of Graph Data Structure:
- Creating and manipulating graphs can be computationally expensive, especially for very large or complex graphs.
- Graph algorithms can be difficult to design and implement correctly, and can be prone to bugs and errors.
- Graph Data Structure can be difficult to visualize and analyze, especially for very large or complex graphs, which can make it challenging to extract meaningful insights from the data.