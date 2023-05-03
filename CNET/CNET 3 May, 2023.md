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