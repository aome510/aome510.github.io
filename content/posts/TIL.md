---
title: "TIL"
draft: false
author: "AOME"
description: "My own collection of TILs"
showtoc: true
---

This is a collection of **T**oday **I** **L**earned(s) inspired by [TIL](https://github.com/jbranchaud/til).

The **TIL** collection is a place where I wrote down things that I learn everyday. It also serves as a small wikipedia for future references and learning. 

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

### Definitions
- [Dynamic dispatch](https://en.wikipedia.org/wiki/Dynamic_dispatch) is "_the process of selecting which implementation of a polymorphic operation (method or function) to call at run time._"
- [Static dispatch](https://en.wikipedia.org/wiki/Static_dispatch) is "_a form of polymorphism fully resolved during compile time._"

### Takeaways
- Static dispatch relies on compile time type information to select the specific interfaces while dynamic dispatch relies on run time information (usually through [vtable](https://en.wikipedia.org/wiki/Virtual_method_table) pointers).
- In Rust, static dispatch uses generics or trait bounds to perform [monomorphization](https://rustc-dev-guide.rust-lang.org/backend/monomorph.html) of the generic codes. On the other hands, Rust allows dynamic dispatch with [trait objects](https://doc.rust-lang.org/book/ch17-02-trait-objects.html).

### Additional Resources
- [Polymorphism in Rust (Blog)](https://oswalt.dev/2021/06/polymorphism-in-rust/?utm_source=pocket_mylist)
- [Trait object (Rust Book)](https://doc.rust-lang.org/book/ch17-02-trait-objects.html)
- [Generic Types, Traits (Rust Book)](https://doc.rust-lang.org/book/ch10-00-generics.html)

## Unix/Linux

### Memory management
- [Memory overcommit](https://en.wikipedia.org/wiki/Memory_overcommitment) is "_a concept in computing that covers the assignment of more memory to virtual computing devices (or processes) than the physical machine they are hosted, or running on, actually has._"
- [Linux's OOM-Killer](https://en.wikipedia.org/wiki/Out_of_memory#Out_of_memory_management) is a mechanism that the **Linux** kernel uses when the system is low on memory. It sacrifices one or more processes to free up memory for the system according to given metrics.

#### Additional Resources
- [PostgreSQL, Memory and the Cloud (Blog)](https://sosna.de/posts/pgaas-memory-overcommit/)

## Other terms/definitions
- [OEM (original equipment manufacturer)](https://en.wikipedia.org/wiki/Original_equipment_manufacturer) is often used to refer to a company that manufactures a product which is then marketed or sold by another company.
- [GDPR (General Data Protection Regulation)](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) is "_a regulation in EU law on data protection and privacy in the European Union (EU) and the European Economic Area (EEA)._"
- [401(k) program](https://en.wikipedia.org/wiki/401(k)) is an "_employer-sponsored defined-contribution pension account_" which employees can contribute to using their paycheck. Employers can also make contributions to the account by [matching](https://www.investopedia.com/articles/personal-finance/112315/how-401k-matching-works.asp).

To be updated...
