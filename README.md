# PathFindingAlgorithmVisualizerPyhton
Using A* Path Finding Algorithm (visualizer), we can find the shortest path from Source to Destination and also in Optimal way. In this Project, I have implemented this algorithm with the help of python and for visualization part with the external python module/library namely "pygame", this module helps the user to interact with the program and in a fun way of learning. 
some functionality are: " c " - clear the board. " space " - space bar is used to start the program. " left click " - mouse left click will set the position respectively. " right click " - mouse right click will revert the position which is already set.

Read this Blog Before Proceedng  https://medium.com/omarelgabrys-blog/path-finding-algorithms-f65a8902eb40

A-star is a graph traversal and path finding/search algorithm, which is been used for its completeness, optimality and efficiency.

(informed search is namely to retrieve information stored within some data structure, or calculated in the search space of a problem domain, either with discrete or continuous values).

(Best-first search is a search algorithm which explores a graph by expanding the most promising node chosen according to a specified rule).

A * is an informed search algorithm or a best-first search, if we were given a start node and an end node, it will try to find the path between them in shortest time and minimum cost, which is optimal, in other words it searches shorter path first rather than longer path. For which it does maintain a tree of paths originating from the start node and extending those paths one node at a time until it reach the destination.

At each iteration, A* needs to determine which of its paths to extend. It does this based on the cost of the path which we travelled and an estimate of the cost required to travel to the destination node or which will lead us to the goal. 
	f (n) = g (n) + h (n) 
where n is the next node on the path, 
g(n) is the cost of the path from the start node to current node, 
h(n) is a heuristic function that estimates/guess the cost of the cheapest path from next node to the goal. 

A* terminates when the path reach to the goal or if there are no paths eligible to be travelled. The heuristic function is problem-specific. it never overestimates the actual cost to get to the goal, so that guarantees to return a least-cost path from start to goal.

firstly why A* algorithm? There are many path finding algorithms like breadth first search, depth first search, Dijkstra, Greedy, A*.
	BFS and DFS are blind search algorithms, which will try to find all possible ways to reach the destination from the start by iterating over and over.so this algorithm runs for O(V+E).

	But Dijkstra, Greedy, A* does a heuristic search, which means it is educated to guess the distance and move to the goal optimally. So its complexity will be in O(E log(V)). 
(in BFS, it moves to all of its child node at each level).
(in DFS, it moves to one of its child node and to child’s child node recursively).
(in Dijkstra, it finds the path by starting node to each node to reach the goal).
	O(E+V log(V))
(in Greedy, it finds the path based on shorted heuristic distance at next level).
	O(E log(V))
And A* is combination of Dijkstra and Greedy, it finds the distance from next node to destination node.
	O(logh*(V))

Programming Logic,
We have 2 list, open set and close set. Open set is the node that we are currently in or visiting and close set is that we haven’t visited the node yet but we’ll use it for calculation.

Algorithm,
1.Add start node to open set.
2.For all the neighbouring nodes, find the least cost F node.
3.Switch to close set,
	3.1.For all the adjacent node to current node.
	3.2.If the node is not reachable, ignore it else,
		3.2.1If the node is not in the open set, add it and calculate f, g, h.
		3.2.2If node is on open set, check if the path it offers is less than current path and change to it if it does so.
4.stop working when,
	4.1.you find the destination.
	4.2.you can’t find the destination going through all possible points.
