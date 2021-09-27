# Concierge

Routes BGP to a set of connected peers.

Specific use case is for an IXP (Internet Exchange Point) to act as a route server, but there may also be other uses.

There will be a strong emphasis on simplicity, aggregate speed, and being incredibly opinionated as to supported peers. It will only support a small subset of BGP Path Attributes, such as AS Path, MED, and Communities (including large and extended).

Written in Go, any choice of OS platform or CPU architecture should be possible, with no external runtime dependencies.

Examples of planned features include:

* Graceful restart enabled by default. [RFC4724](https://datatracker.ietf.org/doc/html/rfc4724)
* Advertisement of multiple paths *to* a peer. [RFC7911](https://datatracker.ietf.org/doc/html/rfc7911)
* Live prefix-list reloading, generated externally.
* RPKI Origin Validation. [RFC6480](https://datatracker.ietf.org/doc/html/rfc6480] and others.
* Sampling of data at both ingress and egress, through either MRTDump, BMP, or simple text logging.
* Real-time looking glass interface, available via API only.
* GTSM (TTL Security) automatically enabled per session when observed.
* Pluggable filter module support for more complex checks (RPSL etc).
* Automatic "next-hop" constraints to ensure the received information comes from a valid recipient.

Examples of features intended never to be implemented include:

* Exporting the routes to the kernel. This is not a packet router.
* Import or advertisement of static routes. This is not a BGP injector.
* Any kind of TCP authentication, be it MD5 or AO.
* Support for any other AFI/SAFI combinations than IPv4 Unicast and IPv6 Unicast.

It is very likely that this will not gain widespread usage. It is very likely that this will not be completed. It is very likely that this will cause arguments. It is very likely that this is a terrible choice of name for the project. It is very likely that this is a fun project to learn from!

