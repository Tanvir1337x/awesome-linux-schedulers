# Awesome Linux Schedulers [![Awesome Linux CPU Schedulers](https://awesome.re/badge-flat.svg)](https://github.com/TanvirOnGH/awesome-linux-cpu-schedulers)

An Awesome & Curated List of Schedulers for Linux.

## Contents

- [Awesome Linux Schedulers ](#awesome-linux-schedulers-)
  - [Contents](#contents)
    - [Official Linux Kernel CPU Schedulers](#official-linux-kernel-cpu-schedulers)
    - [Community-Developed CPU Schedulers](#community-developed-cpu-schedulers)
    - [Multiqueue I/O Schedulers](#multiqueue-io-schedulers)
    - [Non-Multiqueue I/O Schedulers](#non-multiqueue-io-schedulers)
  - [Resources](#resources)

### Official Linux Kernel CPU Schedulers

1. [CFS: Completely Fair Scheduler](https://docs.kernel.org/scheduler/sched-design-CFS.html) - The default process scheduler used in the Linux kernel since version 2.6.23. It is designed to provide fairness and good overall system performance, especially in multi-core systems, with it's "fairness" mechanism.
2. [EEVDF: Earliest Eligible Virtual Dealine First](https://lwn.net/Articles/925371/) - Designed to run the processes with the earliest virtual deadline first, for providing low-latency.

### Community-Developed CPU Schedulers

1. [BORE: Burst-Oriented Response Enhancer](https://github.com/firelzrd/bore-scheduler) - Enhanced version of [CFS](https://docs.kernel.org/scheduler/sched-design-CFS.html) and [EEVDF](https://lwn.net/Articles/925371/), designed to provide high performance while delivering resilient responsiveness to user input under as versatile load scenario as possible.
2. [Baby](https://github.com/hamadmarri/Baby-CPU-Scheduler) - Designed to be very basic and lightweight without compromising performance by disabling a lot of features. Great base ground CPU scheduler on Linux for educational purpose.
3. [TT: Task Type](https://github.com/hamadmarri/TT-CPU-Scheduler) - Designed to detect tasks types based on their behaviors and control the scheduling based on their types, resulting in to have more control over the task to run next on the CPU.
4. [MuQSS: Multiple Queue Skiplist Scheduler](https://lwn.net/Articles/720227/) - Designed to improve system responsiveness and reduce latency, especially in desktop and interactive workloads.
5. [BFS: Brain Fuck Scheduler](https://en.wikipedia.org/wiki/Brain_Fuck_Scheduler) - Designed to be simple and minimalistic, it is an experimental process scheduler designed for low-latency and improved desktop interactivity.
6. [CacULE](https://github.com/hamadmarri/cacule-cpu-scheduler) - [CFS](https://docs.kernel.org/scheduler/sched-design-CFS.html) patchset that is based on interactivity score mechanism which is inspired by the [ULE](https://en.wikipedia.org/wiki/ULE_scheduler) scheduler ([FreeBSD scheduler](https://papers.freebsd.org/2003/bsdcon/jeff-ule_scheduler/)), for enhancing system responsiveness/latency. Performs better with it's own experimental load balancer called [RDB (Response Driven Balancer)](https://github.com/hamadmarri/cacule-cpu-scheduler#response-driven-balancer-rdb).
7. [Cachy](https://github.com/hamadmarri/cacule-cpu-scheduler/tree/c68d210538fabac002acb84d99e9c3d365edc14f) - Earlier generation/version of [CacULE](https://github.com/hamadmarri/cacule-cpu-scheduler).
8. [PDS-MQ: Priority and Deadline based Skiplist multiple queue](https://www.phoronix.com/news/PDS-MQ-Linux-4.17) - Designed with VRQ (Variable Run Queue) support, derived from [BFS: Brain Fuck Scheduler](https://en.wikipedia.org/wiki/Brain_Fuck_Scheduler).
9. [BMQ: Bit Map Queue](https://www.phoronix.com/news/Linux-BitMap-Queue-BMQ) - Design based on existing [PDS](https://www.phoronix.com/news/PDS-MQ-Linux-4.17) development experience and inspired by the scheduler found in [Zircon](https://fuchsia.dev/fuchsia-src/concepts/kernel) by Google.
10. [ECHO: Enhanced CPU Handling Orchestrator](https://github.com/hamadmarri/ECHO-CPU-Scheduler) - A CPU processes scheduler patch for the Linux kernel. It features highly multitasking handling with a maximum 35us quota, shared quotas for tasks, a minimum slice for running tasks, estimation of tasks using Shortest Remaining Task Next (SRTF), and a load balancer similar to the TT scheduler.

### Multiqueue I/O Schedulers

1. [BFQ: Budget Fair Queueing](https://docs.kernel.org/block/bfq-iosched.html) - Designed to improve storage I/O performance, especially for block devices like hard drives and solid-state drives (SSDs), with ability to provide low-latency and fairness for I/O operations.
2. [Kyber](https://lwn.net/Articles/720071/) - Introduced in version 4.12. It is designed to improve storage I/O performance, especially for modern non-rotational storage devices like solid-state drives (SSDs) and eMMC storage, with low overhead.
3. [mq-deadline](https://github.com/torvalds/linux/blob/master/block/mq-deadline.c) - Adaptation of the legacy [deadline](https://en.wikipedia.org/wiki/Deadline_scheduler) scheduler, for the [blk-mq](https://docs.kernel.org/block/blk-mq.html) scheduling framework, it is designed to group queued I/O requests into batches.

### Non-Multiqueue I/O Schedulers

1. [deadline](https://en.wikipedia.org/wiki/Deadline_scheduler) - Introduced in version 2.4.10 and is designed to optimize I/O performance for both rotational (e.g., traditional hard disk drives) and non-rotational (e.g., solid-state drives) storage devices, focusing on meeting I/O request deadlines.
2. [noop: No-operation](https://en.wikipedia.org/wiki/Noop_scheduler) - Designed to be a simple and minimalistic scheduler that works effectively with certain types of storage devices, particularly with modern non-rotational storage media like solid-state drives (SSDs). It's very minimalistic and lacks scheduling overhead.
3. [CFQ: Completely Fair Queueing](https://www.kernel.org/doc/Documentation/block/cfq-iosched.txt) - Designed to provide fairness and good overall system performance, especially for rotational storage devices like traditional hard disk drives (HDDs), focusing on fairness among processes accessing storage devices.

## Resources

- [Project C](https://gitlab.com/alfredchen/projectc) - A project to provide BMQ and PDS-mq cpu scheduler in one single patch set.
- [CK Kolivas' Patches Web Directory](http://ck.kolivas.org/patches/) - CK's web directory providing MuQSS, BFS and other patchsets.
- [Linux Baby](https://github.com/hamadmarri/linux-baby) - Linux kernel with baby patchset applied.
- [Linux CachyOS](https://github.com/CachyOS/linux-cachyos) - Linux kernel with various patchsets applied including bore, eevdf, TT, BMQ, PDS, CacULE+RDB and CFS.
- [Xanmod Kernel](https://xanmod.org) - Custom linux kernel built to provide a stable, smooth and solid system experience.
- [linux-pf](https://codeberg.org/pf-kernel/linux) - Maintained by a kernel engineer ([post-factum](https://pfkernel.natalenko.name/)), contains patchsets not merged into the official kernel mainline.
- [Zen Kernel](https://github.com/zen-kernel/zen-kernel) - Result of a collaborative effort of kernel hackers to provide the best Linux kernel possible for everyday systems.
- [Liquorix Kernel](https://liquorix.net) - An enthusiast Linux kernel designed for uncompromised responsiveness in interactive systems, enabling low latency compute in A/V production, and reduced frame time deviations in games.
- [Kernel patches by Sir lucjan](https://github.com/sirlucjan/kernel-patches) - Curated custom Linux kernel patches.
- [clearlinux-pkgs/linux](https://github.com/clearlinux-pkgs/linux) - Linux kernel patches by [clear linux](https://clearlinux.org) optimized for Intel systems.
- [linux-nitrous](https://gitlab.com/xdevs23/linux-nitrous) - Linux kernel with patchsets optimized for Intel Skylake and newer systems.
- [hamadmarri/benchmarks](https://github.com/hamadmarri/benchmarks) - Curated list of Linux CPU Scheduler Benchmarks and Feedback.
