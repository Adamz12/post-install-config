<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Configure osTicket, post-installation](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Learn the interfaces: Differentiate between the Admin/Analyst (SCP) login and the End User portal.
- Set up agent hierarchy: Create Roles, Departments, and Teams (e.g., Supreme Admin, SysAdmins, Online Banking).
- Control user access: Require registration for ticket creation and add Agents (Jane, John) and End Users (Karen, Ken).
- Define SLAs: Configure Service Level Agreements (Sev-A, Sev-B, Sev-C) with appropriate response times.
- Create Help Topics: Add categories (Business Critical Outage, Password Reset, etc.) for proper ticket routing.

<h2>Configuration Steps</h2>
<p>
In this tutorial, you’ll walk through the final steps of setting up and configuring osTicket so it’s ready for real-world use. We’ll start by accessing the Admin/Analyst (SCP) interface and the End User portal to see the difference between agent and customer views. Then you’ll create a basic help-desk structure—defining Roles (like Supreme Admin), Departments (e.g., SysAdmins), and Teams (such as Online Banking)—before locking down ticket creation so only registered users can open tickets. Next, you’ll add Agents (Jane, John) and End Users (Karen, Ken) to their respective panels, set up Service Level Agreements (Sev-A, Sev-B, Sev-C) to enforce response times, and finally create Help Topics (Business Critical Outage, Password Reset, etc.) so incoming tickets route correctly. By the end, your osTicket instance will be fully organized and ready to handle support requests.
</p>
<h4>1. Configure Roles</h4>
<p>
On the Windows VM, open a web browser and navigate to: http://localhost/osTicket/scp/login.php 


When prompted, enter: admin credentials

Click Login to reach the osTicket dashboard.
</p>
<p>
<img src="https://i.imgur.com/emBscJG.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the osTicket Admin Panel, go to Agents → Roles and click Add New Role. Name the role Supreme Admin and check every permission box so this role has full access to all areas of the system (tickets, agents, staff, settings, etc.)
</p>
<br />

<p>
<img src="https://i.imgur.com/cQRHrLO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Admin Panel, open Agents → Departments and click Add New Department. Name it SysAdmins, set the parent to Top Level so it sits at the root of the hierarchy, and click Create Department. Agents in the SysAdmins department will then have visibility into every ticket across all departments.
</p>
<br />

<p>
<img src="https://i.imgur.com/45STrWb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Admin Panel, navigate to Agents → Teams and click Add New Team. Name the team Online Banking and leave the agent list empty for now, then click Create Team. This sets up the “Online Banking” team so you can assign agents later as needed.
</p>
<p>
<img src="https://i.postimg.cc/8PfKHhpm/creating-online-banking.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
In the Admin Panel, navigate to Settings → User Settings, find “Require registration and login to create tickets”, and uncheck it. Click Save Changes. This allows any visitor to submit a ticket without first registering.
</p>
<p>
<img src="https://i.postimg.cc/rF2nfDD6/ensure-unchecked.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
In the Admin Panel, go to Agents → Add New. For Jane, enter:

- Name: Jane

- Email: jane@gmail.com

- Username: jane

- Password: Password1

- Department: SysAdmins

- Role: Supreme Admin (full access)

- Team: Online Banking
 Click Create Agent to save.

Next, click Add New again for John and enter:

- Name: John

- Email: john@gmail.com

- Username: john

- Password: Password1

- Department: Support

- Role: View Only (restricts him to ticket viewing)

- Team: (leave blank)
Click Create Agent. Now Jane has full admin rights and belongs to the Online Banking team, while John can only view tickets and isn’t assigned to any team.
</p>
<p>
<img src="https://i.postimg.cc/9QhG3T22/adding-agents.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
In the Agent Panel, go to Users → Add New, then:

- For Karen, set Name to Karen and Email to karen@gmail.com, then click Create User.

- For Ken, set Name to Ken and Email to ken@gmail.com, then click Create User.
</p>
<p>
<img src="https://i.postimg.cc/9QhG3T22/adding-agents.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
