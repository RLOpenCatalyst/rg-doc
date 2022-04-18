Getting Started
===============

Research Gateway is a cloud-based solution that makes it possible for researchers and other consumers of High Performance Computing to easily access resources in the AWS cloud.
RLCatalyst Research Gateway is designed for simplicity and you can get started very quickly. 
You can access this product either as a SAAS model.

.. .. _hosted Silo model: https://relevancelab.com/2021/02/11/8-steps-to-set-up-rlcatalyst-research-gateway/

If you are using the Enterprise model, you will be provided a public URL to which you can navigate using your browser. 
You will be given credentials for the Administrator user.

If you are using the SAAS model, you can sign up with your details. Use details from :ref:`Accessing the RLCatalyst Research Gateway` to create a new user.

.. contents::

Enterprise Model
--------------------


.. Setting up your RLCatalyst Research Gateway for use involves the following steps.

.. .. image:: images/FirstSetupTask.png 

Users with the Administrator role can perform the steps below.

  * :ref:`AccessingRG<AccessingSignIn>` - Users could have Administrator, Principal Investigator or Researcher roles.
  * :ref:`Features<Adding Organizational Units>` for looking at updating Organizationl units and other features like budgets,Audit trail and Users.
  * :ref:`Add Account` 
  * :ref:`Adding Catalog Items<Catalog>` 


  .. * :ref:`Add an Organizational Unit<Adding Organizational Units>`
  .. * View `Adding Organizational Units`_  
  .. * :ref:`Add AWS Accounts for projects<Adding AWS Accounts>`  
  .. * View `Budgets`_
  .. * View the `Audit Trail`_
  .. * Add or Assign `Users`_
  .. * Assign :ref:`Catalog` Items 
  
Users with the Principal Investigator role can perform the steps below.
  
  * :ref:`Accessing the RLCatalyst Research Gateway` - Users could have Administrator, Principal Investigator or Researcher roles.
  * :ref:`Project ordering` to create projects.
  * :ref:`Adding Users<Users_PI>` - Users can have Principal Investigator or Researcher roles.
  * :ref:`Add Account`  
  * :ref:`Adding Catalog Items<Catalog>`
  * :ref:`KeyPair`:for creating the key pairs.
  * :ref:`Studies` for creating the Studies.
  * `Assigning Researchers to projects`_

Users with the Researcher role can perform the steps below.
  
  * :ref:`Accessing the RLCatalyst Research Gateway` - Users could have Administrator, Principal Investigator or Researcher roles.
  * :ref:`Project ordering` to create projects.
  * :ref:`KeyPair`:for creating the key pairs.
  * :ref:`Studies` for creating the Studies.

  
SAAS Model  
-------------  

 Users with the Principal Investigator role can perform the steps below.
  
  * :ref:`Accessing the RLCatalyst Research Gateway` - Users could have Administrator, Principal Investigator or Researcher roles.
  * :ref:`Project ordering` to create projects.
  * :ref:`Adding Users<Users_PI>` - Users can have Principal Investigator or Researcher roles.
  * :ref:`Add Account`  
  * :ref:`Adding Catalog Items<Catalog>`  
  * :ref:`KeyPair`:for creating the key pairs.
  * :ref:`Studies` for creating the Studies.
  * `Assigning Researchers to projects`_

 Users with the Researcher role can perform the steps below.
  
  * :ref:`Accessing the RLCatalyst Research Gateway` - Users can have Administrator, Principal Investigator or Researcher roles.
  * :ref:`Project ordering` to create projects.
  * :ref:`KeyPair`:for creating the key pairs.
  * :ref:`Studies` for creating the Studies.


Create an Admin user
--------------------

If you have subscribed to the Enterprise model of the Research Gateway application, you would have created the Admin user during registration.
You would have subsequently received an email with a link to confirm the Administrator user's email. Use these details to login into Research Gateway.



.. .. _`Adding Organizational Units`:

Adding Organizational Units
---------------------------

To plan the creation of a new Organization, use the planning sheet in :ref:`Appendix A<Appendix A>` to collect all the information required upfront. Login into the Research Gateway. User landed to the  main dashboard.

.. image:: images/OrganizationPage.png

Click on the “+Add New” icon  which is at the top right corner. Organization form is opened.

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Field
     - Details
   * - Organization Name
     - <Name of the Organization> 
   * - Organization Description
     - <Description>
   * - Account Details
     - <Select account ID from the list or create new account through **"Add Accounts"** button >
   * - Add Users
     - <Select Principal Investigator ID from the list or create new one through **"Add users"** button > [Optional]
	 
Click on the **“Create Organization”** button. The new organizational unit is added successfully.

.. image:: images/addorg.png

**NOTE**: You can create an organization without Principal Investigator. Through the "Assign O.U." option in users, you can assign later.

The Organizations page of the Research Gateway lists all the existing organizational units created, with some details of each organization displayed on the card. 

.. .. _`Adding AWS Accounts`:

Adding an AWS account to use in a project
---------------------------------------------

Login into the Research Gateway. Click on dropdown bar which is above the header. Choose the  “Settings” option


.. image:: images/mainview.png 

Click on  the  “Settings” menu item. Provider settings page is opened.

.. image:: images/Provider2.png 
   :name: Provider Settings Page
   
**Note:**  When we add the settings please make sure the user credentials has the IAMFullAccess/AdministratorAccess Permissions. You can refer the list of policies that we are using create the role in Research Gateway.

Click on  the  “+Add New” button in the provider setting page. The Add Provider setting dialog-box is opened.

.. image:: images/AddAccount.png
   
Fill the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Attribute
     - Details
   * - Account Name
     - <Account Name>
   * - Account Key
     - <Account Key> [It should be a minimum of 16 characters and a maximum of 128 characters]
   * - Secret Key
     - <Secret Key> [It should be a minimum of 40 characters and a maximum of 128 characters]
   * - Region
     - <Select region from the drop-down list> 
   * - Account Number
     - <Enter an AWS Account Number> [It should be a 12-digit number]
   * - Network Configuration
     -
   * - Use deafult VPC
     - <If you enable this option, Research Gateway will check if a default VPC exists and will create one if it does not exist. If you disable this option, provisioning resources from Standard Catalog may fail.>
   * - Use SSL with ALB
     - <If you enable this option, Research Gateway can set up secure connections to your resources by putting them behind an Application Load Balancer with SSL connections using certificates managed by AWS Certificate Manager. Check this box if you would like to create an ALB for this project. An ALB will incur costs irrespective of traffic passing through it.>	 
   * - Storage Configuration
     -
   * - Use Project Storage	 
     - <Research Gateway will setup a shared S3 bucket (project storage) where the team members can store data. This shared storage will be mounted into all supported workspaces. Storage costs will be accounted at the project level. Note: For now defaultly it will create the project storage.>
	 
Click on the "Verify" button, it will check the provided details are valid or not. If details are valid, it will show verified account message with green color tick mark below the header otherwise it will throw an error message accordingly.

Click on the “Add Account” button. An AWS account is added successfully. You can see all the account details in a table format.

**NOTE**: 

1. The "Add Account" button was disabled until the details are verified.
2. Please ensure that the IAM user whose credentials you entered has the IAMFullAccess/AdministratorAccess policy attached otherwise, it will through an error message accordingly.

On each line item there is a contextual menu. Through this we can delete and sync the account/repair the account.

.. image:: images/Project.png

Click on the 3-dotted icon which is available at the right side of the account details page and choose “Delete” option. A confirmation dialog box is opened and enable the check box and click on the "Delink" button, the account will be deleted. You can only delete provider settings that are not linked to any project or organization.

.. image:: images/delete.png

Research Gateway works in conjunction with AWS Service Catalog. To synchronize the Service Catalog to your project, select the Product Sync option.
Click on the “Sync Now” button. Once the synchronization is started you should see the “Sync Started” message.

.. image:: images/sync1.png

.. image:: images/sync2.png

**Note**: The "Sync Now" option can get the products from the shared, local, account and organization level portfolio.

Click on the contextual menu which is available at the right side of the account name and choose the "Repair" option. 

.. image:: images/repair1.png

Fill the access key and secret key values in the assigned boxes and click on the "Verify" button.

.. image:: images/repair.png

On successful completion of verify you can see the "repair" option, click on the button in the window, the account will be repaired.

Click on the contextual menu which is available at the right side of the account name and choose the "Assign O.U" option. One window is opened and all organizational units are listed there. Choose one organization from the list and click on the "Assign" button. On successful completion you can see the green color toaster message.

.. image:: images/Assign123.png

.. image:: images/Assign4.png

**Note** : When the account is not linked to any other organizations than only you can see the "Assign O.U" option.


Assigning Researchers to projects
---------------------------------

There is an edit functionality for the project entity. The project is independent of the researcher. A user can create an empty project and add researchers later also. Click on “Manage (i.e., Pencil icon)” which is at the Assigned researchers field in the Project Details Page.

.. image:: images/projectdetails1.png 

Select the Researchers and click on the “Update List” button. You can see the “Updated Successfully” toaster message in the UI. You can't unselect the researchers who have associated products. 
 
.. image:: images/researchers.png 
 
.. image:: images/update.png
