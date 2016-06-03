# Cluster and Distributed Computing

# Overview 

Vertical scaling: have faster processors  
Horizontal scaling: have more processors

Types of parallel:

* single machine multipule cores
* loosely coupled cluster of machines
	* Seti@home
* Tightly coupled clusters
	* HPC, servers in a room
* widely distributed clusters of machines ???
* hibrid

### Limitations:

#### Amdahl's Law (modified)

\\[
    S(p) = \frac{p}{1+(p-1)\:f} \approx \frac{1}{f}
\\]

$f$: fraction of work that cannot be parallelised.   
$p$: number of processors.

Meaning: if the **fraction** of serial work is fixed, then the speedup is limited.

#### Gustafson-Barsis's Law (calculaton???)

\\[
	S(N) = \alpha + N(1-\alpha) = N - \alpha (N-1)
\\]

$\alpha$: fraction of running time sequential program **speeds on** parallel parts.

### Approaches for Parallelism

#### Explicit vs Implicit Parallelisation

* Implicit Parallelism
	* supported by parallel languages and parallel compilers
* Explicit Parallelism
	* the programmer is responsible for most of the parallelisation effort
	* assumes user is the best judge

### Parallelisation Paradigms
* Task-farming / master-worker   
	![f](./img/master-worker.png)
	* Master decomposes the problem into smaller tasks, distributs to workers and gathers partial results to produce the final result
	* Realised in many ways of different levels of ==granularity==, e.g. threads through to web service workflow definition and ==enactment==.
* Single-program multiple-data   
	![](./img/spmd.png)
	* Commonly exploied model
		* ==Bioinformatics==, MapReduce, ...
	* Each process executes the same piece of code, but on different parts of the data
	* Data is typically split among the available procs
	* Data splitting and analysis can be done in many ways
	* Assignment 1
* Pipeling   
	![](./img/pipeline.png)
* Divide and Conquer   
	![](./img/dividenconquer.png)
	* A problem is divided into two or more sub problems. Each of these sub problems are solved independently and their results are combined
	* 3 operations: split, compute and join
	* Master-worker is kike divide and conqure with master doing both split and join
* Speculation: very complex, can't understand...
* Parametric Computation: never seen in the slides

### Erroneous Assumptions of Distributed Systems (Problems that hard to deal with)

1. The network is reliable
2. Latency is zero
3. Bandwidth is infinite
4. The network is secure
5. Topology doesn't change
6. There is one administrator
7. Transport cost is zero
8. The netowrk is homogeneous
9. The time is _ubiquitous_ (Because there is no global time)

