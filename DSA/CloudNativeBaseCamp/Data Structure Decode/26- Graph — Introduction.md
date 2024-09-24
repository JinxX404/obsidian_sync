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

8. ****Weighted Graphs:**** A graph in which edges have weights or costs associated with them. Example: A road network graph where the weights can represent the distance between two cities.
9. ****Unweighted Graph****s: A graph in which edges have no weights or costs associated with them. Example: A social network graph where the edges represent friendships.