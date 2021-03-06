[
	{
		"funcName":"Multiple-network Interface & Multiple IP",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Multiple network card",
				"funcP":"According to the VM instance type, a single VM can support to bind up to eight Elastic Network Interfaces which can respectively belong to different subnets under the same VPC."
			},
			{
				"funcName":"",
				"funcTitle":"Multi-Private IP",
				"funcP":"According to the VM instance type, each Elastic Network Interface of the VM supports up to 21 intranet IP addresses, and all Private IP addresses on the same Elastic Network Interface belong to the same subnet."
			},
			{
				"funcName":"",
				"funcTitle":"Multi EIP",
				"funcP":"Each Private IP address is assigned to an Elastic Network Interface. The Private IP address can be associated with an EIP address."
			}
		]
	},
	{
		"funcName":"Migration of Network Interface Card",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Territory-level network card",
				"funcP":"Support Elastic Network Interface of region class attribute, breaking through the limitations of available zones of traditional Elastic Network Interfaces. An Elastic Network Interface can be migrated elastically between VMs in different available zones in VPC."
			},
			{
				"funcName":"",
				"funcTitle":"Flexible migration",
				"funcP":"The Elastic Network Interface can be flexibly migrated between the VMs in the VPC. When the Elastic Network Interface is migrated, the assigned Private IP address, EIP address, and security group are retained."
			}
		]
	},
	{
		"funcName":"Security for Business",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Independent security policy",
				"funcP":"Support security policy control of network interface level. An Elastic Network Interface can associate to 5 security groups, to achieve precise control of service traffic"
			},
			{
				"funcName":"",
				"funcTitle":"Business traffic separation",
				"funcP":"A VM can be mounted with multiple Elastic Network Interfaces. The traffic of a specific service can be carried by a specific Elastic Network Interface. Different Elastic Network Interfaces use security group policies respectively, to accurately separate service traffic and security policies."
			}
		]
	},
	{
		"funcName":"Routing Control",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Subnet routing",
				"funcP":"A VM can attach multiple Elastic Network Interfaces that belong to different subnets. Each subnet can independently set up an identity and access management policy and a route forwarding policy to achieve security isolation between user services and the network."
			},
			{
				"funcName":"",
				"funcTitle":"Machine routing",
				"funcP":"A fine routing policy can be set up inside the VM. The specific service traffic can be forwarded by a specific Elastic Network Interface or a specific IP address."
			}
		]
	}
]