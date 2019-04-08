# Networks

## Bridge

### What is Bridge?
A bridge is a device that separates two or more network segments within one logical network (e.g. a single IP-subnet).

A bridge is usually placed between two separate groups of computers that talk with each other, but not that much with the computers in the other group. A good example of this is to consider a cluster of Macintoshes and a cluster of Unix machines. Both of these groups of machines tend to be quite chatty amongst themselves, and the traffic they produce on the network causes collisions for the other machines who are trying to speak to one another.

The job of the bridge is to examine the destination of the data packets one at a time and decide whether or not to pass the packets to the other side of the Ethernet segment. The result is a faster, quieter network with less collisions.

The bridging code decides whether to bridge data or to drop it not by looking at the protocol type (IP, IPX, NetBEUI), but by looking at the MAC-address unique to each NIC.

Important: It's vital to understand that a bridge is neither a router nor a fire-wall. Spoken in simple term a bridge behaves like a network switch (i.e. Layer 2 Switch), making it a transparent network component (which is not absolutely true, but nearly). Read more about this at Section 4.

In addition, you can overcome hardware incompatibilities with a bridge, without leaving the address-range of your IP-net or subnet. E.g. it's possible to bridge between different physical media like 10 Base T and 100 Base TX.

My personal reason for starting to set up a bridge was that in my work I had to connect Fast Ethernet components to a existing HP Voice Grade network, which is a proprietary networking standard.

More details via that [link](https://www.tldp.org/HOWTO/BRIDGE-STP-HOWTO/what-is-a-bridge.html)
