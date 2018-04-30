---
title: "zeno-he"
description: "Lighter-than-air, peer-to-peer, bounded, non-blocking, non-threaded, etc., implementation of zenoh"
# repo: "https://github.com/atolab/Zeno-He/" # delete this line if you want blog-like posts for projects
tags: ["c"]
weight: 1
draft: false
---

zeno-he (zhe for short) is a compact implementation of the __zenoh__ protocol that does not depend on dynamic allocation or threading. Instead, it is a non-blocking implementation that assumes single threaded use with polling, and a system that can be sized at compile time. Zhe can be configured to operate in peer-to-peer mode or to operate as a client that relies on a broker.

Zhe does not call any operating system functions directly (its use of the standard library functions is currently limited to string.h, stddef.h, limits.h, stdint.h and inttypes.h). It does rely on a small abstraction layer to be provided by the user implementing functions to send a packet without blocking (it may of course be dropped), test addresses for equality and to convert an address to text. What constitutes sending data on a network or what an address looks like is deliberately left undefined. The interface of the abstraction layer is described below.

Please note that it is currently a research project under active development. Only the basic functionality supported by the zenoh protocol has so far been implemented, and still missing are several features we consider important, such as selections and transient data support. These will be implemented in the near future. Furthermore, none of the settings are final, and everything can (and probably will) still change.