# boggl 0.0.1
[![Build Status][travis-image]][travis-url] 
[![Coveralls Status][coveralls-image]][coveralls-url]
[![Dependency Status][depstat-image]][depstat-url]

[travis-url]: https://travis-ci.org/jfogarty/boggl
[travis-image]: https://img.shields.io/travis/jfogarty/boggl.svg?branch=master
[coveralls-url]: https://coveralls.io/r/jfogarty/boggl
[coveralls-image]: https://img.shields.io/coveralls/jfogarty/boggl.svg
[depstat-url]: https://david-dm.org/jfogarty/boggl
[depstat-image]: https://david-dm.org/jfogarty/boggl.svg

[openshift-mm-url]: http://boggl-jfogarty.rhcloud.com
[openshift-mm-bvt-url]: http://boggl-jfogarty.rhcloud.com/test/testMocha.html
[openshift-mm-api-url]: http://boggl-jfogarty.rhcloud.com/api/index.html

**Brain Organization Graph Generation Language** - 
composition, generation, distribution and monitoring of machine intelligence models.

![backgound brain art](images/art/boggl_banner.jpg)

##NOT READY FOR PRIME TIME

When an alpha release is available I'll remove this message.
For the next year or so this project is closed to external developers.

**Please stand by...**

**boggl** provides a toolset for automating the composition of MI components
into a local or cloud deployed distributed application. It supports applications
that model biological central nervous systems at a fairly specific level of
abstraction, well above the level of individual neurons.

[theano]: http://deeplearning.net/software/theano/
[torch]: https://github.com/torch/torch7
[GroundHog]: https://github.com/pascanur/GroundHog
[pylearn2]: http://deeplearning.net/software/pylearn2/
[Lasagne]: https://github.com/Lasagne/Lasagne
[blocks]: https://github.com/mila-udem/blocks
[deep_q_rl]: https://github.com/spragunr/deep_q_rl/tree/master/deep_q_rl
[biopython]: http://biopython.org
[keras]: http://keras.io/
[pybrain]: https://wiki.github.com/pybrain/pybrain
[fann]: https://github.com/libfann/fann
[convnetjs]: https://github.com/karpathy/convnetjs

[ZeroMQ]: http://zeromq.org/
[raphaeljs]: https://github.com/DmitryBaranovskiy/raphael

Boggl is for building larger machine intelligence models from a variety
of other components. 
The components themselves are are feature vector based, continous
operation, unsupervised learning and discrimination processes specialized
for use with **boggl**. 
These can be implemened with existing tools such as 
[torch][torch], 
[theano][theano], 
[Lasagne][Lasagne],
[pybrain][pybrain],
[pylearn2][pylearn2], 
[keras][keras], 
[biopython][biopython],
[blocks][blocks], 
[fann][fann],
[convnetjs][convnetjs],
[deep_q_rl][deep_q_rl], 
or [GroundHog][GroundHog],

It is relatively language neutral so python, lua, go, js and even C are acceptable
for module implementation, although the best suport is currently for python.

boggl is **not** abstraction neutral as it follows a fairly rigid model for
how it expects modules to process inputs and provide results. It is
designed for implementing component networks that can be used to mimic
biological systems so 'off the shelf' neural networks for MNIST are not
going to be much use with it. You write boggl scripts to specify how to find
modules in external processes, and how to provision and interconnect these processes
into a graph. Deployments are generated for specific network and server environments from single machines to public clouds. 
This simplifies experimentation since components
are more easily added, edited and removed without extensive recoding.
Automatic generation of 'stub' modules simplifies testing and aids in incremental
development.

A **BI** (boggl Instance) is a composed, generated, provisioned, deployed, or running instance of a set of components that runs concurrently and on the same data.
Input components connecting external processes can be as simple as isolated training sets, or as complete as vision and hearing and a full range of other senses.
Output components provide results in the form of motor activations,
numeric arrays, or text.
Communication between processes is via [ZeroMQ] queues which uses various forms of IPC including TCP/IP. Network effects are often critical in performance and even function of components so channels between processes include latency specifications and activity monitors.

## Specification and Composition Features
* Neurobiological terminology based module and channel descriptions
* Labeled lines for organization of pathways
* Explicit required/desired channel latencies
* Named bundles with aliases and long names
* Explicit directional channel inteconnections between modules
* Module adjacency definitions for implicit crosstalk channels
* Neural layer specification for interconnection

## General Features
* Follows [semantic versioning](http://semver.org/) for releases

## Packaging Features
* Packaging into a local machine process set
* Packaging into Docker components

## Deployment Features
* Distribution of components to AWS cloud servers
* Cluster orderly startup, checkpointing and shutdown

## Monitoring Features
* Process, channel, and module level activity and performance metrics
* Generated per instance web portal for command, control and monitoring
* Generated [Raphaël][raphaeljs] based graphs for model visualization
	- Process and server instance graphs 
	- Model module and channel graphs with hierarchical expansion
	- Filters for drill down and clutter elimination
* And more

[Contributors](CONTRIBUTING.md)

[Developers](docs/DEVELOPERS.md)

[The current boggl test server (OpenShift hosted)][openshift-mm-url]

#### End of document.
