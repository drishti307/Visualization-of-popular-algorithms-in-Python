# Visualisation of Greedy BFS using networkx library

### Greedy Best First Search ###

Best-first search is a search algorithm which explores a graph by expanding the most promising node chosen according to a specified rule. A greedy algorithm is one that chooses the best-looking option at each step. Hence, greedy best-first search algorithm combines the features of both mentioned above. It is known to be moving towards the direction of the target, in each step. (PS: There is no visiting back in path, as it is Greedy)

#### Heuristic function

Greedy BFS uses heuristics to the pick the "best" node.

A heuristic is an approximate measure of how close you are to the target. In short, h can be any function at all. We will require only that h(n) = 0 if n is a goal.

#### BFS v/s Greedy BFS

BFS expands the most promising node first(by looking at it's proximity to the source node).Hence, the solution is thorough. It might have to return back in path if a dead end is reached.
Whereas, Greedy BFS uses heuristics to prioritize nodes closer to target. Hence, the solution is faster(but not necessarily optimal). There is no returning back in the path.

Often with large data sets, search algorithms could get computationally expensive with thorough approaches. Hence, we resort to approximation algorithms like Greedy BFS.

### Greedy BFS Algorithm

Heuristic functions are clearly problem-specific.

Let us understand this better through an example. 

Source: Artificial Intelligence A Modern Approach
        by Stuart J. Russell and Peter Norvig 

Given here is the map of Romania with cities and distance between them. We need to find the shortest route from Arad to Bucharest. 

The heurestics that we are using here is the straight-line distance from the city to the goal(Here, Bucharest). Note that, this straight line distance is obtained only by knowing the map coordinates of the 2 cities. 


#### Input

Input is taken from the file 
```
input.txt
```

Each line in the input is of the form 
```
city1 city2 dist
```
It denotes each element of the adjacency list. That is, dist is the distance between city1 and city2. An undireced graph is drawn depicting the map of Romania.
Starting city: Arad
Goal city: Bucharest

Heuristics is loaded from the file
```
heuristics.txt
```
Each line is of the form
```
city h
```
'h' stands for the heuristics value(here, the straight line distnace) from the city 'city' to goal city(here, Bucharest)

Working: 

Starting from source city, we choose the next city which is the closest to the Goal city amongst all it's neighbours(based on the heuristics function). We terminate, once we've reached the goal city.

Here, Arad is the starting city. The first node to be expanded from Arad will be Sibiu, because it is closer to Bucharest than either Zerind or Timisoara. The next node to be expanded will be Fagaras, because it is closest. Fagaras in turn generates Bucharest, which is the goal.