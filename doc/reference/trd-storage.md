Application Persistent Data Storage and Permissions
===================================================

**TRD:** <br/>
**Working Group:** Kernel<br/>
**Type:** Documentary<br/>
**Status:** Draft <br/>
**Author:** Brad Campbell<br/>
**Draft-Created:** 2024/03/19<br/>
**Draft-Modified:** 2024/03/19<br/>
**Draft-Version:** 1<br/>
**Draft-Discuss:** tock-dev@googlegroups.com<br/>

Abstract
-------------------------------

This document is in full compliance with
[TRD1][TRD1].

1 Introduction
-------------------------------

Tock applications need to be able to store persistent state. Additionally,
applications need to be able to keep data private from other applications. The
kernel should also be able to allow specific applications to read and modify
state from other applications.

This requires a method for assigning applications persistent identifiers,
a mechanism for granting storage permissions to specific applications,
and kernel abstractions for implementing storage capsules that respect
the storage permissions.




2 Scope
-------------------------------

This document only describes the permission architecture in Tock for supporting
application persistent storage. This document does not include specific types of
persistent storage (e.g., flash, FRAM, etc.) or storage access abstractions
(e.g., block-access, byte-access, etc.).



3 Assumptions
-------------------------------

All persistent application data is labeled based on the application which wrote
the data. Applications can always read and modify data they wrote. Applications
can read and modify data from other applications with suitable permissions.

There are three types of permissions:


1. **Write**: The application can write data.
1. **Read**: The application can read other applications' data.
1. **Modify**: The application can modify other applications' data.




3 Requirements
-------------------------------


1. Applications are given separate write, read, and modify permissions.






12 Authors' Addresses
===============================
```
Brad Campbell <bradjc@virginia.edu>
```

[TRD1]: trd1-trds.md "Tock Reference Document (TRD) Structure and Keywords"
