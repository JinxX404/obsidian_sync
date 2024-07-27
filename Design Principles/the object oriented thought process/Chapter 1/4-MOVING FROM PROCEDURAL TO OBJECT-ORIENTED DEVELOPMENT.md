**Procedural Programming** 
	normally separates the data of a system from the operations that manipulate the data. For example, if you want to send information across a network, only the relevant data is sent with the expectation that the program at the other end of the network pipe knows what to do with it. In other words, some sort of handshaking agreement must be in place between the client and the server to transmit the data. In this model, it is quite possible that no code is actually sent over the wire.
	![[Pasted image 20240623170037.png]]
	الداتا مفصوله عن الاوبريشنز 


**OO Programming**
	The fundamental advantage of OO programming is that the data and the operations that manipulate the data (the code) are both encapsulated in the object. For example, when an object is transported across a network, the entire object, including the data and behavior, goes with it.
	 **A Single Entity**
		 Although thinking in terms of a single entity is great in theory, in many cases, the behaviors themselves may not be sent because both sides have copies of the code. However, it is important to think in terms of the entire object being sent across the network as a single entity.
	![[Pasted image 20240623170259.png]]
	الداتا والاوبريشنز مع بعض فاوبجكت 
	لما بنبعت حاجه عالنيتورك بنبعت الاوبجكت كامل (الداتا والاوبريشن)
	