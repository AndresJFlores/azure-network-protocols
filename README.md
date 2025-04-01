<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Actions and Observations</h2>
<p>
Creating a resource group, Windows 10 virtual machine, and a Linux virtual machine. (Making sure both VMs are under the same Virtual network)
</p>

<p>
  
![CCL2_AL2 1](https://github.com/user-attachments/assets/012652cf-68d4-4a05-a62a-a103f7db6d1b)

</p>

<p>
In the Windows 10 system, I installed Wireshark and started a packet capture.
</p>

<p>
  
![CCL2_AL2 4](https://github.com/user-attachments/assets/fee3ad8c-38d1-4eea-bfee-64bf7b1f8302)

</p>

<p>
Obtained the Private IP address of the Linux system, filtered Wireshark to ICMP traffic only, and attempted to ping the Linux system.
</p>

<p>

![CCL2_AL2 5](https://github.com/user-attachments/assets/6c79c844-b0c9-4e58-8d7f-cb844653aa35)

</p>

<p>
Configuring the firewall of the Linux system to not recieve any ICMP traffic.
</p>

<p>

![CCL2_AL2 7 1](https://github.com/user-attachments/assets/172be43e-36fc-4965-a13d-e765389db4da)

![CCL2_AL2 7 2](https://github.com/user-attachments/assets/dfc90c84-1154-48fd-911f-8765870c363e)

</p>

<p>
Back in the Windows VM, pinged the Linux VM and observed the ICMP traffic.
</p>

<p>

![CCL2_AL2 7 3](https://github.com/user-attachments/assets/c26709dc-4c2d-4928-9b96-4337e717561a)

</p>

<p>
Removing the security rule from the linux VM and observing the ICMP traffic from the Windows VM
</p>

<p>

![CCL2_AL2 8 1](https://github.com/user-attachments/assets/f8914533-431c-444e-bf45-4e7162c9a681)

![CCL2_AL2 8 2](https://github.com/user-attachments/assets/22dc289f-0075-477d-a641-496515f7d27c)

</p>

<p>
Filtering Wireshark for SSH traffic only. Used powershell to connect to the Linux VM using its private IP address via SSH
</p>

<p>

![CCL2_AL2 9 1](https://github.com/user-attachments/assets/89eb4f4f-de74-4186-afe9-a0c4745cd7f9)

![CCL2_AL2 9 2](https://github.com/user-attachments/assets/0510cdc3-283a-47c1-96e8-6d8e9d495085)

![CCL2_AL2 9 3](https://github.com/user-attachments/assets/c1eb1d9b-8e57-4fa5-9d91-18d362756f12)

</p>

