<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket. This tutorial assumes you have fully completed, installed, set up login credentials, and perform clean up on osTicket in your Virtual Machine environment via following the previous tutorial <a href ="https://github.com/ColtonTrauCC/osticket-prereqs">"osTicket - Prerequisites and Installation"</a><br />

</br>

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Internet Information Services (IIS)</li>
  <li>osTicket</li>
</ul>

</br>

<h2>Operating Systems Used </h2>
<ul>
  <li>Windows 10</li>
</ul>

</br>

<h2>Post-Install Configuration Objectives</h2>
<ol>
  <li>Familiarity with the UI of osTicket</li>
  <li>Creating and Configuring Roles</li>
  <li>Creation of Tickets</li>
  <li>Creating Agents and Users</li>
  <li>Setting up Service Level Agreements (SLA Plans) in ticketing system</li>
  <li>Configuring Help Topics</li>
</ol>

</br>

<h2>Configuration Setups</h2>

<!-- <img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/> -->

<h3>Configuring Roles, Departments, & Teams</h3>

<p>
  
<ul>
  <li><b>Note</b>: There are two panels when navigating osTicket; <b>Agent Panel</b> and <b>Admin Panel</b>, you'll know which panel you are on if the <b>opposite panel</b> is displayed on the top right of the UI next to your user login name</li>
  <ul>
    <li>In this example, the user "josh" is on the Agent Panel</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/6abb22de-3ec5-47a9-8efd-46caf9d1622f" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li><b>Roles</b> grant certain permisions to Agents in an Department they are assigned to</li>
  <ul>
    <li>In the <b>Admin Panel</b>, go to the <b>Agents</b> tab and click on <b>Roles</b>, then click on <b>Add New Role</b></li>
    <ul>
      <li><b>Note</b>: osTickets creates four Roles (All Access, Expanded Access, Limited Access, and View Only) by default.</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/6347ce31-f5f1-4078-b738-dc70dd037df6" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Name the new Role <b>Supreme Admin</b>, and click on the <b>Permissions</b> tab; in this tab you can assign specific permissions to this role. For our "Supreme Admin" Role, we will check every box under the <b>Tickets</b>, <b>Tasks</b>, and <b>Knowledgebase</b> tabs. Click on <b>Add Role</b> to finish and create the role.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/306c368f-76fb-4b25-869b-d1a1f430ed76" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
  </ul>

  <li><b>Departments</b> are needed to route and resolve tickets based on their importance or instructions</li>
  <ul>
  <li>Still on the Agents tab, click on <b>Departments</b> and click on <b>Add New Department</b></li>
  <ul>
    <li><b>Note</b>: Much like Roles, osTicket also creates two Departments (Maintenance and Support) by default</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/2a449d47-9632-47ee-9606-65512e292a2e" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>Name the Department <b>System Administrators</b> (we'll leave everything else by default for now), then click on <b>Create Dept</b> to create Department</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/700f78be-2640-4f34-85d6-0ab8ff6ae994" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  </ul>

  <li><b>Teams</b> allow us to organize Agents from different Departments in osTicket to handle specific issues and supersede Agents and their Departments' parameter rules</li>
  <ul>
    <li>In the Agents tab, click on <b>Teams</b> and click on <b>Add New Team</b></li>
    <ul>
    <li><b>Note</b>: Just like previous set ups, osTicket creates a Team (Level I Support) by default</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/5ede2f9c-91d5-4f9b-8199-99e8f0696e5c" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Name the Team <b>Level II Support</b> then click on <b>Create Team</b> to create the Team</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/b9aa5ab2-2c41-4666-a4f2-6a0f3ff88bc1" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Allowing anyone to create Tickets</h3>

<p>
  
<ul>
  <li>In the <b>Admin Panel</b>, head to the <b>Settings</b> tab and click on <b>Users</b>, make sure <b>Registration Required</b> is unchecked. This will allow us to create tickets anonymously</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/97c51388-324a-42e0-a808-067de164c4b6" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Adding Agents and Users</h3>

<p>
  
<ul>
  <li><b>Agents</b> (or Workers) are given the access to the help desk in osTicket to respond, resolve, and update the status of tickets</li>
  
  <ul>
    <li>In the <b>Admin Panel</b>, head to the <b>Agents</b> tab and click on <b>Add New Agent</b></li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/d66757f0-54d1-458f-8a2d-4f1890b2da1d" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>For this tutorial, we will be creating two new Agents <b>Jane</b> and <b>John</b>, it is advise to have a notepad ready to catalog login information as you enter their credentials, but we will set their user names as <b>[name].doe</b> and both of their passwords as <b>Password1</b> for convenience (which is our admin password from the installation tutorial)</li>
    <ul>
      <li>Fill in the Agent's basic info and set the Agent's email address as <b>[name].doe@osticket.com</b> and click on <b>Set Password</b></li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/06fbd1ca-9d97-4f4f-b866-9b304dbdeb57" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
      <li>Set the Agent's password to <b>Password1</b> and unchecked the boxes to prevent the Agent for our example from needing to reset password or change password after login</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/51953148-bddc-476c-9368-4b62f4bf3d42" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>Go the <b>Access</b> tab to set the Agent's <b>Primary Department</b> (Mandatory to create the Agent). <b>Extended Access</b> can also be added to the Agent in order to access additional Departments</li>
    <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/c57bca22-2622-4f01-88eb-bd699d1f12de" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>OPTIONAL: Head to the <b>Teams</b> tab to assign the Agent to a Team</li>
  </ul>
  
  <li><b>Users</b> (or Customers) are creators and owners of tickets and by using osTicket they are able to track the status of their tickets</li>
  
  <ul>
    <li>In the <b>Agent Panel</b>, go to the <b>Users</b> tab and click on <b>Add User</b></li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/f08ec067-3a66-420e-bfaf-6a3003512bcb" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
    <li>For this tutorial, we will be creating two new Users <b>Ken</b> and <b>Karen</b> and setting up usernames, emails, and passwords similar to our Agents.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/8eadff14-b483-4781-9679-80b252a092c4" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Adding SLA Plans</h3>

<p>
  
<ul>
  <li><b>Service Level Agreements</b> or SLA Plans provide a length of time for the ticket Administrator when the ticket is expected be CLOSED. They can also be designated to specific Departments or Help Topics</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and drop down to <b>SLA</b> then click on <b>Add New SLA Plan</b></li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/1ebc6fe9-aa95-4e52-9fd9-1ecd7724d3b9" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/cf8da66d-209b-40e6-a4f1-c99bbd102b3a" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>osTicket by default has the SLA Plan <b>Default SLA</b>. We will be creating three SLA Plans each with their own length of time for different kinds of importance of the ticket, from highest priority to lowest priority:</li>
  <ol>
    <li>SEV-A with <b>1 hour Grace Period, 24/7 Schedule</b>, suitable for tickets that are business critical</li>
    <li>SEV-B with <b>4 hour Grace Period, 24/7 Schedule</b>, suitable for tickets affecting employees such as troubleshooting or PC problems</li>
    <li>SEV-C with <b>8 hour Grace Period, business hours Schedule</b>, suitable for tickets requesting new equipment</li>
  </ol>
  <li>Example of creating SEV-A SLA Plan, click on <b>Add Plan</b> to create the SLA Plan</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/ee7d6fbb-f67a-4055-aa9b-b9fd77d48de1" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Configuring Help Topics</h3>

<p>
  
<ul>
  <li><b>Help Topics</b> are helpful to streamline the ticket entry experience for the user by helping them specify their ticket info and also determine what Department the ticket should go to</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click on <b>Add New Help Topic</b></li>
  <ul>
    <li><b>Note</b>: osTicket creates four Help Topics (Feedback, General Inquiry, Report a Problem, and Report a Problem / Access Issue) by default</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/27299450-a705-462c-a7d0-6fcdac6f5a59" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  <li>We will create four different Help Topics based on the potential serverity a ticket could have, from highest to lowest priority:</li>
  <ol>
    <li>Business Critical Outage</li>
    <li>Personal Computer Issues </li>
    <li>Equipment Request</li>
    <li>Password Reset</li>
  </ol>
  <li>Example of entering credentials for the Help Topic "Equipment Request," click on <b>Add Topic</b> to create the Help Topic</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/97777c9e-516c-4831-891b-9d65e9613ed0" height="80%" width="80%" alt="Disk Sanitization Steps"/></li>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Further Reading and Manual</h3>
<ul>
  <li>This concludes to basics of osTicket configuration, but further information and research on the features of osTicket can be found in the official online doccumentation <a href= "https://docs.osticket.com/en/latest/index.html">here</a></li>
</ul>

<br/>

<h3 align = "right">Next Tutorial - <a href = "https://github.com/Christion17/ticket-lifecycle">osTicket: Ticket Lifecycle Examples</a></h3>
