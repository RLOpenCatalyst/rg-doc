.. _`Appendix A`:

Appendix A - Registration Information 
======================================

.. csv-table::
   :file: AppendixA.CSV
   :widths: 80, 90
   :header-rows: 1
   
.. _`Appendix B`:

Appendix B - Standard Catalog Information
=========================================

.. csv-table::
   :file: AppendixB.csv
   :widths: 50, 40, 200
   :header-rows: 2
   
.. _`Appendix C`:

Appendix C - Hosted Silo Model
==============================

.. csv-table::
   :file: AppendixC.csv
   :widths: 50, 40, 40, 40
   :header-rows: 2
  
.. _`Appendix D`:

Appendix D - Audit Trail Events for Administrator
=================================================

.. csv-table::
   :file: AppendixD.csv
   :widths: 20, 20, 20
   :header-rows: 2
   
.. _`Appendix E`:

Appendix E - Project Related Events
====================================

.. csv-table::
   :file: AppendixE.csv
   :widths: 10, 10, 50
   :header-rows: 2

.. _`Appendix F`:

Appendix F - Audit Trail Events for Principal Investigator
==========================================================

.. csv-table::
   :file: AppendixF.csv
   :widths: 20, 20, 20
   :header-rows: 2

Appendix G - Release Notes
==========================

v1.15.0
^^^^^^^^

Enhancements
-------------

#. Principal Investigators will now see all the products launched by all the project team-members in the All Products tab. They will also be able to perform Stop and Terminate actions on the products using the 3-dotted icon which is available at the right side of the table.  
   
   * Products which are in Creating, Transitioning and Terminating State will not show any actions in the All Products tab.
   
   * Products which are in stopped state will show only the Terminate action.
   
   * Project Storage will not show any actions as it cannot be terminated independent of the project.
   
   * EFS or FSx file-systems will only show the Terminate action.
#. PCluster Enhancement. Users will now be given choice to connect either an EFS or FSx file- system (provisioned earlier) to the PCluster.
#. End of Day (EOD) Report for Principal Investigators. EOD Reports will be sent with the subject as "Research Cost Tracking Daily Report". It will show the following tables.
   
   * Account table: This table lists all the accounts in use in your tenant. Each account will show the month-to-date consumption and the forecast value.
   
   * Projects summary table: This table shows each project’s summary including month to date consumption and cumulative consumption (since inception).
#. Project Details table: This table shows all the Active products per project and the month to date and cumulative cost per project. It also shows a single line item for the cumulative month-to-date and cumulative cost of Terminated products. For each provisioned product User will now be able to see Created on Parameter in Product Details Tab which will indicate the Product Creation Date.
#. Audit Trail: Filter values should be sorted in Alphabetical order. This will help Users to find the expected values more easily. 


Bug-fixes
----------
1. Amazon SageMaker : product launch failed. 
   Note: User will need to manually sync their project once for the product template to get updated in their account. 
2. Notificationsink: When send email of failed product fails, the error message talks about the email failure instead of actual error 
3. Date range picker on the Costs tab now allows to select only valid dates based on the lifespan of the product. 
4. Choosing Organizational Unit should be disabled when the role is chosen as Admin while creating a user. 
5. My Products tab: Budget value for product card is showing two decimal values but when the search is performed in my products tab it is not working as expected 
6. When a role gets removed from AWS console and we still have a setting in RG DB, new settings addition is failing by throwing a malformed policy error 
7. Product daily cost missing for certain days  
8. Even if the Status key value "DELETE_IN_PROGRESS" or "AVAILABLE" is set, the isDeleted flag is set to true. 
9. User Creation: If B2C mode is set to true and the user is PI, then only create the default organization. 
10. All audit events should be tagged with organization ID. 

 
v1.14.0
^^^^^^^

Enhancements
------------
1. Select User-Created Studies to Mount. Users now have the ability to choose up to 5 studies that will be mounted to the workspaces being created. With this feature, the “Bring Your Own Bucket “ (BYOB) feature is now complete. This powerful feature allows users to create their own studies, assign them to specific projects, choose which studies to mount while creating workspaces, and finally use the mounted studies to read the data from their workspaces.
2. Current Month Cost in Daily EOD Report. Users are always sensitive to cost in the AWS cloud environment. To help them be aware of the costs, we have created an End of Day report to the principal investigator, which will give them the current month direct costs as well as the AWS current month to date billing. This is expected to help users keep better track of their project budgets.
3. Budget Screen Enhancements. Budget screens will also show the current month direct costs in line with the feature above.
4. Edit User-Created Studies. This allows users to reuse the studies they create by assigning new projects to the same study. A classic use-case is when a professor wants to use a dataset for a semester project by his students. Each semester the project and students would change but the dataset created as a study would remain the same.
5. Export Project Budget Details. This feature is being done for a Singapore based university using the Research Gateway product. They wanted the details of the budget consumption to be exported in a form that can be used for analysis using the Excel or other tools.

Bug-fixes
---------
1. Organization Id to be added to all Audit Trail events to allow filtering by OU.
2. Project sync was not working when more than 200 products exist in Service Catalog.
3. Invalid URL typed by user should show error message.
4. KMS ARN field should be validated in Add/Edit Internaly Study screen.
5. Updates to project catalog should be restricted when one update is in progress.
6. Product Cost Trends chart should show dates in ascending order.
7. S3 Explore: Copy to clipboard action getting duplicated.
8. SSH action links should be accessible only to owners.
9. Security fixes. This includes some technology refresh in major third-party technologies used like MongoDB, npm packages, node.js etc. The chief among these is an upgrade to MongoDB v4.0.0 that also allows us to upgrade to Node.js v18. Database passwords are now stored using AWS Secret Manager service, providing an additional layer of security, in line with AWS recommended best practices.

v1.13.2
^^^^^^^

Enhancements
------------

1. Amazon EFS added to standard catalog. You can now provision high performance NFS based file-system (Amazon EFS) for computational needs that needs high-performance shared storage.
2. Project storage creation made optional during project creation.
3. Project catalog automatically picks up new attributes like tags during daily sync when there is an update.
4. New audit trail events for product provisioning success and failure.
5. ImageBuilder pipeline support for PCluster AMI creation in Enterprise Mode.
6. Optimization of Service Catalog API calls to reduce costs. Catalog sync now only happens when manually initiated from Project Sync action.
7. Users will now receive email notification of provisioning completion (success or failure) on their verified email ids.


Bug-fixes for existing issues
-----------------------------

1. User Management: User should be added to the DB only after cognito signup is successful
2. User id should be case insensitive.
3. notificationsink: Product Provisioning events should only be sent to the PI and Researchers
4. notificationsink: product events not getting updated when isDeleted flag is set to true
5. Users Screen: Add User :Error toaster message changes.
6. Security vulnerability for the Passport-Cognito package in the Node Js Server Side Code
7. Security fixes related to OWASP Top 10 vulnerabilities.

v1.13.0
^^^^^^^
We are excited to release v1.13.0 of the Research Gateway. This release has some exciting new features and some bug-fixes as well.

Enhancements
------------

1. PCluster enhancements. The cluster head-node by default has NICE DCV installed which allows you to connect to the head-node via  a GUI interface. This is especially useful to visualize results of the jobs that you run on the cluster (e.g. using Paraview to view the results of OpenFOAM jobs). The URL to the NICE DCV server on the head-node will be secured using SSL if you choose that option while adding your AWS account as a setting in Research Gateway. The pcluster head node also updates the latest security patches during provisioning so that you do not have to worry about open vulnerabilities. PCluster provisioning now also provides control over Hyperthreading and ElasticFabricAdapter support based on the instance types chosen for the compute nodes.
2. Support to add your own external studies and link them to projects. A new study type called external study has been introduced. This allows you to bring in any existing bucket in your project account as a study even if the bucket was not provisioned via the Research Gateway interface (e.g. you can bring in existing data). External buckets can be linked to projects and are auto-mounted to all workspaces in the project just like ProjectStorage.
3. ProjectStorage can be deleted while archiving a project. You will now be prompted for deletion of the projectstorage when you archive a project. Select the checkbox if you want to delete the projectstorage bucket along with all of its contents.
4. Daily cost trends for each product (workspace) are now available in the Cost tab (new feature). See the daily cost for the workspace from the date of creation to current date in both chart and table form. Select the date range you want to view the information for (the default is seven days).
5. NICE DCV standalone workspace also supports secure connections using SSL (if the project has opted for SSL).
6. Security fixes - Many of the third-party packages used have been updated to address vulnerabilities found during security scans so that users can rest assured that their data and workspaces are secure.

Bug-fixes for existing issues
-----------------------------
1. If a user has active products in which they are the "owner" of the share provisioned product, PI should not be allowed to remove them from the project.
2. Page refresh in Studies:Explore:Folder was causing loader issues. 
3. Connect URL button showing for stopped workspaces of type NICE DCV.
4. Change Icon for FSx product.
5. Subnet ID mismatch when multiple subnets are required in the CFT input.
6. In Users Screen: Download CSV format action is not working.
7. Studies : Public Study : Explore : Folder: Page Refresh is showing Create new button.
8. Studies Page : explore action : Folder : showing no data available : once click on refresh action which is available in the UI it will show content.
9. For workspaces that connect to DCV, the button should read "Remote Desktop" rather than "Connect DCV".
10. PI Login : Archive project : Delete project storage S3 bucket.
11. Subnet ID mismatch when multiple subnets are required in the CFT input.
12. UI changes required in Public studies.
13. s3:Explore:Upload: create an audit trail event for failure.
14. PCluster: Latest AMI causing stack to fail if there is a fileSystemId as input parameter when scheduler is aws batch

Appendix H - FAQs - Frequently Asked Questions
==============================================

1. How can I access help or reach out for support?

 **Answer**: You can use the Chat widget or you can send an email to rlcloudsupport@relevancelab.com to create a support case.


2. In the in-browser SSH window in Research Gateway, how do I paste commands from the clipboard?
  
 **Answer**: Use the browser menu to paste from the clipboard.

 .. image:: images/FAQ_SSHwindow.png

3. I have just received an email from AWS for request to authorise email address to be used with Amazon SES and Amazon Pinpoint in region US East (N. Virginia). Can I check this is triggered by you and not a phishing email?
 
 **Answer**: This is to verify your email address so that Research Gateway can send you a daily End-Of-Day report if any instances are left running. The report will act as a reminder to turn off the system. So we would recommend to go ahead and verify your email through that link sent out via AWS.

4. The costs that are shown in Research Gateway are less than what I am seeing in my AWS console.
 
 **Answer**:  The costs shown in Research Gateway are the direct costs (costs that can be ascribed to the products created by PI or Researchers in the project). Directs costs may take up to 24 hours to show under the direct costs. To avoid higher API costs, we only update the costs once a day at 12:00 AM UTC time. There are a few shared products like the project-storage and the ALB that is created for SSL connections. That cost is not shown as part of the direct costs. There will also be some costs which are shared costs (e.g. Data Transfer, API calls etc.) which will be on your bill but not shown in the direct costs.

5. I have started a rstudio machine and installed something. The machine was stopped now, why is that the case?
 
 **Answer**: RStudio machines have an idle detection script that will stop the machine after 15 minutes of inactivity. The Idle timeout is actually based on the Rstudio interface and not the SSH session. You can however modify the timeout period by editing the below mentioned file in your instance /usr/local/bin/check-idle : Ln. No - 12 (MAX_IDLE_MINUTES = 15). You can specify your timeout period in minutes or set it to 0 to disable the feature.

6. I added an AWS account and created a project in Research Gateway. However the cost always shows zero even though I have provisioned workspaces.
 
 **Answer**: This indicates that you have not approved the cost_allocation tags in your payee account. Research Gateway tags all resources with certain tags so that we can track the costs. However AWS requires that cost allocation tags be first approved in the payee account. Your account may be a payee account (in which case you might be able to follow the instructions in the link yourself). More often than not, there is a master account which IT controls which is the payee account. The consumption accounts are child accounts of that master account. In this latter case the cost allocation tags need to be approved in the payee (master account).  Note that products created before the tags are approved will not be tracked for cost. See the procedure for :ref:`Cost allocation tags activation<Cost_allocation>`.

7. My First Name or Last Name is incorrect. How can I correct it?
 
 **Answer**: Please contact rlcloudsupport@relevancelab.com.

8. I provisioned a product but received an error "You have requested more vCPU capacity than your current vCPU limit of N allows for the instance bucket that the specified instance type belongs to."
 
 **Answer**: It looks like you have hit an AWS Service Quota limit. Please contact your Principal Investigator or IT Administrator who manages your AWS account and ask them to create a support case with AWS for a `service quota <https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ limit increment.

9. I provisioned a product but it is stuck in "Transitioning". How can I connect to the system?
 
 **Answer**: This should occur very rarely. Please contact rlcloudsupport@relevancelab.com.

10. I received a verification link when I registered for Research Gateway (or when my Principal Investigator invited me). However when I click on the link, I get an error that says the link has expired.
 
 **Answer**:  The link expires in 24 hours for security reasons. You can ask your PI to "Resend the verification link" from the user management screen. If you are still facing an issue, you can send an email to rlcloudsupport@relevancelab.com.

11. how the user can connect to their workspaces using an external SSH client?

 **Answer**: For linux product you have to do 
 
 ssh -i </path/to/pem/file>  <user-name>@<ip-address>

 In this user-name is ec2-user for Amazon Linux 2 workspaces and ubuntu for Ubuntu workspaces and rstudio for RStudio workspaces.

 To get the public-ip-address:
 1. Click on the Project card
 2. Click on My Products tab
 3. Click on any Product card(Nextflow Advanced , Rstudio etc) 
 4. Click on Outputs tab
 5. Scrolling down in the Outputs tab will show you InstanceIPAddress domain where you will get public-ip-address.

 If you are connecting from a Windows box you can use an SSH client like `PuTTY <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html>`_.

 1. Click on the project on the “My Projects” page.
 2. Navigate to the “My Products” tab
 3. Click on your instance in the My Products view. 
 4. In the product details page, you will find the SSH/RDP button in the Connect pane on the right side. Click on the button to launch the SSH Launcher window in a separate tab of your browser. 
 5. Enter a username and select the authentication type from the list and upload the Pem file and click on submit. The SSH window should open.

 If you are unable to connect, check your current IP address against the “AllowedSSHLocation” parameter provided at provisioning time.

