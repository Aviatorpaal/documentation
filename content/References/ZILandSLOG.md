---
title: "ZFS ZIL and SLOG Demystified"
description: "Provides clarification on ZFS, ZIL, and SLOG concepts."
weight: 80
tags:
- zfs
- storage
---

The ZIL and SLOG are two of the most misunderstood concepts in ZFS and hopefully this helps clear things up.

As you surely know by now, ZFS is taking extensive measures to safeguard your data and it should be no surprise that these two buzzwords represent key data safeguards. What is not obvious however is that they only come into play under very specific circumstances.

**The first thing to understand is that ZFS behaves like any other file system with regard to asynchronous and synchronous writes.** 

When data is written to disk, it can either be buffered in RAM by the operating system kernel prior to being written to disk, or it can be immediately written to disk. 
The buffered asynchronous behavior is often used because of the perceived speed that it provides the user, while synchronous behavior is used for the integrity it guarantees. 
A synchronous write is only reported as successful to the application that requested it when the underlying disk has confirmed completion of it. 
Synchronous write behavior is determined by either the file being opened with the `O_SYNC` flag set by the application, or the underlying file systems being explicitly mounted in *synchronous* mode. 
Synchronous writes are desired for consistency-critical applications such as databases and some network protocols such as NFS but come at the cost of slower write performance. 
In the case of ZFS, the `sync=standard` property of a pool or dataset provides POSIX-compatible synchronous-only-if-requested write behavior while `sync=always` forces synchronous write behavior akin to a traditional file system being mounted in synchronous mode.

**“Asynchronous unless requested otherwise” write behavior is taken for granted in modern computing with the caveat that buffered writes are simply lost in the case of a kernel panic or power loss.**

Applications and file systems vary in how they handle such interruptions and ZFS fortunately guarantees that you can only lose the few seconds worth of writes that came after the last successful transaction group. 
Given the choice between the performance of asynchronous writes with the integrity of synchronous writes, a compromise is achieved with the ZFS Intent Log or ZIL. 
Think of the ZIL as the street-side mailbox of a large office: it is fast to use from the postal carrier perspective and is secure from the office perspective, but the mail in the mailbox is by no means sorted for its final destinations yet. 
When synchronous writes are requested, the ZIL is the short-term place on disk where the data lands prior to being formally spread across the pool for long-term storage at the configured level of redundancy. 
There are however two special cases when the ZIL is not used despite being requested: if large blocks are used or the `logbias=throughput` property is set.

**By default, the short-term ZIL storage exists on the same hard disks as the long-term pool storage at the expense of all data being written to disk twice: once to the short-term ZIL and again across the long-term pool.** 

Because each disk can only perform one operation at a time, the performance penalty of this duplicated effort can be alleviated by sending the ZIL writes to a separate ZFS intent log or SLOG, or simply log. 
While using a spinning hard disk as SLOG yields performance benefits by reducing the duplicate writes to the same disks, it is a poor use of a hard drive given the small size but high frequency of the incoming data.

**The optimal SLOG device is a small, flash-based device such an SSD or NVMe card, thanks to their inherent high-performance, low latency and of course persistence in case of power loss.** 

You can mirror your SLOG devices as an additional precaution and be surprised what speed improvements can be gained from only a few gigabytes of separate log storage. 
Your storage pool has the write performance of an all-flash array with the capacity of a traditional spinning disk array. 
This is why we ship every spinning-disk TrueNAS system with a high-performance flash SLOG and make them a standard option on our FreeNAS Certified line.

Thank you **Matthew Ahrens** of the OpenZFS project for reviewing this article.
