<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Post-Install Configuration Objectives</h2>

- Configure Roles
- Configure Departments
- Configure Teams
- Configure Agents (workers)
- Configure Users (customers)
- Configure SLA

<h2>Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/4f8dZcc.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login as User Admin. Notice on the top right there's an Admin Panel button. Click on it to switch into the Admin Panel.
</p>
<br />

Roles
=====

<p>
<img src="https://i.imgur.com/ZHBj01P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments.

**Role Permissions for Tickets include:**

  **Assign:** Ability to assign tickets to agents or teams

  **Close:** Ability to close tickets

  **Create:** Ability to open tickets on behalf of users

  **Delete:** Ability to delete tickets

  **Edit:**  Ability to edit tickets

  **Edit Thread:** Ability to edit thread items of other agents

  **Link:** Ability to link tickets

  **Mark as Answered:** Ability to mark a ticket as Answered/Unanswered

  **Merge:**  Ability to merge tickets

  **Post Reply:**  Ability to post a ticket reply

  **Refer:**  Ability to manage ticket referrals

  **Release:** Ability to release ticket assignment

  **Transfer** Ability to transfer tickets between departments

**Role Permissions for Tasks include:**

  **Assign:** Ability to assign tasks to agents or teams

  **Close:** Ability to close tasks

  **Create:** Ability to create tasks

  **Delete:** Ability to delete tasks

  **Edit:** Ability to edit tasks

  **Post Reply:** Ability to post task update

  **Transfer:** Ability to transfer tasks between departments

**Role Permissions for the Knowledge Base include:**

  **Premade:** Ability to add/update/disable/delete canned responses

If granted access to the Admin Panel, that Agent will have the ability to make changes in the configurations of the help desk. From the Agent tab of the Admin Panel, the configurations of each Agent of the help desk can be modified, including the ability to Limit an Agent’s access to only tickets that are specifically assigned to them.

The Permissions tab of the Agent profile allows the Agent functionality within the help desk which are not Department specific access items. Areas such as the User Directory, Organization, and Knowledge Base can be limited per Agent. This includes the ability to search for and see the ticket metadata for tickets the Agent does not have access to, the email ban list, and other staff statistics on the dashboard.
  
 Departments
===========

**Admin Panel > Agents > Departments**

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/admin_agents_departments.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Since tickets are routed through Departments in the help desk, there are many settings that can be set for each Department.

**Department Information:**

  **Parent:**  If nesting departments, this is the Parent Department to nest the department under. Please note: If an agent has access to the Parent Department, they will see the tickets of nested or child departments also, but access does not extend from child departments to Parent Departments.

  **Status:** The status of the department will determine its visibility as well as if tickets can be routed to that department.

**Active:** The department is available when transferring tickets.

**Archived:** The department is no longer in use and cannot be selected to transfer any ticket. Also, if tickets in that department are reopened via an End-User response it will create a new ticket referencing the original ticket number and subject line but the department will be the system default.

**Disabled:** Tickets can no longer be transferred to this department and any tickets set up to be auto routed to this department will now be routed to the default department in the Helpdesk. Closed tickets in this department will reopen if the End-User responds.

  **Name:** Department name as it will be displayed throughout the helpdesk.

  **Type:** Select Private if you wish to mask assignments to this Department in the Client Portal. Additionally, when labeled as Private, the **Department Signature** will not be displayed in email replies. At least one department of the help desk must be Public.

  **SLA:** Service Level Agreement for tickets routed to this Department. This the expected amount of time (in hours) that a ticket is expected to be closed once opened. If the ticket is not closed in the allotted amount of time, it will then be Overdue.

  **Schedule:** Schedule is used by the Service Level Agreement when rendering tickets routed to this Department. This setting takes precedence over System and SLA schedule settings.

  **Manager:** Electively, select a Manager for the departments of the help desk. Managers can be configured to receive special alerts.

  **Ticket Assignment:** Enable this to restrict ticket assignment to include only members of this Department. Department membership can be extended to based on Agent’s Department Access, if **Alerts & Notices Recipients** includes those with department access.

  **Claim on Response:** Check this to **disable** auto-claim on response/reply for this department. Agents can still manually claim unassigned tickets.

  **Reopen Auto Assignment:** Check this to disable auto-assignment of reopened tickets for this department. Otherwise, the Ticket will be auto assigned to the last responding Agent.

**Outgoing Email Settings:**

  **Outgoing Email:** Email Address used when responses are sent to Users when Agents post Responses to Tickets.

  **Template Set:** Email **Template Set** used for Auto-Responses and Alerts & Notices for tickets routed to this Department. Template sets can be cloned and edited for department use in the Admin Panel > Emails > Templates.

**Auto Responder Settings:** This allows you to override the global Autoresponder settings for this Department.

  **New Ticket:** If checked, this will disable the New Ticket Auto-Response sent to the User
  when a new ticket is created and routed to this Department.

  **New Message:** If checked, this will disable the Auto-Response sent to the User to confirm a newly-posted message for tickets in this Department.

  **Auto-Response Email:** Select an email address from which Auto-Responses are sent for this Department; this email would send only auto-response messages, not Agent responses.


</p>
<br />

Teams
=====

**Admin Panel > Agents > Teams**

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/admin_agents_teams.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
**How to Create Teams In Your Help Desk**

  Teams allow you to pull Agents from different Departments and organize them to handle a specific issue or user via a Help Topic or Ticket Filter.

  Having Agents from different Departments assigned to a Team will supersede the parameters of the Agents’ Department rules. For example, you can create a Help Topic associated with a particular product you produce, and assign it to a Team of specialist Agents from different Departments.

  To create a Team in your Admin Panel, locate the Agents tab, and click on Teams. Then click Add New Team on the right, and fill out the appropriate information. Then you will be able to add Agents to the team by clicking on their name from your list of Agents and checking the corresponding box next to the Team name you wish to add them at the bottom of the page.

  A Team can have an appointed leader who can receive Alerts & Notices separate from other team members. In order to set a Team Leader you can choose an Agent from the Team Lead dropdown when creating a Team or Editing an existing Team.

</p>
<br />

Agents
======

**Admin Panel > Agents > Agents**

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/admin_agents_agents.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Agents are given access to the help desk with the intent to respond and resolve the tickets. When adding an Agent to the help desk, they will need to be assigned to a Primary Department and given a Primary Role for the Tickets/Tasks routed to that department. Agents can be given Extended Access to additional departments of the help desk as well as assigned different Roles to those departments; this can be configured in the Access tab of the Agent’s Profile.

**Reset an agent’s password**

If necessary, administrators can manually reset an agent’s password by clicking the Set Password box in the middle of the Account page. This will produce a pop-up box with two options; the first is to send a password reset email to the agent. **Please note**, if the agent has not first set a password post-creation they can not reset said password. The second option for the admin is to uncheck the box which will populate fields to manually set a password for the agent. Once manually set, the admin will need to communicate this to the agent allowing them to log-in; the agent can be forced to reset the password upon logging in by keeping the box checked at the bottom left of the pop-up.

**Status and Settings**

  **Locked:** Agents who are Locked/Disabled are unable to log into the help desk. They will not be visible for assignment or auto assignments. Email alerts will not be sent to disabled agents as well.

  **Administrator:** Agents marked as “Administrators” simply have access to the Admin Panel are able to make global configuration changes to the help desk. All changes are effective moving forward and will not revert to previously configured settings. Agents with access to the Admin Panel can grant additional agents access to this panel for global configurations.

  **Limit ticket access to ONLY assigned tickets:** When this is checked these agents will only see tickets which are directly assigned to them as an agent or a team to which the agent belongs- regardless of department access. Once tickets are set to a status of a closed state, the assignment is released and the agent will lose access to these closed tickets; if the ticket is reopened, the agent could regain access if it is reopened assigned to them.

  **Vacation Mode:** Agents who are on vacation mode are able to log into the help desk but, like Locked/Disabled agents, they will not be visible for assignment or auto assignments and email alerts will not be sent to these agents as well. An agent can manually set themselves to Vacation Mode in their Profile or an agent with access to the Admin Panel. Vacation Mode must be manually enabled as well as disabled.

Agent Access
------------

Agents are given access to the help desk with the intent to respond and resolve the tickets. When adding an Agent to the help desk, they will need to be assigned to a Primary Department and given a Primary Role for the Tickets/Tasks routed to that department. Agents can be given Extended Access to additional departments of the help desk as well as assigned different Roles to those departments; this can be configured in the Access tab of the Agent’s Profile.

Fall back to primary role
For agents without department access which are granted access to tickets via Ticket Assignment/Ticket Referral, they will have Primary Role Permissions for tickets if this is checked. Otherwise, Agents will have a view only access to these tickets allowing them to post an internal note only.

**Agent Permissions**

  **Users**

   **Create:** Ability to add new users

   **Edit:** Ability to manage user information

   **Delete:** Ability to delete users

   **Manage Account:** Ability to manage active user accounts

   **User Directory:** Ability to access the user directory

  **Organizations**

   **Create:** Ability to create new organizations

   **Edit:** Ability to manage organizations

   **Delete:** Ability to delete organizations

  **Knowledgebase**

   **FAQ:** Ability to add/update/disable/delete knowledgebase categories and FAQs

  **Miscellaneous**

   **Banlist:** Ability to add/remove emails from banlist via ticket interface

   **Search:** See all tickets in search results, regardless of access

   **Stats:** Ability to view stats of other agents in allowed departments

</p>
<br />

User Directory
==============

**Agent Panel > Users > User Directory**

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/agent_users_userDir_dir.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Users can now create an account and log-in to create a ticket or check a ticket’s status. As always with osTicket, users or ticket creators are associated with their email address as the unique identifier of each user. The User Directory, located on the Agent Panel, allows agents to  search tickets by user as well as create Organizations to associate the user to. Agents can be configured as internal Account Managers for tickets created by users of an Organization.


What is a User?
---------------

Users are the ticket owners of the tickets in the help desk. When a ticket is created in the help desk, the user is associated with their email address in the User Directory of the help desk. Users can be added or deleted from the User Directory of the help desk at any time. Please note, if the user is deleted the tickets of the user must also be deleted.


Add New Users
-------------

You can add users to the User Directory of the Agent Panel of the help desk either individually or by importing them by uploading a CSV file. If you are uploading, you will need to match the headers of the CSV to the fields in the Contact Information built-in form.  Once you add the user, you can associate the User to an Organization of the help desk.

User Import via Copy/Paste
--------------------------

Importing a list via copy/paste allows you to easily import User’s names and email addresses from a simple list.

Create a list of names and email addresses on any text editor. Separate each name and address by comma, making a new line for each User.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/User_Copy_Paste_1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Copy the list, then go to the User Directory and select import.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/User_Copy_Paste_2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Paste list then select ‘Import Users’.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/User_Copy_Paste_4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
User import via CSV file
------------------------

Importing Users via CSV file allows you to import User’s names and email addresses as well as additional details if necessary.

Go to the User Directory and select ‘Import’ then ‘Upload’.

</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/user_CSV_1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Take note of the Column Headers listed here as your spreadsheet headers will need to match. You can customize these headers as well as add additional fields to import by editing the Contact Information form located at Admin Panel > Manage Tab > Forms.

Create a spreadsheet of names and addresses, as well as any other fields that you would like to import, matching the column headers to the ones shown in osTicket.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/user_CSV_2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the spreadsheet is complete, export the document into a CSV file and import the file into osTicket at Agent Panel > Users > Import > Upload Tab.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/user_CSV_3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Guest User vs Registered User
-----------------------------

You can choose to have your users register prior to submitting a ticket to your help desk from your Client Portal from Agent Panel > Users > User Directory > More > Regis. If a User is registered, this means they have created an account and verified their email. Once registered, they will be able to access all tickets they have in the help desk. Users can create their own User account or they can be added from the Agent Panel of the help desk. If added internally, the Agent will need to send the registration email for the User to verify their email address prior to becoming a registered user. Guest Users don’t require registration to submit tickets.

Managing Registered Users
-------------------------

Once a user has activated their account with the help desk, Agents can administratively manage their access to the help desk; including requiring a password reset, locking them from the help desk, and even resetting their password. The User management feature is accessible by opening the configurations of that user and clicking the Manage Account quick button at the top right of the header.
</p>
<br />

<p>
<img src="https://raw.githubusercontent.com/osTicket/docs/master/_static/images/agent_users_userDir_manageUser.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A pop up box will appear; click on the Manage Access tab to configure these features.
</p>
<br />

<p>
<img src="https://i.imgur.com/gdv8E1U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reset a User’s password
-----------------------
  
If necessary, administrators can manually reset a User’s password by going to their User Profile in the User Directory, then selecting the Manage Access Tab. Once manually set, an Agent will need to communicate the new password to the User allowing them to log-in; the User can be forced to reset the password upon logging in by keeping the box checked at the bottom left of the pop-up.

</p>
<br />

SLA Plans
=========

**Admin Panel > Manage > SLA (Service Level Agreements)**

Create A New SLA Plan
---------------------

<p>
<img src="https://i.imgur.com/iwTLMqL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
SLA Plans or Service Level Agreements, are unlimited in osTicket. The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed.

SLA Plans can be created by going to the Admin Panel > Manage > SLA Plans. Click on the top right of the table to “Add New SLA Plan.”

One configuration to note with each SLA Plan is whether it can be overridden on Department transfer or change of Help Topic by being Transient. Transient SLAs are considered temporary and can be overridden by a non-transient SLA on Department transfer or when its **Help Topic** is changed.

Once created, SLA Plans can be determined for Departments, Ticket Filters, and Help Topics. There is also a System Default SLA Plan which can be chosen by going to Admin Panel > Settings > Tickets.

When a ticket is created internally from the Staff Panel, agents can choose an SLA Plan which will override any other assignments to a Department or Help Topic. Agents can also select a Due Date for the ticket which, if passed, will cause the ticket to become overdue. No SLA plan can override a due date.

If a ticket is created from the Client Interface, the SLA Plan associated with the Help Topic will be in effect unless a Ticket Filter is in place and the criteria is met; then the SLA Plan associated with the Ticket Filter will be in effect.

For tickets created via email, the department that the email address is assigned to will determine the SLA plan of the ticket unless a Ticket Filter is in place and the criteria is met; then the SLA Plan associated with the Ticket Filter will be in effect.

**Admin Panel > Manage > SLA Plans:**

**Service Level Agreements:** SLA Plans can be set by help topic and department to ensure the ticket is CLOSED in the allotted or specified amount of time.

  **Name:**  Plan name to be selected when assigning.

  **Grace Period:**  Amount, in hours, before tickets with this SLA will become overdue if not closed in allotted time.

  **Status:**  Choose Active or Disable for the plan.

  **Transient:** SLA can be overridden on ticket transfer or help topic change; if not transient, the SLA will remain the same as it is assigned on ticket creation.

  **Ticket Overdue Alerts:** This will DISABLE overdue alert notices to staff for tickets assigned this SLA.

</p>
<br />

SLA Plans or Service Level Agreements, are unlimited in osTicket. The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed.

SLA Plans can be created by going to the Admin Panel > Manage > SLA Plans. Click on the top right of the table to “Add New SLA Plan.”

One configuration to note with each SLA Plan is whether it can be overridden on Department transfer or change of Help Topic by being Transient. Transient SLAs are considered temporary and can be overridden by a non-transient SLA on Department transfer or when its **Help Topic** is changed.

Once created, SLA Plans can be determined for Departments, Ticket Filters, and Help Topics. There is also a System Default SLA Plan which can be chosen by going to Admin Panel > Settings > Tickets.

When a ticket is created internally from the Staff Panel, agents can choose an SLA Plan which will override any other assignments to a Department or Help Topic. Agents can also select a Due Date for the ticket which, if passed, will cause the ticket to become overdue. No SLA plan can override a due date.

If a ticket is created from the Client Interface, the SLA Plan associated with the Help Topic will be in effect unless a Ticket Filter is in place and the criteria is met; then the SLA Plan associated with the Ticket Filter will be in effect.

For tickets created via email, the department that the email address is assigned to will determine the SLA plan of the ticket unless a Ticket Filter is in place and the criteria is met; then the SLA Plan associated with the Ticket Filter will be in effect.

**Admin Panel > Manage > SLA Plans:**

**Service Level Agreements:** SLA Plans can be set by help topic and department to ensure the ticket is CLOSED in the allotted or specified amount of time.

  **Name:**  Plan name to be selected when assigning.

  **Grace Period:**  Amount, in hours, before tickets with this SLA will become overdue if not closed in allotted time.

  **Status:**  Choose Active or Disable for the plan.

  **Transient:** SLA can be overridden on ticket transfer or help topic change; if not transient, the SLA will remain the same as it is assigned on ticket creation.

  **Ticket Overdue Alerts:** This will DISABLE overdue alert notices to staff for tickets assigned this SLA.

<p>
<img src="https://i.imgur.com/4W3XCMV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Add New Role.
</p>
<br />

<p>
<img src="https://i.imgur.com/0LKnECl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Supreme Admmin Role.
</p>
<br />

<p>
<img src="https://i.imgur.com/laOPU7Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on the Permissions Tab.
</p>
<br />

<p>
<img src="https://i.imgur.com/ZKEXtWK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Tickets, select all options.
</p>
<br />

<p>
<img src="https://i.imgur.com/SMX9pcf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Tasks, select all options.
</p>
<br />

<p>
<img src="https://i.imgur.com/LM0hLUX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Knowledgebase, select the option and finally click Add Role.
</p>
<br />

<p>
<img src="https://i.imgur.com/xnVSfzW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Departments.
</p>
<br />

<p>
<img src="https://i.imgur.com/Yf5yxcF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Add A New Department.
</p>
<br />

<p>
<img src="https://i.imgur.com/2rIAaTB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Fill in the name, select options and create the Department.
</p>
<br />

<p>
<img src="https://i.imgur.com/8oM5v8R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Teams.
</p>
<br />

<p>
<img src="https://i.imgur.com/MfzR6HY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Add Team.
</p>
<br />

<p>
<img src="https://i.imgur.com/e6j6yPg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name the Team and create it.
<br />

<p>
<img src="https://i.imgur.com/LpetDUK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Members and add yourself to the team.
</p>
<br />

<p>
<img src="https://i.imgur.com/m93SkT6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Settings, Users, Settings, uncheck Require Registration.
</p>
<br />

<p>
<img src="https://i.imgur.com/XH5uAuW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click the Agents Tab and Add New Agent.
</p>
<br />

<p>
<img src="https://i.imgur.com/f5cJXnY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create your first Agent.
</p>
<br />

<p>
<img src="https://i.imgur.com/RYs87Ny.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Uncheck the boxes and set password.
</p>
<br />

<p>
<img src="https://i.imgur.com/0OTuRow.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set Access Settings.
</p>
<br />

<p>
<img src="https://i.imgur.com/GjU2UkR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Create after selecting Team.
</p>
<br />

<p>
<img src="https://i.imgur.com/lSh3Avy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to Agents and repeat steps for Agent 2.
</p>
<br />

<p>
<img src="https://i.imgur.com/65ksYdo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set Access Settings for Agent 2.
</p>
<br />

<p>
<img src="https://i.imgur.com/lyGcxca.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create Users by going into the Agent Panel.
</p>
<br />

<p>
<img src="https://i.imgur.com/WvT93Jz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click the Users Tab.
</p>
<br />


<p>
<img src="https://i.imgur.com/0QAD95l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click User Directory and repeat steps for 2nd User.
</p>
<br />

<p>
<img src="https://i.imgur.com/pwdphzP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to Admin Panel, Manage, and SLA.
</p>
<br />

<p>
<img src="https://i.imgur.com/hopZq53.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Add New SLA Plan.
</p>
<br />

<p>
<img src="https://i.imgur.com/GOz2RyN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name and set rules for 1st SLA.
</p>
<br />

<p>
<img src="https://i.imgur.com/J9EEMy7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create rules for 2nd SLA.
</p>
<br />

<p>
<img src="https://i.imgur.com/9Uo6I6y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create rules for 3rd SLA.
</p>
<br />

<p>
<img src="https://i.imgur.com/HQSHban.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Help Topics.
</p>
<br />

<p>
<img src="https://i.imgur.com/eypFZRy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create Business Critical Outage and repeat the steps for the others. All Helps Topics are listed on the final slide.
</p>
<br />

Take note of the Column Headers listed here as your spreadsheet headers will need to match. You can customize these headers as well as add additional fields to import by editing the Contact Information form located at Admin Panel > Manage Tab > Forms.

Create a spreadsheet of names and addresses, as well as any other fields that you would like to import, matching the column headers to the ones shown in osTicket.
