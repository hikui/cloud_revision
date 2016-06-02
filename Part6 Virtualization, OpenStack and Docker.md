# Virtualization

## Terminology

* Virtual machine monitor / Hypervisor   
	The virtualisation layer between the underlying hardware (e.g. the physical server) and the virtual machines and guest operating systems it supports.
	* The environment of the VM should appear to be the same as the physical machine	* Minor ==decrease in performance only==	* Appears as though in control of system resources

* Virtual Machine: A ==representation of a real machine== using hardware/software that can host a guest operating system.
* Guest Operating System: An operating system that runs in a virtual machine environment that would otherwise run directly on a separate physical system.

![](img/hmm_vmware.png)
*The user interface of a HMM (VMWare Fusion)*

## Background Knowledge

### Processor modes
A processor in a computer running a typical OS has two different modes: user mode and kernel mode. The processor switches between the two modes depending on what type of code is running on the processor. Applications run in user mode, and core operating system components run in kernel mode. While many drivers run in kernel mode, some drivers may run in user mode.

#### Kernel Mode

In Kernel mode, the executing code ==has complete and unrestricted access to the underlying hardware==. It can execute **any** CPU instruction and reference **any memory address**. Kernel mode is generally reserved for the lowest-level, most trusted functions of the operating system. Crashes in kernel mode are catastrophic; they will ==halt the entire PC==.

#### User Mode

In User mode, the executing code has ==no ability to directly access hardware or reference memory==. Code running in user mode must ==delegate to system APIs to access hardware or memory==. Due to the protection afforded by this sort of isolation, crashes in user mode are always recoverable. Most of the code running on your computer will execute in user mode.

![](img/cpumode.png)

---

### Protection rings (Privilege rings)

![](img/Priv_rings.png)

Computer operating systems provide different levels of access to resources. A protection ring is one of two or more hierarchical levels or layers of privilege within the architecture of a computer system. This is generally hardware-enforced by some CPU architectures that provide different ==CPU modes== at the hardware or microcode level. Rings are arranged in a hierarchy from most privileged (most trusted, usually numbered zero) to least privileged (least trusted, usually with the highest ring number). On most operating systems, ==Ring 0 is the level with the most privileges and interacts most directly with the physical hardware such as the CPU and memory==.

---

### Classification of instructions

> 'Instructions' means CPU instructions. Please see assembly language to learn more about instructions. [Here is the instrction set of x86](https://en.wikipedia.org/wiki/X86_instruction_listings).

* Privileged Instructions:   
	instructions that trap if the processor is in user mode and do not trap in kernel mode.
	

# Linux Containers

# OpenStack

# Docker

