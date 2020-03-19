# dijktras_psudo

~~~c
Dijktras(S,E)//s start node
	dist(S)=0 //distance of start node to 0
	dist(v)=inf //distance of every other node to big
	Prev(v) = nullptr //the begining of the path
	Q = min heap wrt dist  //q is a min heap according to distance
	Q.add(v)//add all vertices (including s) to q
	vector<node> m //vector of nodes 
	
	While Q !empty
		u = Q.pop() //pops the smallest vertex
		if(u == E) //if u is the end of the path
			while(u != S) //goes until u is not the start node
				m.push(u) //adds u to the path
				u = Prev(u) //u becomes the parent of u
			break //breaks out of loop because found the best path to E
		Foreach a in u.adj //for all the adjecents to u
			Da = dist(u) + edgeWeight(u,a)  //int distance to a 
			If Da < dist(a)  //if that is smaller than the distance found for the node
				Dist(a) = Da //update the distance
				Prev(a) = u 
				Q re-heap //re-sort the queue
	Return flip of m //reverse m so that the first of the path is index 0
~~~
