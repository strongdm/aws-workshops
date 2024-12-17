---
title : "StrongDM Walkthrough"
weight : 40
---

# Getting Started with StrongDM

1) Access the StrongDM portal and log in with your credentials.

   Start by navigating to the [StrongDM Login Page](https://app.strongdm.com) and entering your credentials. After logging in, you will be greeted with the StrongDM dashboard, where you can manage resources, requests, and policies.

   ![Resource Center](/static/ResourceCenter.png)

2) Set up a connection to your database.

### Configure the PostgreSQL connection

   From the dashboard, add a new connection. For this example, we are setting up a PostgreSQL database connection. Fill in the required details such as host, port, and database credentials.

   ![Beekeeper Studio](/static/BeekeeperStudio.png)

3) Submit an access request.

   If access to a specific resource is restricted, navigate to the Requests section and create a new access request. Be sure to provide a reason and specify the duration for the requested access.

   ![Access Request](/static/RequestAcccess.png)

   Once submitted, the request will enter the review queue for approval.

4) Review and approve requests (Admin Perspective).

   For administrators, incoming requests appear in the review queue. Approve or deny the request based on the provided justification. Approvals grant temporary access to the requested resource.

   ![Access Review](/static/RequestAcccess.png)

5) Monitor activity with Policy Monitor.

   Use the Policy Monitor to view and evaluate user actions within StrongDM. It provides a detailed breakdown of allowed and denied actions, helping ensure compliance with security policies.

   ![Policy Monitor](/static/PolicyMonitor.png)

6) Explore logs for auditing and troubleshooting.

   StrongDM maintains detailed logs of all user actions, making it easy to audit and troubleshoot any issues. Access the logs section from the dashboard and filter results by user, resource, or action.

   ![Logs Overview](/static/Logs.png)

7) View and manage database entries.

   Once access is granted, you can use tools like Beekeeper Studio to explore and query your database. For example, you might view tables and execute queries to interact with the data.

   ![Database Table](/static/Table.png)

# Destroying the Configuration

To revoke all access and reset the environment, follow the process outlined in the StrongDM documentation or manually revoke connections and delete resources from the dashboard.

---

# Additional Resources

- [StrongDM Documentation](https://www.strongdm.com/docs)
- [StrongDM Support](https://support.strongdm.com)

This walkthrough introduces key features of StrongDM and demonstrates its capabilities for simplifying and securing infrastructure access. Let us know if you have any questions or need further guidance during the workshop!
