<h1>Active Directory Home Lab</h1>

 
<h2>Description</h2>
Active Directory (AD) stands out as a widely recognized directory service from Microsoft. It operates as a centralized database, effectively organizing and overseeing network assets within Windows environments. AD plays a critical role in network management, offering a structured framework for user authentication, authorization, and resource oversight. This empowers IT administrators to efficiently govern access, uphold security protocols, and optimize user and device administration within their network. Thanks to its robust capabilities in domain management, group policy application, and directory services, Active Directory proves indispensable for ensuring the reliability, security, and scalability of Windows-based networks in various professional settings.

<br />
<h2>Summary of my next steps throughout the project</h2>

Step 1: Oracle VirtualBox Installation

•	Start by visiting the official Oracle VirtualBox website at https://www.virtualbox.org/.

•	Download the VirtualBox installer compatible with your operating system (e.g., Windows, macOS, Linux).

•	Execute the installer and carefully follow the installation instructions provided to complete the VirtualBox setup.
<br />

Step 2: Acquire Windows 10 and Server 2019 ISOs

•	Obtain the necessary Windows 10 and Windows Server 2019 ISO files from trusted sources, such as the official Microsoft website.

•	Save these ISO files to a location on your local computer.

<br />

Step 3: Setting Up the Domain Controller Virtual Machine 

1.	Launch Oracle VirtualBox.
2.	Create a new virtual machine by clicking "New."
3.	Assign a name to your virtual machine, for example, "DomainController."
4.	Select "Windows" as the Type and "Windows Server (64-bit)" as the Version.
5.	Allocate an appropriate amount of memory (RAM) based on your system's capabilities (e.g., 2 GB or more).
6.	Create a new virtual hard disk (VHD) or use an existing one.
7.	Configure two network adapters for the virtual machine in the "Settings":
•	Adapter 1: Set to "NAT" for internet access.
•	Adapter 2: Set to "Internal Network" to facilitate private communication with clients.
8.	In the VM settings, attach the Windows Server 2019 ISO as a virtual optical disk.
<br />

Step 4: Installation of Windows Server 2019
1.	Begin the Domain Controller VM.
2.	Follow the on-screen instructions during the Windows Server installation, selecting your preferred language, time settings, keyboard layout, and entering your license key when prompted.
3.	When prompted, choose the virtual hard disk you previously created.
4.	Progress through the installation wizard to finalize the Windows Server setup.
5.	Manually configure an IP address for the internal network adapter, e.g., "192.168.1.1."
<br />

Step 5: Active Directory Installation and Configuration
1.	Log in to the Windows Server after installation.
2.	Open "Server Manager."
3.	Access "Add roles and features" in "Server Manager."
4.	Opt for "Active Directory Domain Services" and follow the on-screen instructions to install.
5.	Upon completion, promote the server to a domain controller.
6.	Configure your desired domain name (e.g., "mydomain.local").
7.	Establish routing to enable private network clients to access the internet through the domain controller.
<br />

Step 6: DHCP Configuration on the Domain Controller
1.	Within "Server Manager," navigate to "Add roles and features."
2.	Add the "DHCP Server" role and configure it using the provided wizard.
3.	Define the scope for the internal network and activate DHCP services.
<br />

Step 7: User Creation via PowerShell Script
1.	Create a PowerShell script (e.g., "CreateUsers.ps1") containing the necessary code for generating user accounts in Active Directory. You can customize this script as required.
2.	Execute the script from the PowerShell console.
<br />

Step 8: Setting Up the Windows 10 Client Virtual Machine
1.	Create a new VM for the Windows 10 client, following a setup similar to that of the Domain Controller.
2.	Attach the Windows 10 ISO as a virtual optical disk.
3.	Install Windows 10 on the client VM, configuring it to use DHCP.
<br />

Step 9: Joining the Windows 10 Client to the Domain
1.	Initiate the Windows 10 VM.
2.	Join it to the previously established domain ("mydomain.local").
3.	Access the system using one of the domain user accounts you created earlier.

<br />
Following these steps, you will successfully establish a virtual network environment featuring a domain controller, Active Directory, DHCP services, and a Windows 10 client. Additionally, you will gain valuable experience in PowerShell scripting and have a fully functional environment for further exploration and learning.


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 

<h2 align="center">Program walk-through:</h2>
<b>The network diagram that I'm going to use for this project</b> <br/> 
<img src="https://ibb.co/m8d0JyQ" height="80%" width="80%" alt="Network Diagram"/>




