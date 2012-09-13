#The Software-defined Datacenter Has Arrived

**SUMMARY:** 

VMware and Microsoft provide solutions for software-defined datacenters where all resources – compute, storage, availability, networking and security – are virtualized and automated. This article focuses on the latest additions: virtualized networking and security.

-----

VMware and Microsoft provide solutions for software-defined datacenters where all resources – compute, storage, availability, networking and security – are virtualized and automated. This article focuses on the latest additions: virtualized networking and security.

VMware and Microsoft are making the final steps in providing a completely automated datacenter which can be the basis for cloud solutions, either public, private or hybrid ones. VMware calls the technology a [Software-defined Datacenter](http://cto.vmware.com/interop-and-the-software-defined-datacenter/) (SDDC), while Microsoft speaks of [Software-defined Networking](http://blogs.technet.com/b/windowsserver/archive/2012/08/22/software-defined-networking-enabled-in-windows-server-2012-and-system-center-2012-sp1-virtual-machine-manager.aspx) (SDN), the later referring to the last piece of the datacenter puzzle that needed to be automated. Computing, storage and availability resources have been automated for many years, but companies are working on virtualizing and automating networking and its associated policies and security. Two such solutions are VMware [vCloud Suite](http://www.vmware.com/company/news/releases/vmw-vmworld-vcloud-suite-082712.html)  and Microsoft Windows Server 2012 and System Center 2012 SP1, Virtual Machine Manager.

Recently announced at [VMware World 2012](http://www.vmworld.com/index.jspa), [vCloud Suite 5.1](http://www.vmware.com/company/news/releases/vmw-vmworld-vcloud-suite-082712.html) offers the possibility to build a datacenter with all resources virtualized, pooled and automated including networking and security. [vCloud Networking and Security](http://www.vmware.com/products/datacenter-virtualization/vcloud-network-security/overview.html) creates multi-tenant virtual networks that are dynamically modified to adapt to new requirements, including virtual firewalls, VPN, load balancing and [VXLAN](http://blogs.cisco.com/datacenter/digging-deeper-into-vxlan/) networks. Allwyn Sequeira, VP/CTO, Security and Networking in the Cloud Infrastructure BU at VMware, explains the [key attributes of software-defined networking](http://cto.vmware.com/unveiling-sdn-and-sdsec-architectures-at-vmworld-2012/):

>+ ABSTRACTION. The network is abstracted as a set of network ports (and virtual NICs on the VM side). Security is abstracted as a set of port firewalls and end-point introspection. These abstractions are instantiated via virtual switches (vSwitch) and virtual firewalls (vShield) respectively and deployed in a scale out fashion on each host hypervisor. The network and security virtualization layer effectively untethers the VDC from the underlying physical network and firewall architecture, and provides a logical foundation to build the stack.  
+ POOLING. vSwitches are pooled into virtual distributed switches (VDS). Ports are pooled into port groups. Logical networks leverage these port groups and can be instantiated across the data center (VXLAN). Port firewalls are realized in vShield App or Edge. VM-based security is available via vShield Endpoint and endpoint security partner offerings. Because of the scale out nature of deployment, these pools are elastic and data center wide, and available on demand to be allocated to tenants or app owners.  
+ SERVICE INSERTION. The platform must be extensible to enable instant insertion of additional abstractions into the virtual plane e.g. encryption, intrusion detection & prevention, anti-virus, application delivery controllers, data leakage prevention, wan optimization control, monitoring tools, and other L4-7 services. The network and security virtualization layer provides a logical context for the instant insertion of such services.  
+ AUTOMATION. Just as VMs were the container for server virtualization, the Virtual Data Center (VDC) is the container for the SDDC. VDC deployments are completely automated via vCloud Director, and handle policy-based deployment of compute and storage, delegating networking and security deployments to the vCloud Networking & Security sub-system. A centralized command and control mechanism (vShield Manager) takes inventory of all the abstractions & pools, and is responsible for managing and mapping these pools into the needs of higher level entities like tenants or apps, and aligning with higher level virtual containers. Notions of multi-tenancy, isolation, elasticity, and programmability via RESTful interfaces are also handled here.

In a recent blog post, Sandeep Singhal, GM of the Windows Networking team, and Vijay Tewari, Group Program Manager in the SCVMM team at Microsoft, discuss the [software-defined networking capabilities](http://blogs.technet.com/b/windowsserver/archive/2012/08/22/software-defined-networking-enabled-in-windows-server-2012-and-system-center-2012-sp1-virtual-machine-manager.aspx) built into Windows Server 2012 and System Center 2012 SP1, explaining how their virtualized networks allows customers to move their datacenters into the Windows Azure cloud without changing IP addresses:

>[Hyper-V Network Virtualization](http://blogs.technet.com/b/windowsserver/archive/2012/04/16/introducing-windows-server-8-hyper-v-network-virtualization-enabling-rapid-migration-and-workload-isolation-in-the-cloud.aspx) delivers network flexibility for the cloud by providing the ability to create multi-tenant virtual networks on a shared physical network.  Each tenant gets a complete virtual network, including multiple virtual subnets and virtual routing.  (Some network virtualization solutions out there assume the tenant only has a single subnet!)  On each host, Hyper-V uses dynamically updatable SDN policies to associate a tenant network and properly direct traffic to the destination. The SDN policy also determines which VM’s these tenant VM’s are allowed to communicate with, providing the requisite isolation.  As a result, Hyper-V Network Virtualization allows tenant workloads to be placed anywhere in the physical datacenter.  Tenant networks even can use private IP addresses (which might overlap with addresses used by other tenants), allowing tenants to rapidly migrate their existing workloads to the cloud by bringing their own IP addresses.  In fact, Windows Server 2012 supports interoperable cross-premise connectivity, so you can seamlessly link your subnets in the public cloud back to your local network. …

>Our SDN solution is further enabled through rich traffic control policies on the Hyper-V virtual switch.  On a per-VM basis, you can configure security policies that limit the types of traffic (and destinations).  You can reserve bandwidth to particular VMs, ensuring that mission-critical services can always access necessary network capacity.  You can even apply bandwidth caps, allowing you to avoid traffic starvation or enforce a variety of charging models.  What’s more, these network control policies are dynamic, so they can be adjusted in real-time.

Singhal and Tewari claim that their networking virtualization solution has been tested in production within Azure datacenters “orchestrating communication for tens of thousands of VMs running on over 4000 physical hosts.” On the other hand, VMware’s solution claims to be built on open standards allowing third party services, including using hardware and virtual appliances, to be inserted in various places within the virtual network in order to access the traffic, as detailed in this [whitepaper](http://www.vmware.com/files/pdf/products/vcns/vCloud-Networking-and-Security-Overview-Whitepaper.pdf).

原文链接：<http://www.infoq.com/news/2012/08/Software-defined-Datacenter>