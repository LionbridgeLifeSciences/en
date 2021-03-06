[
	{
		"funcName":"High-available deployment across availability zones",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Cross-availability Zone",
				"funcP":"When creating a high availability group, you need to support the assignment of multi-availability zone. The high availability group will ensure that the VMs in the group are evenly distributed in the allocated zone. When a VM is created, the number of VMs will be automatically selected in the configured zone. It needn’t you to assign availability zone."
			},
			{
				"funcName":"",
				"funcTitle":"Single High Availability Group Multiple Fault Domain",
				"funcP":"The fault domain is a physical resource pool that is isolated from each other. The same high availability group allocates at least five fault domains in a single available zone. Hardware faults or scheduled maintenance in one fault domain do not affect other fault domains, so as to reduce the risk that all VMs in your service are not available at the same time. When you deploy your business, it is recommended that you choose a high availability group for each type of service for deployment, and the number of VMs in the high availability group shouldn’t less than two sets."
			}
		]
	},
	{
		"funcName":"Resource Monitoring",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Multi-dimensional monitoring",
				"funcP":"Based on multi-dimensional monitoring of VMs in high availability groups, visual chart display is convenient for users to grasp the usage and operation status of VM resources in real time. Automatically report CPU utilization rate, memory utilization rate and disk read/write throughput and other monitoring data, allowing you to monitor resources using different statistical methods, such as average and maximum values etc."
			}
		]
	},
	{
		"funcName":"Automatic Expansion",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Alarm scaling policy",
				"funcP":"When your service has business fluctuation, it can support you configure the alarm scaling policy based on the monitoring indicators (such as CPU and memory usage rate). When the scaling condition is met, the VM is automatically triggered to be added or deleted the VM. Hence, it could cope with business load change flexibly and guarantee business service capability, and save business deployment cost."
			},
			{
				"funcName":"",
				"funcTitle":"Timing scaling strategy",
				"funcP":"You can plan the number of VMs in a high availability group and configure a timing scaling policy to add or delete VMs at regular time under predictable business fluctuations. If periodic fluctuations occur, it also supports repetition cycle by day/week/month."
			},
			{
				"funcName":"",
				"funcTitle":"Scaling record",
				"funcP":"If auto-scaling is enabled in the high availability group, the scaling activity triggered by the scaling strategy will be recorded to help you grasp the activities of the automatic scaling, including the scaling content, the scaling status, and the starting and ending time. This allows you to query the history record by time."
			}
		]
	},
	{
		"funcName":"Efficient Management",
		"funcContent":[
			{
				"funcName":"",
				"funcTitle":"Configure Instance Template",
				"funcP":"It should configure instance templates when creating high availability group, and startup templates to record VM required configuration, such as mirror image, VM specification and network information, and it will be based on startup template configuration to create VM and needn’t to assign again by you, and could guarantee VM consistency of your same service with fast deployment. \n"
			}
		]
	}
]