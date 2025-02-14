---
title : "StrongDM Walkthrough"
weight : 40
---

# Getting Started with StrongDM

1) Access the StrongDM Admin UI portal and log in with your credentials.

   After you receive an invite from StrongDM, start by navigating to the [StrongDM Login Page](https://app.strongdm.com) and entering your credentials. You will be required to use a TOTP MFA app, such as Google Authenticator, to configure MFA. This MFA token will be used later in the workshop, as well.
   
   After logging in, you will be greeted with the StrongDM Admin UI, where you can manage resources, requests, and policies.

   ![StrongDM Admin UI](/static/strongdm_admin_ui.png)

2) Download the StrongDM Desktop app

   On the bottom left, click on "Download & Install" and download the StrongDM Desktop app specific to your desktop client. macOS and Windows platforms have GUI and CLI apps, Linux is CLI only. Install the Desktop App and login with the same credentials as the Admin UI.

   ![StrongDM Downloads](/static/strongdm_downloads.png)

3) Using StrongDM Gateways

   StrongDM Gateways will already be installed in your AWS account, with the appropriate port (TCP/5000) configured in the EC2 Security Group. When creating resources in StrongDM, you will associate to these gateways.

   ![StrongDM Gateways](/static/strongdm_gateways.png)

4) Set up an EC2 Linux Instance

   Start an Ubuntu (recommended) or other Linux instance. You will need the private key to store in Strong Vault when setting up the SSH resource under Resources -> Servers. The default port 22 will be used to configure the resource in StrongDM. After setting up the resource, confirm that the resource status is "Healthy". In the resource settings, make sure you set a tag with "name=first+lastname" (no spaces).

5) Set up an RDS PostgreSQL Database

   Start a new RDS PostgreSQL database. The user and password credential for your admin user will be stored in the Strong Vault when setting up the database resource under Resources -> Datasources. The default port 5432 will be used to configure the resource in StrongDM. After setting up the resource, confirm that the resource status is "Healthy".
   
   Download and install a SQL client of choice onto your desktop. Recommended is Beekeeper Studio Community Edition or DBEaver. In the resource settings, make sure you set a tag with "name=first+lastname" (no spaces).
   
   ![Beekeeper Studio](/static/BeekeeperStudio.png)

6) Submit an access request

   Under Principals -> Users, click on Actions -> Grants Temporary Access, search for your resources, and grant yourself temporary access for the resources above. Once granted, you will see the resources in the StrongDM Desktop app. Click on "Connect". Test connectivity to those resources using the clients of choice: SSH CLI or GUI client; SQL CLI or GUI client. When connecting, use `localhost` and the StrongDM generated port number. No username or password will be used.

   You will approve your own request.

   ![Access Request](/static/RequestAcccess.png)

7) Create Policies

   In the StrongDM Admin UI, create policies that will allow access based contextual attributes (SSH and Postgres) and SQL actions (Postgres). Set up a policy that requires MFA (`@mfa` annotation) when connecting to a resource. The [StrongDM Policies documentation](https://www.strongdm.com/docs/admin/policies/) has syntax and attributes supported, the Policy Creator in the Admin UI has autocomplete hints, and the [Policy Playbooks page](https://www.strongdm.com/policies) has real-world examples you can experiment with.

8) Monitor activity with Policy Monitor.

   Use the Policy Monitor to view and evaluate user actions within StrongDM. It provides a detailed breakdown of allowed and denied actions, helping ensure compliance with security policies.

   ![Policy Monitor](/static/PolicyMonitor.png)

9) Explore logs for auditing and troubleshooting.

   StrongDM maintains detailed logs of all user actions, making it easy to audit and troubleshoot any issues. Access the logs section from the dashboard and filter results by user, resource, or action.

   ![Logs Overview](/static/Logs.png)

10) View and manage database entries.

   Once access is granted, you can use tools like Beekeeper Studio to explore and query your database. For example, you might view tables and execute queries to interact with the data.

   ![Database Table](/static/Table.png)

# Destroying the Configuration

You may manually revoke sessions and delete resources from the Admin UI and AWS Console, if you wish. We will destroy all resources and remove resources and users from the StrongDM Admin UI after the Workshop. We highly recommend you sign up for a free [StrongDM trial](https://www.strongdm.com/signup) after the workshop to continue using StrongDM.

---

# Additional Resources

- [StrongDM Documentation](https://www.strongdm.com/docs)
- [StrongDM Support](https://support.strongdm.com)

This walkthrough introduces key features of StrongDM and demonstrates its capabilities for simplifying and securing infrastructure access. Let us know if you have any questions or need further guidance during the workshop!
