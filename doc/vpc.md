
# Virtual Private Cloud

[Virtual Private Cloud](https://aws.amazon.com/vpc/)

Definining Virtual Private Cloud
  - It makes a public code (e.g. AWS) act "as if" it were private cloud
  - It is a logical construct. VPC endpoints connect to AWS resources. The VPC endpoint can be controlled by policies.
  - VPN Connections can be made to the VPC
  - Applications can run in the VPC or on-premises
  - Subnets can be created within the VPC

Multiple VPCs can be interconnected using peering.
Distinguish between old use of an endpoint (any way to access a server throug a network) with AWS defining an endpoint as a channel secured by a policy to access an AWS resource.

All AWS accounts have a default VPC. One in each region. AMZ recoomends do not delete.

Features of VPC
  - Dynamic private IP
  - Dynamic public IP
  - AWS-provisioned DNS names - not human friendly
  - Private DNS names
  - Public DNS names

## Amazon VPC Applications

[AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html)

[Virtual Private Clouds](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
  - [Your VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
    - Create a VPC -> VPCs do not talk to one another unless routes are built between them.
    - Classless Inter-Domain Routing (CIDR) - creates a private IPv4
    - Create a Subnet -> dedicates a set of the IPs that belong within a VPC

- Configuring DHCP Options
  - On premise, DHCP is setup by assigning ranges of IP addresses. AWS will have already done this when you defined a subnet.
  - So you need to [define a DHCP option for a subnet](https://console.aws.amazon.com/vpc/home?region=us-east-1#dhcpOptions:). A DHCP option is a configuration parameter related to an IP address protocol, the protocol we use to get an IP addresses in all the rest of our configuration on the device that receives the configuration set, so that it could be a client. It could be a server
  - Can define a DHCP option set name (recommended), domain name, domain name servers, network time protocol (NTP) servers, NetBIOS name servers and NetBIOS node types. NetBIOS is not frequently used today.

[Elastic IP addresses (EIPs)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-eips.html)

EIP is a public IP address from the VPC and is allocated to an AWS region until it is released.
You are charged for it.
Network interfaces consume EIPs
EIPs can be moved between instances in the same region.
A way to ensure an EIP is not used (so that you can release it and not pay for it) is to check that there is no instance associated with it.

[Elastic Network Interface (ENIs)](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ElasticNetworkInterfaces.html)

A virtual network interface attached to an instance.
Only available w/i a VPC
associated with a subnet
allows dual homing - a network node that can have more than 1 home. Examples:
  - Internet router has a home on the internet and a home on your private network
  - Firewall has a home on the untrusted parts of the network and and a home on the trusted parts of the network.
General practice: 1 public address with multiple private addresses.
It is a virtual network network card installed on a VPC, where it can be given an IP address on any subnet or the public facing internet 

- Endpoints


## VPC Peering

Suppose you have 2 VPCs. How do you enable them to communicate?

[VPC Peering Guide](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)
* Enables 2 VPCs to communicate
* It is not transitive

[VPC Peering Basics](https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-basics.html)

Establishing a VPC connection

1. Owner of *requester* VPC sends a request to the owner of the *accepter* VPC to create the VPC peering connection.
    * Requires owner role
    * IP [CIDR](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) blocks in each VPC cannot overlap
        * E.g. `10.0.0.0/16` and `192.168.0.0/16` overlap
    * Therefore each VPC should use a unique CIDR block
2. The owner of the accepter VPC accepts the VPC peering connection request to activate the VPC peering connection.
3. To enable the flow of traffic between the VPCs using private IP addresses,
   the owner of each VPC in the VPC peering connection must manually add a route to one or more of
   their VPC route tables that points to the IP address range of the other VPC (the peer VPC).
4. If required, update the security group rules that are associated with your instance to
   ensure that traffic to and from the peer VPC is not restricted.
   A security group rule in AWS is like a firewall rule.
5. By default, if instances on either side of a VPC peering connection address each other using
   a public DNS hostname, the hostname resolves to the instance's public IP address.
   To change this behavior, enable DNS hostname resolution for your VPC connection.
   After enabling DNS hostname resolution, if instances on either side of the VPC peering connection
   address each other using a public DNS hostname, the hostname resolves
   to the private IP address of the instance.


## Amazon VPC Security

### Security Groups

[VPC Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) acts like
a firewall.
    * Applied to an instance in a VPC
    * Applied to an instance not a subnet
 They also define allowed traffic flows
    * Ingress (entrance)
    * Egress (exit)

* Storage Groups
    * Only supports Allow rules. The default is to Deny. These are properties of a Closed-to-Open system
    * It uses stateful processing
* Network access control lists (NACLs)
    * Applied on subnets
    * It uses stateless processing
    * Supports both Allow and Deny rules.
    * Rule number defines precedence.
        * Lowest numbered rules first
        * First match applies


### Network Address Translation (NAT)

### Gateways (VPGs and CGWs)

### VPN Configuration Options

## VPC Resources

All VPC Resources are the building blocks to build a network in the cloud

### [Virtual Private Clouds](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

- [Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)
- [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)
- [Egress Only Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html)
- [Carrier Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/Carrier_Gateway.html)
- [DHCP Options Set](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_DHCP_Options.html)
- [Elastic IPs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-eips.html)
- [Managed Prefix Lists](https://docs.aws.amazon.com/vpc/latest/userguide/managed-prefix-lists.html)
- [Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html) appears to be part of AWS PrivateLink
- [Endpoint Services](https://docs.aws.amazon.com/vpc/latest/privatelink/endpoint-service.html) appears to be part of AWS Private Link
- [NAT Gatweways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)
- Peering Connections

### [Security](https://docs.aws.amazon.com/vpc/latest/userguide/security.html)

- [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
- [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)

### Reachability

- [Reachability Analyzer](https://docs.aws.amazon.com/vpc/latest/reachability/what-is-reachability-analyzer.html)


### [AWS Network Firewall](https://docs.aws.amazon.com/network-firewall/)

- Firewalls
- Firewall policies
- Network Firewall rule groups


### Virtual Private Network (VPN)

- Customer gateways
- Virtual Private Gateways
- Site-to-Site VPN Connecitons
- Client VPN Endpoints

### [Transit Gateways](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)

- Transit Gateways
- Transit Gateway Attachments
- Transit Gateway Route Tables
- Transit Gateway Multicast
- Network Manager


### [Traffic Monitoring](https://docs.aws.amazon.com/vpc/latest/mirroring/what-is-traffic-mirroring.html)

- Mirror Sessions
- Mirror Targets
- Mirror Filters

