<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Install Configuration</h1>

<p>
This project demonstrates the post-install configuration of the open-source help desk ticketing system <b>osTicket</b>.
</p>

<p>
This configuration builds on the initial deployment and focuses on structuring a functional help desk environment by organizing agents, defining access control, and establishing ticket prioritization and routing.
</p>

<p>
This project assumes osTicket has already been installed and configured. See:
<a href="https://github.com/Christion17/osticket-prereqs">osTicket - Prerequisites and Installation</a>
</p>

<br />

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines)</li>
  <li>Remote Desktop</li>
  <li>Internet Information Services (IIS)</li>
  <li>osTicket</li>
</ul>

<br />

<h2>Operating System Used</h2>
<ul>
  <li>Windows 10</li>
</ul>

<br />

<h2>Configuration Objectives</h2>
<ul>
  <li>Establish role-based access control for agents</li>
  <li>Create departments and teams for structured ticket routing</li>
  <li>Configure users and agents within the system</li>
  <li>Define SLA plans based on ticket severity</li>
  <li>Organize ticket intake using help topics</li>
</ul>

<br />

<h2>System Design Overview</h2>
<ul>
  <li><b>Agents</b> are assigned roles and departments to control permissions and responsibilities</li>
  <li><b>Departments</b> organize ticket ownership and escalation paths</li>
  <li><b>Teams</b> group agents across departments to handle specific issue types</li>
  <li><b>SLAs</b> define response expectations based on ticket severity</li>
  <li><b>Help Topics</b> categorize tickets and influence routing</li>
</ul>

<br />

<h2>Configuration Setups</h2>

<h3>Configuring Roles, Departments, & Teams</h3>

<p>
<ul>
  <li><b>Note:</b> osTicket has two main interfaces: <b>Agent Panel</b> and <b>Admin Panel</b>. The active panel can be identified by the toggle option displayed in the top-right corner.</li>
  <ul>
    <li>Example showing Agent Panel:</li>
    <li><img src="https://i.imgur.com/yJpHeM3.png" height="80%" width="80%" alt="Agent Panel"/></li>
  </ul>

  <li><b>Roles</b> define the permissions granted to agents within the system.</li>
  <ul>
    <li>Navigate to <b>Admin Panel → Agents → Roles → Add New Role</b></li>
    <li>Default roles include: All Access, Expanded Access, Limited Access, and View Only</li>
    <li>Create a role named <b>Supreme Admin</b> and grant full permissions across:
      <ul>
        <li>Tickets</li>
        <li>Tasks</li>
        <li>Knowledgebase</li>
      </ul>
    </li>
    <li><img src="https://i.imgur.com/jpBqHsf.png" height="80%" width="80%" alt="Role Configuration"/></li>
  </ul>

  <li><b>Departments</b> provide structure for ticket routing and ownership.</li>
  <ul>
    <li>Navigate to <b>Admin Panel → Agents → Departments → Add New Department</b></li>
    <li>Create a department named <b>System Administrators</b></li>
    <li><img src="https://i.imgur.com/1pUDA8d.png" height="80%" width="80%" alt="Department Creation"/></li>
  </ul>

  <li><b>Teams</b> group agents across departments to handle specific categories of issues.</li>
  <ul>
    <li>Navigate to <b>Admin Panel → Agents → Teams → Add New Team</b></li>
    <li>Create a team named <b>Level II Support</b></li>
    <li><img src="https://i.imgur.com/eeiO3fN.png" height="80%" width="80%" alt="Team Creation"/></li>
  </ul>
</ul>
</p>

<br />

<h3>Allowing Ticket Creation</h3>

<p>
<ul>
  <li>Navigate to <b>Admin Panel → Settings → Users</b></li>
  <li>Uncheck <b>Registration Required</b> to allow ticket creation without requiring user login</li>
  <li><img src="https://i.imgur.com/7q1wQds.png" height="80%" width="80%" alt="User Settings"/></li>
</ul>
</p>

<br />

<h3>Adding Agents and Users</h3>

<p>
<ul>
  <li><b>Agents</b> are responsible for managing and resolving tickets.</li>
  <ul>
    <li>Navigate to <b>Admin Panel → Agents → Add New Agent</b></li>
    <li>Create sample agents (e.g., Jane Doe, John Doe)</li>
    <li>Assign:
      <ul>
        <li>Department: System Administrators</li>
        <li>Role: Supreme Admin</li>
      </ul>
    </li>
    <li><img src="https://i.imgur.com/816gi8m.png" height="80%" width="80%" alt="Agent Creation"/></li>
  </ul>

  <li><b>Users</b> represent individuals who submit tickets.</li>
  <ul>
    <li>Navigate to <b>Agent Panel → Users → Add User</b></li>
    <li>Create sample users (e.g., Ken, Karen)</li>
    <li><img src="https://i.imgur.com/9NiIMNf.png" height="80%" width="80%" alt="User Creation"/></li>
  </ul>
</ul>
</p>

<br />

<h3>Configuring SLA Plans</h3>

<p>
<ul>
  <li><b>Service Level Agreements (SLAs)</b> define expected response and resolution times.</li>
  <li>Navigate to <b>Admin Panel → Manage → SLA → Add New SLA Plan</b></li>
  <li>Create the following SLA tiers:</li>
  <ol>
    <li><b>SEV-A:</b> 1-hour response (business-critical issues)</li>
    <li><b>SEV-B:</b> 4-hour response (standard operational issues)</li>
    <li><b>SEV-C:</b> 8 business hours (low-priority requests)</li>
  </ol>
  <li><img src="https://i.imgur.com/lYGmtJe.png" height="80%" width="80%" alt="SLA Configuration"/></li>
</ul>
</p>

<br />

<h3>Configuring Help Topics</h3>

<p>
<ul>
  <li><b>Help Topics</b> categorize incoming tickets and guide routing.</li>
  <li>Navigate to <b>Admin Panel → Manage → Help Topics → Add New Help Topic</b></li>
  <li>Create the following categories:</li>
  <ol>
    <li>Business Critical Outage</li>
    <li>Personal Computer Issues</li>
    <li>Equipment Request</li>
    <li>Password Reset</li>
  </ol>
  <li><img src="https://i.imgur.com/kral6FL.png" height="80%" width="80%" alt="Help Topics"/></li>
</ul>
</p>

<br />

<h2>Key Takeaways</h2>
<ul>
  <li>Demonstrates structured configuration of a help desk system</li>
  <li>Shows how roles, teams, and departments control access and workflow</li>
  <li>Highlights SLA-based prioritization of support requests</li>
  <li>Reinforces real-world ticket routing and support operations</li>
</ul>

<br />

<h3 align="right">
Next Tutorial - 
<a href="https://github.com/Christion17/ticket-lifecycle">
osTicket: Ticket Lifecycle Examples
</a>
</h3>
