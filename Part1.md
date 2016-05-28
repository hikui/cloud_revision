# Cluster and Cloud Computing Revision

# Overview 

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
$p$: number of procs

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


