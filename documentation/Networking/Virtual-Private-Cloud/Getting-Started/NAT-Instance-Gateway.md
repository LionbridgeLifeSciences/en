## **NAT Instance Gateway**

### Features

If multiple VMs in the same VPC have access to the Internet at the same time and the EIP resources are insufficient, you can solve this problem by creating a NAT instance gateway. JD Cloud supports self-built NAT instance gateway to realize SNAT function.

Use Restrictions: The self-built NAT instance gateway shares quotas with the VM.



### **Overview**

A NAT instance gateway is an instance gateway that translates Private IP addresses and EIP addresses in a VPC. It is a way for cloud resources without EIP in the VPC to access the Internet (but it does not support Internet active access to the VPC). The typical application scenarios of the JD Cloud VPC NAT instance gateway are as follows:

- Large bandwidth, high availability public network access. For the public network access application scenarios where users require to large bandwidth, large EIP usage, and large deployment services, JD Cloud NAT instance gateway can meet the demands.
- Secure public network access. The NAT instance gateway of JD Cloud VPC provides IP security conversion. If the user wants to hide the EIP of the machine in the VPC to avoid exposing its network deployment and wants to access the public network, then the JD Cloud NAT instance gateway can meet such needs.



### **Use of NAT instance gateway and Elastic IP**

#### **Solution1: Only use NAT instance gateway**

The VM is not associated to the elastic EIP, and all access to Internet traffic is forwarded through the NAT instance gateway. In this solution, the traffic of the VM accessing the Internet is forwarded to the NAT instance gateway through the intranet. Therefore, the VM is not limited by bandwidth limit of the public network bandwidth. The network traffic cost generated by the NAT instance gateway does not occupy the public network bandwidth export of VM.

##### **Solution 2: Use elastic EIP only**

The VM is only associated to the elastic EIP and does not use the NAT instance gateway. In this solution, all Internet access traffic of the VM flows out through the elastic EIP , which is limited by the bandwidth limit of the public network bandwidth when purchases the VM. The related costs generated by accessing the public network are determined according to the VM network charging mode.

#### **Solution 3: Simultaneous use of NAT instance gateway and elastic EIP**

The VM is associated to the elastic EIP, and the subnet route accesses the Internet traffic points to the NAT instance gateway. In this solution, all the traffic that the VM actively accesses the Internet is only forwarded to the NAT instance gateway through the intranet. The return packet is also returned to the VM through the NAT instance gateway. This part of the traffic is not affected by the bandwidth limit of the public network bandwidth when the VM purchases. The network traffic cost generated by the NAT instance gateway does not occupy the public network bandwidth export of the VM. If the traffic from the Internet actively accesses the elastic EIP of the VM, the VM return packet is uniformly returned through the elastic EIP. The resulting public network outgoing traffic is limited by the upper limit of the bandwidth of the public network bandwidth when the VM purchases. The related costs generated by accessing the public network are determined according to the VM network charging mode.

**NAT Instance Gateway Configuration Description**

**Purpose**: Multiple machines on the same VPC access the public network through a machine that acts as a NAT instance gateway to share IP bandwidth.

**Simulation Scenario**: Assume that there is currently a VPC named NAT01 (10.1.0.0/16) and affiliated two subnets: SNAT01 (10.1.1.0/24) and SNAT02 (10.1.2.0/24). There are multiple machines under SNAT02. Multiple machines under the subnet SNAT02 can access the Internet as the machine of the NAT GW through the subnet SNAT01.



**Step 1: Create a machine as a NAT instance gateway under the SNAT01 subnet**

![](/image/Networking/Virtual-Private-Cloud/Getting-Started/NAT-Instance-Gateway/step1.png)

Create a machine under SNAT01 and select CentOS-7.2 64-bit NAT Gateway for image

![](/image/Networking/Virtual-Private-Cloud/Getting-Started/NAT-Instance-Gateway/step2.png)



Select VPC to which it belongs as NAT01 and the subnet is SNAT01

Configure the EIP type and bandwidth

The machine is named as SNAT01

![](/image/Networking/Virtual-Private-Cloud/Getting-Started/NAT-Instance-Gateway/step3.png)



After the creation is complete, you can see the machine status of different subnets under the same VPC on the machine list page



**Step 2: Configure the route table of subnet SNAT02 points to the NAT instance gateway**

![](/image/Networking/Virtual-Private-Cloud/Getting-Started/NAT-Instance-Gateway/step4.png)



View the route table associating to the subnet through subnet SNAT02

![](/image/Networking/Virtual-Private-Cloud/Getting-Started/NAT-Instance-Gateway/step5.png)



Edit the Route Table: - Next Hop Type: VM, next hop machine: SANT01

After the configuration is complete, all machines on the subnet SNAT02 can access the public network through the SANT01 function as the NAT instance gateway.

Similarly, other subnet routes under the same VPC can be configured.

**Note: If the machine needs to communicate through the NAT instance gateway, you cannot select a machine in the subnet that is associated to the same route table as the subnet where the machine resides as the NAT instance gateway.**