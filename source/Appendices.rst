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


v1.19.0
^^^^^^^^

Features: 
----------

1. Ingress Gateway Project. This is a new project type that can be created against an account enabled for Secure Research Environments. This project is meant for researchers to be provided a storage area where they can upload files that they want to bring into a secure project. An Ingress Storage s3 product will be automatically created as part of project creation. The researchers can upload files via the UI and then submit an ingress request. After approval, these files are made available in the IngressStore folder that is mounted to their workspaces. 

2. New additions to the catalog: JupyterLab and VS Code products. JupyterLab is a popular open-source software package that provides a highly extensible notebook authoring and editing environment. It offers advanced features and customization options compared to Jupyter Notebook. VS Code is a lightweight yet powerful open-source code editor on Linux. It provides built-in support for JavaScript, TypeScript, and Node.js, along with an extensive range of extensions for various languages and runtimes like C++, C#, Java, Python, PHP, Go, and .NET. 

3. Integration with Egress application. With this integration, researchers will have an EgressStore folder automatically mounted to their workspaces. They can copy files that they want to extract from the SRE into this folder and submit an Egress Request. The request must be approved via the Egress Application and can be downloaded by the Information Governance lead after approvals. 

4. Secure Research: Users will be able to add Secure Research Environment accounts and Secure Research Projects from the 'Add Accounts' and 'Add Projects' screens, provided they meet the preset requirements in their Organizational Unit (OU) and upon login. 

5. Keypairs: Keypairs will be fetched based on the ProjectID.  

6. Name Modification: Users will now encounter the term 'Secure Research Environment' instead of 'Trusted Research Environment.' 

7. RStudio product: The Authentication screen will be removed from the product. 

8. Add project Screen: If all the required input parameters are not set, users will receive an error toaster message. For example, if a user tries to create a Secure Research Project or Data Library Project after creating a Secure Research Environment account without meeting all requirements, they will be restricted and see an error toaster message on the 'Add Project' screen.  

9. Secure Research Linux product: Users should be able to view the 'Instance Type' action on the Product Details page for the Secure Research Linux product. Additionally, Load Balancers will be created during the Secure Research Project creation. 

10. A confirmation dialog box will be displayed for the 'stop' action in the PCluster Product. 

11. Enhanced Nice DCV product: Users can now view the 'Instance Type' action on the Product Details page for the Nice DCV product. 

12. IGV-Viewer product: VPC and Subnet will no longer appear as input parameters in the product launch form. 

13. Keyboard Accessibility fixes. 

14. Security fixes. 

  
Bug-fixes: 
----------
  

1. Internal Studies: When a user attempts to assign or create two studies with the same name for the same project, they shall receive an error toaster message. 

2. Users can delink an account even if the account is linked to an internal study. 

3. Assign product to project: If the stack is created twice during the assign action on the catalog page, duplicate products were being assigned to the project and were visible in the available products tab. 

4. Events page: Users were unable to see the respective project name under the 'project creation started' event. 

5. Project status: The 'Active' status for a project will now be updated after the completion of all steps. 

6. Researcher login: If a user is assigned to an OU without a project, they should see an appropriate message on the Budgets screen. 

7. When a user creates and deletes a project with an ALB (Application Load Balancer) simultaneously, it should not cause conflicts during the creation and deletion of the ALB. 

8. Screen refresh count: The screen refresh count will be minimized during multiple project creation. 

9. Storage creation issue: If a user unchecks the 'Project Storage' checkbox, selects an account in the project creation form, and clicks on the 'Create Project' action, the project will still be created with storage. 

10. SAML Login: After successful authentication, users will be redirected to the home page without any issues. 

 
v1.18.0
^^^^^^^^

Features
--------

1. Secure Research Linux Desktop. This product operates in a custom-created VPC with no internet access. It is accessed through a browser via a secure NICE DCV-based connection which provides access to a MATE desktop environment. It allows for Trusted Research environments to be created which are isolated from external access. The Secure Research Linux Desktop comes with a Chrome browser, docker engine, and miniconda pre-installed on the machine.

2. Encrypted S3 buckets. The S3 product in the standard catalog now allows for data to be encrypted using either an AWS-managed key or a customer-managed KMS key. This enables data at rest to be encrypted to meet security and regulatory needs.

3. Public studies can be mounted to workspaces. The studies available from the Registry of Open Data on AWS (RODA), can now be assigned to projects from the study details page. Once assigned to a project, the study appears in the Study Selection pane in the launch form for a researcher to select during the creation of a workspace. The selected study is then mounted to the workspace and can be used.

4. Internal studies can be created in read-write mode. This allows the PI to create studies that can be updated by researchers generating new data or when they want to share outputs with other researchers using the same study.

5. Internal studies can be deleted. 

6. Project labels are editable. This feature has been a long-standing customer request. The name of a project can now be edited and changed to suit the customer's needs.

7. Support for SPAC in PCluster product. The user now has the option to install SPAC during the provisioning of a PCluster workspace. This provides an easy method to install other software like GROMACS or Open FOAM used in High-Performance Computing.

8. Subscription Renewal Date is enforced. Users can no longer log in beyond the subscription renewal date.

9. New IGV Viewer product in the catalog. IGV Viewer is an important open-source tool in genomics analysis and this was a demand from some of the customers who want to perform genomics analysis.

10. Updated NICE DCV standard catalog item. The NICE DCV product in the standard catalog has been updated with a newer version of the NICE DCV server. The workspace now comes with Chrome browser, docker engine, and miniconda pre-installed and the User interface uses the MATE desktop environment.

11. Keyboard accessibility improvements

12. Security improvements

Bug-fixes
---------

1. Admin: My Organizations: Organization Name Alignment issue.

2. In the login screen after entering a username and password and clicking on enter it is viewing the password, instead of logging in.

3. Create appropriate audit message and status for "delete setting" and "project storage terminate".

4. Navigating from the Product launch form to the Create study section, if there is no Internal Study for the user, gives an error.

5. Error in updateBudgetForAccount.

6. Error in terminateProvisionedProduct - Provisioned product not found.

7. When the EBS product terminates getting the following error "This bucket is shared with other researchers, please check with them and disconnect any Sagemaker notebooks connected to it before terminating."  but there is no Sagemaker product in the project.

8. Error handling in login with an appropriate message. And add a logger during reset-password with the user name.

9. Added audit events for PROJECT_CREATION_STARTED and PROJECT_CREATION_COMPLETED. 

10. In the PCluster product switch the Parameter Names based on the Scheduler type.

11. During project creation, if the S3 templates bucket is inaccessible, the user should see an error on the project events page. 

12. On the Study s3 explore page, the "Actions" drop-down button should not be visible if the user selected one or more than one folder. Also, it should handle duplicate folder prefixes.

13. Project creation throws an error that the S3 bucket quota is reached even when the project storage requirement has been unchecked.

14. In the Catalog page, if the stack creation fails, the existing product check mark should not be shown.

15. During Project Sync, Keypairs should be Inserted only if they have a valid project tag.

16. When a project is being deleted, all the keypairs for that project in the Research Gateway database should be deleted.

17. In the Catalog page, if we click "Assign product to project" twice, the stack is created twice. So duplicate products getting created.

18. During Project Creation, if multiple copies are created, Project Storage creation fails because of duplicate namespace values passed to the different stacks.

19. In the internal study, when I try to link compute resources and check assigned projects in study details, the same project name appears three times. It happens the same with unlinking as well.

20. In the Catalog page, show all existing tags in the dropdown.

21. Users with the Researcher role shall only be able to view studies that are assigned to the projects they are a part of.

22. Store created_on and updated_on in accounts collection. Add column "Last Updated" in the billing accounts table

23. If an Internal Study has no project assigned, we have to be able to delete it.

24. Upgrade Mongoose to 6.10.1

25. EC2-NICE-DCV: NiICE DCV-based products should be accessible through a one-time-usable URL.

26. Prevent users who are not assigned to any organization from performing any actions.

27. Notifications should be handled gracefully during post-provisioning when public IP is not found.


v1.17.0
^^^^^^^^

Enhancements
-------------

1. Support for mounting Internal Studies to Sagemaker instances. Users can now use the "Study selection" section of the Launch form, to select studies that should be mounted to Sagemaker instances. The studies, so selected, will appear under the $HOME/studies folder.

2. New Billing Accounts screen - All accounts added to an organization will now be visible in the Billing Accounts screen to help the user track their overall spend in the AWS account. This screen shows the current AWS billing for that account (total across all regions including consumption from Research Gateway and externally). This screen also shows the forecast for the current month.

3. Bulk user tag updates. Importing users via CSV now has the capability to update tags for existing users. Tags have to follow the same constraints (maximum of 32 characters, maximum of 5 tags) and are updated in an all or none manner.


Bug-fixes
----------

1. Archived projects that had crossed the budget thresholds were reappearing as Stopped projects when Cost Control feature is on.

2. User edit function was not creating audit trail events.

3. Keypairs created in one project were appearing in another project if the associated account had more than one project linked to it.

4. A user who is not assigned to any organization was getting incorrect message on logging in.

5. Search function in the catalog should show all products - assigned or unassigned.


v1.16.0
^^^^^^^^

Enhancements
-------------

1. Attach secondary EBS volumes created via the project catalog to EC2 Linux based instances i.e., EC2 Linux, RStudio, Chenlab, Cromwell Advanced etc. 

2. Amazon EBS volumes can now be created via the Available Products catalog.  

3. PCluster product now offers the user the choice to mount a secondary EBS volume to the head node 

4. Admin and Principal Investigators can edit user Information like the First name, Last name, Organizational Unit (editable only if user was previously not assigned to any Organizational unit) and tags. 


Bug-fixes
----------

1. Admin: Budget Screen: able to see archived projects in organization also budget assigned is divided among archived projects as well. This is inconsistent with the view that PI has. 

2. Alignment issue fixes in Project creation screen Add User form, My Projects, Product Details page, Study Details Page. 

3. UI inconsistency fixes in My Products tab, Project Details page breadcrumb, Project Details page Events tab. 

4. Admin: User: after switching to table view and searching for particular user pagination action is not working. 

5. Add user form is breaking when user click on the add user button from Create project and Create organizations screen. 

6. On the study screen users are not able to search in the tag fields. 

7. Admin: User management: Unable to sort by User Roles. 

8. SSH Window: User Name should be shown in white colour while typing 

9. Admin login: Users Screen: some user cards are showing empty in card and table view 

10. User Screen: Reset filter issue fix. 

11. Audit trail page: Select a value filter: items in the drop down should be sorted in alphabetical order. 

12. Users Screen: Sort by filter: AESC and DESC both are showing same behaviour 

13. Researcher login: My products tab: when we select any filter (All/Research/IT Application) in Available Products tab and enter My Products tab same filter selection is reflected instead of All/Active/Terminated filters. 

14. Studies: Search action: Space is not allowed in between words.  

15. Keyboard Accessibility fixes for My Projects page and Budget KPI cards of Project Details page. 

16. When User role is selected as Admin, the Organizational Unit field will be disabled in Add User form. 

17. Research Gateway now uses distroless container images as the base images for Research Gateway software to reduce the attack surface created by unnecessary software components included in the image. 

18. Budgets: product provisioned time should be shown on basis of logged in user’s time zone 

19. Security fixes. 


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
   
   * Project Details table: This table shows all the Active products per project and the month to date and cumulative cost per project. It also shows a single line item for the cumulative month-to-date and cumulative cost of Terminated products. 
#. For each provisioned product User will now be able to see Created on Parameter in Product Details Tab which will indicate the Product Creation Date.
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

2. Which AWS regions are supported by RG?

 **Answer**: RG is currently supported in us-east-1, us-east-2, us-west-1, us-west-2, ca-central-1, eu-central-1, eu-west-1, eu-west-2, ap-northeast-1, ap-southeast-1, ap-southeast-2, ap-northeast-2, sa-east-1.

3. how can i login into Research Gateway as Admin?

 **Answer**: Please visit the following link to login to Research Gateway as Admin: " add proper link", Login with proper username and password.

4. If the user is unable to login into research gateway with password what are the ways to resolve it?

 **Answer**: Below are the ways to resolve the login issue

 1. Check if you are using the correct password. 
 2. Check if you are using the correct case for the password. 
 3. Check if your browser is storing your password. 
 4. Clear your browser cache and cookies. 
 5. Try logging in from a different browser.
 6. Contact Research Gateway support for help.
 7. You can reset you password by clicking on Forgot Password link on the login page.
 
5. How can user reset the password?

 **Answer**: User can reset his password by clicking on the Forgot Password link on the login page. User can add his email address in input field and click on "Send Reset Link" button. User will be sent an email with a link to reset his password.

6. What are the special characters that can be included in password?
   
 **Answer**: The password must contain at least one lowercase letter, one uppercase letter, one number, and one special character. The special characters are:= + - ^ $ * . [ ] { } ( ) ? ! @ # % & / , > < ‘ : ; | _ ~

7. What is the password policy in research gateway? 

 **Answer**: The password policy for Research Gateway is 8 characters minimum and 16 characters maximum, 1 lowercase letter, 1 uppercase letter, 1 number, and 1 special character.
 
8. My First Name or Last Name is incorrect. How can I correct it?
 
 **Answer**: Please contact rlcloudsupport@relevancelab.com.
 
9. I received a verification link when I registered for Research Gateway (or when my Principal Investigator invited me). However when I click on the link, I get an error that says the link has expired.
 
 **Answer**: The link expires in 24 hours for security reasons. You can ask your PI to "Resend the verification link" from the user management screen. If you are still facing an issue, you can send an email to rlcloudsupport@relevancelab.com.

10. I am from the Ap-Notheast-1 region; shall I add an account in that region in RG?

 **Answer**: No , we can Add Account in specific regions only,by customer request ,New region will be add on Research Gateway

11. How can i sign up for a new account?

 **Answer**: In a browser window, open the Research Gateway URL (https://research.rlcatalyst.com/login).

 1. Click on the “Sign up for new account” link which is below the sign-in button.
 2. A registration form will be opened.
 3. Fill in the proper detail
 4. Click on the “Sign Up“ button. If the provided details are valid, you will receive a verification link on the registered email address to reset the password. On clicking the link in the email, you will be led to the change password screen.
 5. The password needs to confirm to the password policy.
 6. If the password change is successful you will be navigated to the verification successful page. Through the “Click here to login button” you will be navigated to the Research Gateway login screen.
 7. Once logged in to your account, you will land on the Welcome page in Research Gateway.

12. How can i sign in with google into portal?

 **Answer**: Please click on the google sign in button on the login page.

13. How many researchers can I add at a time on Research Gateway?
 
 **Answer**: You can add 20 researchers at a time on Research Gateway		

14. What are the project states in Research Gateway?

 **Answer**: A Project can be in one of the following states: Active, Paused, Stopped, Failed

15. What are the actions user can perform on project?

 **Answer**: Once the project is active, user can perform Pause/Resume/Stop/Archive/Add Budget actions on a project.
 
16. How to add budget to project?

 **Answer**: The “Add Budget” action will provide Principal Investigators with a way to add more budget to the project. Clicking on the “Add Budget” button will bring up a dialog box where you can add any whole number greater than 0.
 
17. I added an AWS account and created a project in Research Gateway. However the cost always shows zero even though I have provisioned workspaces.
 
 **Answer**: This indicates that you have not approved the cost_allocation tags in your payee account. Research Gateway tags all resources with certain tags so that we can track the costs. However AWS requires that cost allocation tags be first approved in the payee account. Your account may be a payee account (in which case you might be able to follow the instructions in the link yourself). More often than not, there is a master account which IT controls which is the payee account. The consumption accounts are child accounts of that master account. In this latter case the cost allocation tags need to be approved in the payee (master account).  Note that products created before the tags are approved will not be tracked for cost. See the procedure for :ref:`Cost allocation tags activation<Cost_allocation>`.
 
18. Will the user get any email on budget alert?

 **Answer**: Yes, User will get an email alert if your budget is going to be exceeded.

19. Why am I not seeing any costs getting updated in my project?

 **Answer**: For Research Gateway to pull the cost information from your AWS account, you need to approve the cost allocation tags in your payer account. Check if you have done that.

20. What are the user roles supported in Research Gateway?

 **Answer**: Research Gateway supports the following roles:

 1. Administrator. Can create OUs, add accounts, create users, assign users and catalog items to OUs.
 2. Principal Investigators. PIs are associated with one OU and within that OU they can create users, add accounts, create projects, assign users and catalog items to projects.
 3. Researchers are associated with a single OU and can create and use resources within the projects that they are a member of.		

21. What is the difference between a Principal Investigator role and a researcher role?
    
 **Answer**: Principal Investigators are the main point of contact for the project. They are responsible for managing the project and its resources. Researchers are the users who will be using the resources in the project. They can create and manage resources, but they cannot manage the project itself.

22. Can there be more than one Principal Investigator in a project?

 **Answer**: Yes, there can be more than one Principal Investigator in a project.
 
23. As an Administrator user what actions can I perform?

 **Answer**: As an Administrator you can create OUs, add accounts, create users, assign users and catalog items to OUs.

24. As Principal investigator what actions can I perform?

 **Answer**: Principal Investigators are associated with one OU and within that OU they can create users, add accounts, create projects, assign users and catalog items to projects.                                                                                                                  Principal Investigators can create users, add accounts, create projects, assign users and catalog items to projects, provision resources from the project, and manage budgets.

25. As a researcher user what actions i can perform?

 **Answer**: Researchers are associated with a single OU and can create and use resources within the projects that they are a member of.

26. Can you name some of products in Research Gateway?

 **Answer**: Below are the list of products in Research Gateway:

  1. Amazon EC2 Linux
  2. Amazon EC2 Windows
  3. Amazon S3
  4. Amazon Sagemaker
  5. RStudio
  6. Nextflow Advanced
  7. Cromwell Advanced
  8. Docker on Amazon EC2 Linux
  9. My SQL
  10. Ubuntu 20 04 on Amazon EC2
  11. PCluster
  12. FSx For Lustre
  13. NICE DCV on Amazon EC2 Linux 
  14. Amazon EFS
  15. Amazon EBS
  16. Secure Research Linux Desktop
  17. Integrated Genomics Viewer
  18. JupyterLab
  19. VS Code

27. What are the different provisioned product status?
    
 **Answer**: The provisioned product status can be: Active, Failed, Creating, terminating, terminated. stopped  

28. I provisioned a product but received an error "You have requested more vCPU capacity than your current vCPU limit of N allows for the instance bucket that the specified instance type belongs to."
 
 **Answer**: It looks like you have hit an AWS Service Quota limit. Please contact your Principal Investigator or IT Administrator who manages your AWS account and ask them to create a support case with AWS for a `service quota <https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ limit increment.

29. I provisioned a product but it is stuck in "Transitioning". How can I connect to the system?
 
 **Answer**: This should occur very rarely. Please contact rlcloudsupport@relevancelab.com.

30. In the in-browser SSH window in Research Gateway, how do I paste commands from the clipboard?
  
 **Answer**: Use the browser menu to paste from the clipboard.

 .. image:: images/FAQ_SSHwindow.png

31. I have just received an email from AWS for request to authorise email address to be used with Amazon SES and Amazon Pinpoint in region US East (N. Virginia). Can I check this is triggered by you and not a phishing email?
 
 **Answer**: This is to verify your email address so that Research Gateway can send you a daily End-Of-Day report if any instances are left running. The report will act as a reminder to turn off the system. So we would recommend to go ahead and verify your email through that link sent out via AWS.

32. The costs that are shown in Research Gateway are less than what I am seeing in my AWS console.
 
 **Answer**:  The costs shown in Research Gateway are the direct costs (costs that can be ascribed to the products created by PI or Researchers in the project). Directs costs may take up to 24 hours to show under the direct costs. To avoid higher API costs, we only update the costs once a day at 12:00 AM UTC time. There are a few shared products like the project-storage and the ALB that is created for SSL connections. That cost is not shown as part of the direct costs. There will also be some costs which are shared costs (e.g. Data Transfer, API calls etc.) which will be on your bill but not shown in the direct costs.

33. I have started a rstudio machine and installed something. The machine was stopped now, why is that the case?
 
 **Answer**: RStudio machines have an idle detection script that will stop the machine after 15 minutes of inactivity. The Idle timeout is actually based on the Rstudio interface and not the SSH session. You can however modify the timeout period by editing the below mentioned file in your instance /usr/local/bin/check-idle : Ln. No - 12 (MAX_IDLE_MINUTES = 15). You can specify your timeout period in minutes or set it to 0 to disable the feature.

34. how the user can connect to their workspaces using an external SSH client?

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

35. I terminated all my  provisioned products; does that consume any indirect costs for AWS after that?

 **Answer**: Inorder to stop cost consumption for AWS you should delete Account from the settings.
 
36. Can I share my research study data with researchers under the project?

 **Answer**: Yes
 
37. When launched products fail, how can I get those logs to debug as a researcher?

 **Answer**: You can get the logs from the CloudWatch logs.
 
38. Can resources provisioned by one researcher be shared with another user in the project?

 **Answer**: Yes, resources provisioned by one researcher can be shared with another user in the project.

39. How can a user share a resource in the project?
    
 **Answer**: A user can share a resource by clicking on the share button on the product details page. A resource can only be shared with the entire project. Once shared, a resource cannot be unshared and will be visible to all project members.

40. What are actions a user can take for a product?

 **Answer**: The actions a user can take depends on the product. Common actions for active products include stop, share, Terminate, reboot, SSh\rdp, Remote desktop, Open link, etc also if we have any Secondary EBS product launched in same availibility zone as applicable products then we can also perform Attach and Detach Volume action. for failed products we have terminate action, for stopped products we have start, terminate instance type actions etc.
