# Cloud

## History （how we got there）

1. Centralised system
	* Single physical system. All resources are fully shared and tightly coupled within one integrated OS. (Time sharing???)
2. Parallel system
	* All procs eighter tightly coupled with centralised shared memory (multi-cores, OpenMP) or loosely coupled with distributed memory (MPI). Interprocess communication throught shared mem or message passing.
3. Distributed system
	* Multiple _autonomous_ computers with their own private memory, communicating through message passing over a computer network.
	* computer to computer interaction focus
	* heterogeneity
4. Grid computing
	* organization to organization focus

(Cloud computing is centralised again to some extent (data centre))

## Motivation
* Cost-benifits: flexibility
* Simplicity: providers will take care of hardware.

## Flavours of Cloud

### Delivery models

<img src= "./img/cloudflavours.png" style="max-width:100%"/>

* On-premises
* IaaS
* PaaS
	* GAE
* SaaS
	* Gmail, Office 365

#### Essential Characteristics

* _On-demand_ self-service
* Broad network access 
* Resource pooling (don't have fixed set of resources)
* Rapid elasticity
* Measured service (Determines how you pay the money)

### Deployment models

* Public clouds
	* pros
		* utility computing
		* (users can) focus on core business
		* cost-effective
		* right sizing
		* democratisation of computing???
	* cons
		* security
		* loss of control
		* possible lock-in
* Private clouds
	* cons
		* core business irrelevent
		* staff/management overheads
		* hardware obsolescence
* Hybrid clouds