# Routing Algo classification
Last class notes
- Global Information
	- All routers have complete topology, link cost info
	- Link State Algorithms
- Decentralized Information
	- Router knows physically connected neighbors. Link costs to neighbors
	- Iterative process of computation, exchange of info with neighbors
	- Distance Vector algos

- Static
	- Routes are hardcoded and slowly change over time
- Dynamic
	- Routes change more quickly 
		- Periodic update
		- Response to link changes such as congestion
---
### Link State
- Global Centralized
	- Full route information is available to every node (Flood)
- Find directly connected neighbors
- Builds a LSP(Link-State Packet) to all neighbors, who stores the recieved LSP in a database
	- The result of the nodes' broadcast is that all nodes have an identical and complete view of the netwokr
	- Accumulates costs along each path from source to destination
	- Each node/router
- Flood neighbors with LSP 
- Use of Djisktra algo to compute weights and costs for every edge
- Notation
	- c(x,y)
		- Cost from x to y
	- D(v)
		- Direct Cost from U to V
	- P(v)
		- Predecessor to V
	- N'
		- Visited Node


| Step | N'     | D(v), P(v) | D(w), P(w) | D(x), P(x) | D(y), P(y) | D(z), P(z) |
| ---- | ------ | ---------- | ---------- | ---------- | ---------- | ---------- |
| 0    | u      | 2,u        | 5, u       | 1,u        | infinite   | infinite   |
| 1    | ux     | 2,u        | 5, u       |            | infinite   | 3, z       |
| 2    | uxv    |            | 5, u       |            |            |            |
| 3    | uxvy   |            |            |            |            |            |
| 4    | uxvyw  |            |            |            |            |            |
| 5    | uxvywz |            |            |            |            |            |
NOTE:: DO this table later baad mein (Very bad at this)

