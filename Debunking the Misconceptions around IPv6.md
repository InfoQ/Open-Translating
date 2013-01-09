#	Debunking the Misconceptions around IPv6
In an industry full of Next Big Things, IPv6 is the biggest one that people don’t want. That’s the conclusion that we’ve reached at WildPackets. Based on feedback from our global customer base from AMER to APAC and EMEA, IPv6 is a technology that most companies have delayed installing as long as possible. Full implementation of IPv6 will require global cooperation, from Tier 1 backbone carriers down to individual desktops. However, new IPv4 addresses are dwindling – APNIC and RIPE are exhausted, and ARIN has moved to the final pre-exhaustion phase, including new inter-region transfer rules. Pressure is building to do the transition right.

In order to make this easier, let’s look at some of the common misconceptions with this protocol.

##The elephant in the room: addressing
One of the misconceptions about IPv6 is that the addresses will be difficult to manage due to their length. The new addresses are four times longer — 128 bits instead of 32 bits. IPv4 addresses were easy to memorize, but the longer addresses seem too long to manage.

In reality, this barrier is psychological, not technological. These addresses work the same way that they always have— global, local and specific node.  The global routing prefix is the same for every computer in your network, so you’ll quickly memorize it. The local subnet is a flexible way you can organize computers by location and/or function. The node interface identifier just specified each computer within the subnet. While the interface identifier is potentially long – 64 bits – it can also be relatively short if the subnet uses structured addressing with DHCP, just like in IPv4.

The key to shorter IPv6 addresses is to maximize the number of consecutive zeroes. Number your subnets starting high, and number your nodes starting low. Leading zeroes are dropped, and consecutive zeros are replaced with  '':: '', so ''2001:0db8:0005:0000:0000:0000:0000:0018'' becomes ''2001:db8:5::18''. After understanding how IPv6 addresses work, you’ll very quickly find your IT team further shortening it to ''5::18'' – which is even shorter than an IPv4 address.

IPv6 is even easier for your users and customers – most of them will type hostnames and URLs just like they do now, and DNS will translate that into the address.  Once your DHCP and DNS are IPv6-enabled, the transition to a new address scheme is relatively easy, and certainly easier than the occasional dreaded IPv4 re-numbering.

##The word choice: It’s not a transition; it’s an addition
From a user standpoint, the shift over to IPv6 is an addition rather than a transfer. The change will not be like switching from one version of an operating system to another. As an IT administrator, you will not shut down IPv4 after enabling IPv6. That doesn’t mean things won’t break, but if there are any P1 problems, the quick back out is simply to turn IPv6 off.

I personally had an unexpected IPv6 problem in a hotel room: the WiFi connected, but the hotel captive portal login page wouldn’t load.  OmniPeek showed me that IPv6 was enabled on the network, but not on the captive portal.  Since captive portals work by redirecting web pages, I had partial connectivity to the web via IPv6, but not via IPv4.  I sighed, disabled IPv6, and was immediately online.

Since the Internet currently runs primarily on IPv4, there will be transition mechanisms like IPv6 Rapid Deployment (6rd) for quite some time. Your IPv6 support doesn’t have to be perfect. However, choosing to add it now will both demonstrate your commitment to the new technology and help IPv6 reach critical mass, reducing the awkward transition phase.

##The fail-safe: 6 to 4 fallback
The most recommended method to roll out IPv6 is with Dual Stack: use both IPv6 and IPv4 at the same time. This provides both future and backwards compatibility. If a PC has both addresses, the web browser will generally try to connect first to IPv6, then to IPv4 if IPv6 doesn’t work.

Early adopters of Dual Stack found that the fallback, though automatic, was hardly transparent. Fallback times routinely took 1-3 minutes per TCP session, which translates into a single web page loading in 15-30 minutes.

Now, this problem has been very well addressed by web browsers, and work is ongoing to generalize the solution for operating systems. Many browsers have implemented the ''Happy Eyeballs'' solution (RFC 6555), and Windows 8 is using a modified form of its Wi-Fi Internet connectivity testing to determine whether to use IPv6 for connections.

As an example of how well this fallback works in practice, after IPv6 Day in 2011, Facebook decided to keep IPv6 turned on even though the CSS part of its website didn’t support IPv6. The site still worked based on automatic fallback to IPv4 on the client side for Dual Stack hosts.

##The ever-present fear: Security, or lack thereof
A popular myth is that Network Address Translation (NAT) is a security feature, and IPv6 is insecure because it does not use NAT. NAT usually hides internal IPv4 addresses behind a single external IPv4 addresses. However, it was created to slow the exhaustion rate of IPv4 addresses, not as a security feature.

The misconception is that NAT makes a network more secure because the firewall makes it ''impossible'' for anyone on the Internet to reach the ''private'' internal IP addresses.  However, NAT itself will not prevent inbound connections or attacks. A firewall just implements policy, and a bad policy will still allow unwanted traffic.  All NAT does is stretch IPv4 addresses, break some protocols, and increase management complexity.

Removing NAT may actually improve security, since it will be easier for admins to understand what the network is doing.  I have a customer whose network requires three levels of NAT between desktops and servers, and it’s nearly impossible to audit, change firewall rules, or troubleshoot using logs.  IPv6 will restore visibility, thus simplifying management, reducing MTTR, and increasing security.

##The biggest IPv6 question: Who will let me use IPv6?
A few years ago, if you wanted IPv6, you had to use a tunnel broker. Tunnel brokers provide a VPN to carry IPv6 over the IPv4 Internet, similar to how 6rd works. World IPv6 Launch Day in 2012 encouraged ISPs to offer IPv6 directly to end customers, so tunnels would not be necessary. Now there are major companies — like AT&T, Comcast, and Time Warner Cable — that offer this natively to their subscribers. However, not every ISP is offering IPv6, and even those that do might not offer it for every service.  At home, I’m still waiting for my AT&T U-Verse connection to support IPv6.

If you are in a position to renegotiate your ISP contract(s), add IPv6 to the list of requirements. Even if your carrier doesn’t offer IPv6, asking for it will help push carriers to change. The more support that everyone has for IPv6, the sooner we’ll all overcome the transition problems.

##And For Fun: IPv6 Actually Has Two Addresses
IPv6 is not without its learning curve, and one idiosyncrasy will become apparent on your first test network. With IPv6, you will be using at least two different IPv6 addresses on every interface. Traditionally, IPv4 only used two addresses: a hardware address and an IPv4 address. With IPv6, these addresses will still exist, but IPv6 adds a second ''link-local'' IPv6 address. You and your network management tools may experience some initial confusion, but your network will actually run better with the additional address layer.

The reason for the link-local address is to fix some problems left over with Ethernet.  Switches have provided enhanced bandwidth usage by implementing targeted traffic delivery, allowing larger numbers of computers per subnet or VLAN, but some types of administrative broadcast traffic are still delivered to every connected node.  IPv6 uses the link-local addresses to replace the broadcast with multicast, and even uses targeted multicast in the hardware address.  This takes advantage of the efficiency of switches, thus completely eliminating wasteful broadcasts and increasing efficiency across the subnet.

With the shelf life of the remaining IPv4 addresses coming to an end, it is essential that we start planning for IPv6 and not get caught up in the misconceptions that often stop companies from adding this protocol. The IT world will continue to change, and the Internet is a cornerstone of that progress. Given that businesses rely heavily on their networks to perform essential day-to-day tasks, it is only fitting that the protocol behind it provides as much visibility and room for growth as possible.

##About the Author
Jim MacLeod is a Product Manager at [WildPackets](http://www.wildpackets.com/), and tweets occasionally as [@shewfig](http://twitter.com/shewfig). He has been in the networking industry since 1994. His experience includes positions in firewall and VPN setup and policy analysis, log management, Internet filtering, anti-spam, intrusion detection, network monitoring and control, and packet sniffing.

##About WildPackets
[WildPackets](http://www.wildpackets.com/) develops hardware and software solutions that drive network performance, enabling organizations of all sizes to analyze, troubleshoot, optimize, and secure their wired and wireless networks. WildPackets products are sold in over 60 countries and deployed in all industrial sectors. Customers include Boeing, Chrysler, Motorola, Nationwide, and over 80 percent of the Fortune 1000. WildPackets is a Cisco Technical Development Partner (CTDP).

原文链接：[Debunking the Misconceptions around IPv6](http://www.infoq.com/articles/Misconceptions-IPv6)