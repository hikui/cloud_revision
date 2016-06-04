# OpenStack
## Components and Architecture

<img src="img/openstack_arch.png" style="max-width:70%"/>

*  Compute Service (code-named Nova)*  Image Service (code-named Glance)*  Block Storage Service (code named Cinder)*  Object Storage Service (code-named Swift)*  Security Management (code-named Keystone)
*  Orchestration Service (code-named Heat)*  Network Service (code-named Neutron)*  Metering Service (code-named Ceilometer)
*  Database service (code-named Trove)*  Dashboard service (code-named Horizon)
*  Search service (code-named Searchlight)*  Security API (code named Barbican)

## Terminologies

### Volume Store (Clinder in OpenStack, EBS in AWS)
Block-level storage volumes that can be attach to a running instance. It behaves like a raw, unformatted, external block device (hard drive).

### Object Storage (Swift in OpenStack, S3 in AWS)

Object storage is a storage architecture that manages data as objects. It stores and retrieves ==arbitrary unstructured data objects==. The OpenStack object storage (and Amazon S3) provides storage ==through web services interfaces (REST, SOAP)==. Fault tolerant with data replication and scale-out architecture.

### Machine Image (Glance in OpenStack, AMI in AWS)

The main component of a machine image is a ==read-only filesystem image== that includes an operating system (e.g., Linux, Unix, or Windows) and ==any additional software== required to deliver a service or a portion of it. (In short: pre-configured virtual machine image that is ready to run on a hypervisor).

### Key-pair

A pair of public key and private key used in Public-key cryptography. In OpenStack (and AWS), all Linux instances use key-pairs to authenticate users when they are logging in via SSH.

### Security Groups

A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you associate one or more security groups with the instance. You add ==rules== to each security group that allow traffic to or from its associated instances.



