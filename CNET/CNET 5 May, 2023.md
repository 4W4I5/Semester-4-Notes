# Distance Vector Routing

Cons of Broadcast
- Generates a lot of traffic

Types of Vector Routing Algo
- Distributed
	- Each node communicates with directly attached Negihbours
- Iterative
	- Continues until no nodes exchange info
	- Self-Terminatig signal to stop
	- Runs until every node gets a constient view
- Asynchronous
	- Nodes need not exchange info/iterative in lock state
	- Avoids lock state

Bellman-Ford Algo
- Used in DVR Algo
- Probes each neighboring connection for the shortest path
- 