# Boggl - general notes

[ZeroMQ]: zeromq.org/

Boggl starts with the assumption that all its simulated computation will use
modules that are effectively DNNs (deep neural networks). 
The actual implementation of these networks is external to Boggl, however
for it to be used as a module within a **BI** (Boggle Instance), it will need
to use (or be wrappered with) the Boggl module API.

A **module** in Boggl terms is any code that runs within a process on a single
computer that conforms to the module API. A process may implement one to many
modules, but a single process cannot span more than one machine.

Boggl is intended for use in exploring ideas for AGI (artificial general
intelligence) while recognizing that available computation is typically
many orders of magnitude too limited for significant results.  All
symbolic representation is abandoned in favor of topomorphic maps to brain
structures with physical analogues in the embodiment (real or virtual) or to
maps (temporal-spatial) used in real world navigation.
This assumes that cognition can always be thought of as a delayed part of
a behavioral response loop. 

In this model, adjacent modules will by definition provide connections to neighbors.
Interconnections between modules are predetermined in the specification for
a given model (an analogy with genetic expression). The scale (i.e. #layers,
size of layers, channel widths) of various modules are fixed in the provisioning
specification. Various pre-defined specs are available for model organisms at
different detail levels as baselines for experimentation.

## Development

For mammals the full set of neurons is fairly fixed well before birth.
The connections between neurons continues to grow (synaptogenesis) even as the 
total number of neurons gradually declines. 
There's a synaptic catastrope at 
puberty with a drastic decline in the number of synapses, followed by 
gradual declines until death. 
Actual neurogenesis seems to be largely restricted to the hippocamus as part
of acquision of new memories requires the addition of somewhere to store 
(or perhaps just to index) them.

These would seem to indicate human performance comes not from creating new
networks so much as it is to gradually prune overconnected ones to find
optimal techniques for functioning the the given environment.

Humans also appear to reason by analogy using their spacial and sensory maps
as part of higher level cognition. To mimic this functionality well in a model,
we should connect our modules in a similar way. Boggl implements crosstalk between
adjacent modules and assumes that properly implemented modules will take advantage
of this for plasticity.

Boggl models assume its modules will operate in a similar fashion. A
module configures itself based on provisioning information provided on startup.
Channels to other modules are provided and the modules handshake with a base 
level of communication.

Channel activity changes based on developments within a module, and the
module can reorganize its internal representations as needed, but generally
the BI should not consume significantly
more resources as it matures.

## Deployments

Models are usually first tested on indivual machines by generating with
very limited provisioning specs. This gets the kinks out of the connection
graph and makes sure that all modules can communicate.

The next step is deployment to a larger set of machines with significant
GPU acceleration. These are available un

Connections between modules are implemented as [ZeroMQ][ZeroMQ] queues. 
These send inter-server traffic over TCP/IP connections.
For larger models the number of channels may be impressively large and BIs
send **lots** of traffic between modules. Latency and throughput will
often be as critical for correct function as it will be for performance so
dedicated resources with fast interconnects will be needed.



```

	g_ : Denotes a nucleus (gray matter) - a module
	w_ : Denotes a tract or nervee (white matter) - a channel

	AA : Anatomically adjacent - denotes an implicit channel

	Directions

	L,M,I,S,A,P : lateral, medial, inferior, superior, anterior, posterior
	D,V,R,C : dorsal==S, ventral==I, rostral==A, caudal==P (CNS directions)
	D,V,R,C : dorsal==P, ventral==A, rostral==S, caudal==I (PNS directions)

```

#### End of document.
