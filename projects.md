---
layout: page
title: Projects
permalink: /projects/
---

# TCP Proxy in rust

[Challenge](https://github.com/fly-hiring/platform-challenge)

#### Checkpoint 0

1. Single threaded implentation using simple tcplistener.
1. Tcplistener accepts connection and we relay data from downstream to upstream.

#### Checkpoint 1

1. Single listner port and single upstream.
1. Epoll implemetation but can only support one connection at a time.

#### Checkpoint 2

1. Single listner port and single upstream.
1. Can handle multiple parallel connections and uses epoll.


#### Checkpoint 3

The TCP Proxy can
1. Reads the config file and sets itself up accordingly with the listening ports and the upstreams the customer want to forward the request.
1. Currently it expects the upstream server is alwasys up and round robins among the avilable.

#### Checkpoint 4

1. Handle stream half close.
1. And do current state based upstream selection and fallback to next upstream server.

#### Checkpoint 5

1. Implement closing of idle tcp sessions.
1. The idle events are processed in main event loop itself.

#### Checkpoint 6
