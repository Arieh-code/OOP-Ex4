# OOP - EX4: Gotta Catch Them All (in python)
<br /> 

![pokemon front pic](https://user-images.githubusercontent.com/68643157/148652118-8a62da58-9d86-4f2d-8efa-943ed2694220.jpg)

**Done by Arieh Norton and Leead Jacobowitz** 
  <br />
  
  ### In this assingment, we were challenged to create an algorithm to catch as many value Pokemons as possible. 
  
  

## The main idea of the code <br />

This is the final assignment, we are tasked to catch as many pokemnons as possible. The Pokemnons are spread around a directed weighted graph.
The Agents are spread on different nodes on the graph. We are using the graph implementation from our previous assignment, we had Digraph and GraphAlgo. 
Our algorithm to allocate which agent will go to catch the pokemon, is a greedy algorithm, the closest pokemon to an agent will be allocated to it and then the pokemon will be marked. 
The algorithm time complexity is O(n^2) and space complexity is also O(n^2)

## Our code structure <br />
![UML](https://user-images.githubusercontent.com/68643157/148660877-b1b33f98-305b-4109-ab2a-a00591838b63.png)



## classes <br />
1. **Gnode** - This class is our Node object, to create one it needs to get key and location, if it doesn't get location
               it will give it a random location. 
      <br />
2. **Edge** - This class is our Edge object and gets src dest and weight.<br /><br />
3. **DiGraph** -AKA "Directed weighted graph" this class implements the graph interface
            and is build of two different dicts, one for nodes and one is a nested dict for edges.<br /><br />
4. **GrapAlgo** - aka Directed weighted grap algo. This class implements the Graphalgo interface, that is where all the algorithms for the graph are.
                - Shortest path between 2 vertacies.
                - The ideal center of the graph.
                - Travelling salesman problem for a group of vertacies in the graph
                - Plot the graph 
5. **Agent** - This is out Agent object all of its information comes from the client server.
6. **Pokemon** - This is the Pokemon object all of its information come from the server.
7. **GameFunc** - This is the main class for the project, in this class we build our game, we have a list of all the pokemons, a dict of all the agents and
                  a GraphAlgo as the graph of the case. 
8. **GUI** - This is our GUI class, we turn our game into a UI (more on this down bellow)
9. **Ex4Main** - This is the "main" class where we connect everything together to make each case run and have a visible gui. 
  
## GUI
<br />

This is the Graph User Interface, which will show the graph that we have created <br />
This is case 1 for example: 

![case_1](https://user-images.githubusercontent.com/68643157/148652409-70aef2b0-4542-43a0-abb6-bbf1c638ff54.png)

### What's in the picture above: <br />

1. **Time** - This will show the time the game has been running for.
2. **Moves** - This shows the amount of moves that have been made. 
3. **Grade** - This shows the grade you are on. 
4. **The graph** - This represents the arena you are in. 
5. **Click To Stop** - This will stop the game. 

## Algorithms<br />

- **IsConnected** - This algorithm will check if all the vertacies are connected.<br />
  We implemented this by usign DFS, and checking if all the nodes were visited.    

- **Shortest_Path** - This algorithm finds the shortest path between two Nodes and return the weight and the route it travels between them.
  We used the Dijkstra algorithm. <br /><br />
    
- **CenterPoint** - Find the Node that is the most center in the graph.<br />
  We use the Dijkstra algorithm and find the minimum distance for each Node. <br /><br />

- **Tsp** - Travelling Salesman Problem. 
  Given a list of Nodes, find the shortest way to visit all Nodes at least once. 
  In the tsp we first initialized a matrix. 
  Each index in the matrix represented the weight between two nodes.
  We than ran the 'Dijkstra' algorithem, minimizing each index to the shortrst path between the two nodes.
  We then initialized a boolean array, where each index represents a node key from the givin graph.
  The index in the boolean array is true if the node was visited and false if not.
  Since the rout is cyclic there is no importance to the starting point.
  We used the tsp_helper function. It recursivly computes the tsp for each node.
  The helper returns the lowest path by weight.
  
- **Load from json** - Given a path of a json file, load it to a GraphAlgo

- **Save to json** - Given a graph that we want to save, it will save it in a json format.

- **Get graph** - return the graph that is in the GraphAlgo.

- **Allocate Agent** - This will find the best agent for each pokemon. 

## Three cases: 
  **Case 3**
  
  <img width="818" alt="updated_case3" src="https://user-images.githubusercontent.com/68643157/148674601-88ff2f15-3cfa-4634-a244-87fea9168a41.png">

  
  **Case 7**
  
  <img width="707" alt="updated_case7" src="https://user-images.githubusercontent.com/68643157/148674630-da254465-57b9-4233-9783-e5e318af1bb9.png">


  **Case 11**
  
  <img width="782" alt="updated_case11" src="https://user-images.githubusercontent.com/68643157/148674639-c7468f1e-5aa9-4550-a35d-bdadb567ae84.png">
      

## Algorithms Results<br />
![game_results](https://user-images.githubusercontent.com/68643157/148660893-993b080b-6ce2-4f89-80cd-99b9f6b466a7.png)
<br />


## Short clip of our game<br />
![short_clip_ex4_AdobeCreativeCloudExpress_AdobeCreativeCloudExpress](https://user-images.githubusercontent.com/68643157/148661181-18729a84-1442-46d6-ab96-5d0cb100f737.gif)


## Running the programme <br />

1. Clone the project from [here](https://github.com/Arieh-code/OOP-Ex4.git). <br />
2. Open the project and go to Ex4Main and change the case number from 0-15 (picture bellow)
![run the case](https://user-images.githubusercontent.com/68643157/148662665-7b24ba32-7206-411d-83e4-2264391e3960.png)
3. Download the release code for [here](https://github.com/Arieh-code/OOP-Ex4/releases/tag/v1.0.0)


