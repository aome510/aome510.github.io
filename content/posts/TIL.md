---
title: "TIL"
draft: false
author: "AOME"
description: "My own collection of tech-related TILs"
showtoc: true
---

This is a collection of **T**oday **I** **L**earned(s) inspired by [TIL](https://github.com/jbranchaud/til).

The **TIL** collection is a place where I wrote down things that I learn everyday. It also serves as my own small Wiki for future references and learning.

## General Programming

### Static linking vs dynamic linking

#### Definitions

- [Static library](https://en.wikipedia.org/wiki/Static_library) is
  > a set of routines, external functions and variables which are resolved in a caller at compile-time and copied into a target application by a compiler, linker, or binder, producing an object file and a stand-alone executable
- [Dynamic linker](https://en.wikipedia.org/wiki/Dynamic_linker) is
  > the part of an operating system that loads and links the shared libraries needed by an executable when it is executed (at "run time"), by copying the content of libraries from persistent storage to RAM, filling jump tables and relocating pointers.

#### Takeaways

- The main different between dynamic and static linking is that one happens at **compile time** by **compiler or linker** and the other happens at **run time** by **operating system**.
- One trade-off when using dynamic linking compared to static linking is to be able to reduce the binary size (possibly RAM and disk storage) with a potential performance cost.
- There are also trade-offs in dependency management in which static link application is more portable and easier to control but is harder to upgrade/manage its dependencies.

#### Additional resources

- [Rust Linkage (Rust Doc)](https://doc.rust-lang.org/reference/linkage.html)
- [Dynamic link (HN Article)](https://news.ycombinator.com/item?id=23654353)
- [Linus Torvalds' opinion on shared libraries (HN Article)](https://news.ycombinator.com/item?id=27009044)
- [Dependency Hell (Wiki)](https://en.wikipedia.org/wiki/Dependency_hell)

### Static dispatch vs dynamic dispatch

#### Definitions

- [Dynamic dispatch](https://en.wikipedia.org/wiki/Dynamic_dispatch) is "_the process of selecting which implementation of a polymorphic operation (method or function) to call at run time._"
- [Static dispatch](https://en.wikipedia.org/wiki/Static_dispatch) is "_a form of polymorphism fully resolved during compile time._"

#### Takeaways

- Static dispatch relies on compile time type information to select the specific interfaces while dynamic dispatch relies on run time information (usually through [vtable](https://en.wikipedia.org/wiki/Virtual_method_table) pointers).
- In Rust, static dispatch uses generics or trait bounds to perform [monomorphization](https://rustc-dev-guide.rust-lang.org/backend/monomorph.html) of the generic codes. On the other hands, Rust allows dynamic dispatch with [trait objects](https://doc.rust-lang.org/book/ch17-02-trait-objects.html).

#### Additional Resources

- [Polymorphism in Rust (Blog)](https://oswalt.dev/2021/06/polymorphism-in-rust/?utm_source=pocket_mylist)
- [Trait object (Rust Book)](https://doc.rust-lang.org/book/ch17-02-trait-objects.html)
- [Generic Types, Traits (Rust Book)](https://doc.rust-lang.org/book/ch10-00-generics.html)

## Programming Languages

### Rust

TBA...

## Database

### ORM (Object–relational mapping)

#### Definition

- [Object–relational mapping](https://en.wikipedia.org/wiki/Object%E2%80%93relational_mapping) is
  > a programming technique for converting data between incompatible type systems using object-oriented programming languages [usually through abstraction (API)]. This creates, in effect, a "virtual object database" that can be used from within the programming language.

#### Compare with traditional database model

Traditional SQL is dry (don't repeat yourself), using ORM can help reduce code duplication through abstraction and interfaces. On the other hand, users of ORM can suffer from performance issues (normally the N+1 query problem) if not understand properly the underlying implementation behind the abstraction.

## Networking

TBA...

## Virtualization/Cloud Computing

TBA...

## Unix/Linux/OS/Computer Architecture

### Memory management

- [Memory overcommit](https://en.wikipedia.org/wiki/Memory_overcommitment) is "_a concept in computing that covers the assignment of more memory to virtual computing devices (or processes) than the physical machine they are hosted, or running on, actually has._"
- [Linux's OOM-Killer](https://en.wikipedia.org/wiki/Out_of_memory#Out_of_memory_management) is a mechanism that the **Linux** kernel uses when the system is low on memory. It sacrifices one or more processes to free up memory for the system according to given metrics.

#### Additional Resources

- [PostgreSQL, Memory and the Cloud (Blog)](https://sosna.de/posts/pgaas-memory-overcommit/)

### Terms/definitions

- [Inter-process communication (IPC)](https://en.wikipedia.org/wiki/Inter-process_communication) is a mechanism that allows progresses to communicate with each other usually through shared states or message passing/streaming.
- [Monolithic kernel](https://en.wikipedia.org/wiki/Monolithic_kernel) is an operating system architecture that holds a privilege access through a number of components such as process management, file system, I/O, hardware, etc. This model differs than other architectures such as [Microkernel](https://en.wikipedia.org/wiki/Microkernel) (which provides "_only a near-minimum amount of software_" to implement an OS) or [Hybrid kernel](https://en.wikipedia.org/wiki/Hybrid_kernel) (which tries to combines the benefits of both **Microkernel** and **Monolithic kernel**).
- [Kernel-based Virtual Machine (KVM)](https://en.wikipedia.org/wiki/Kernel-based_Virtual_Machine) is "_is a virtualization module in the Linux kernel that allows the kernel to function as a [hypervisor](https://en.wikipedia.org/wiki/Hypervisor)._"
- [Seccomp (secure computing mode)](https://en.wikipedia.org/wiki/Seccomp) is a secure mode that creates a sandbox in which a progress cannot make any system calls except `exit`, `read`, `write` and `sigreturn`. **seccomp-bpf** is an extension of **seccomp** that allows filtering system calls with [Berkeley Packet Filter](https://en.wikipedia.org/wiki/Berkeley_Packet_Filter).
- [Kernel mode setting (KMS)](https://wiki.archlinux.org/title/Kernel_mode_setting) is "_a method for setting display resolution and depth in the kernel space rather than user space. [It] enables native resolution in the framebuffer and allows for instant console (tty) switching._"
- [Linux control groups (cgroups)](https://en.wikipedia.org/wiki/Cgroups) is a feature used to manage the resource usage of a collection of processes. `cgroups` provides **resource limiting**, **resource prioritizing**, **resource accounting**, and **resource control** features.

## Cryptography

### Terms/Definitions

- [Message authentication code (MAC)](https://en.wikipedia.org/wiki/Message_authentication_code) is a code used to authenticate a message in order to confirm that the message is from a corresponding sender and has not been tampered. Normally, a MAC system consists of three algorithms which includes key-generation, singing, and verifying.
- [Hash-based message authentication code (HMAC)](https://en.wikipedia.org/wiki/HMAC) is "_a specific type of MAC involving a cryptographic hash function and a [shared] secret cryptographic key._" HMAC computes the hash in two passes. The secret is used to derive two keys, inner and outer. The first pass involves hashing the message with the inner key. The hash result is then used to produce the final result with the outer key.

## Other terms/definitions

- [Hypervisor (virtual machine monitor, virtualizer)](https://en.wikipedia.org/wiki/Hypervisor) is a technology that creates, manages, and runs virtual machines. A computer in which a hypervisor is running on is called _host machine_ while each virtual machine is called _guest machine_.
- [OEM (original equipment manufacturer)](https://en.wikipedia.org/wiki/Original_equipment_manufacturer) is often used to refer to a company that manufactures a product which is then marketed or sold by another company.
- [DRM (Digital rights management )](https://en.wikipedia.org/wiki/Digital_rights_management) is a set of technologies for restricting the use of copyrighted works (normally software or digital assets).
- [GDPR (General Data Protection Regulation)](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) is "_a regulation in EU law on data protection and privacy in the European Union (EU) and the European Economic Area (EEA)._"
- [401(k) program](<https://en.wikipedia.org/wiki/401(k)>) is an "_employer-sponsored defined-contribution pension account_" which employees can contribute to using their paycheck. Employers can also make contributions to the account by [matching](https://www.investopedia.com/articles/personal-finance/112315/how-401k-matching-works.asp).

## Misc

- [Kubernetes](https://kubernetes.io/) is also called K8s which stands for "the letter K followed by 8 characters then ends with letter s". This is also similar to Internationalization (i18n).

To be updated...
