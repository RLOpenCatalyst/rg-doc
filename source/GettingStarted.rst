Getting Started
===============

Research Gateway is a cloud-based solution that makes it possible for researchers and other consumers of High Performance Computing to easily access resources in the AWS cloud.
RLCatalyst Research Gateway is designed for simplicity and you can get started very quickly. 
You can access this product either as a `hosted SaaS product`_ or as an Enterprise product.

.. _hosted SaaS product: https://relevancelab.com/2021/02/11/8-steps-to-set-up-rlcatalyst-research-gateway/

If you are using the hosted version, you will be provided a public URL to which you can navigate using your browser. 
You will also be provided with the credentials for the Administrator user.

If you are using the Enterprise version, your IT department will provide you a URL to access the product. You can set up an Administrator user by following the steps below.

.. contents::

Planning your set up
--------------------

Setting up your RLCatalyst Research Gateway for use involves the following steps.

Users with the Administrator role can perform the steps below.

  * :ref:`Adding Users<Adding Users>` - Users can have Administrator, Principal Investigator or Researcher roles.
  * `Adding AWS Accounts`_
  * `Adding Organizational Units`_

Users with the Principal Investigator role can perform the steps below.
  
  * `Adding a New Project`_
  *  Assigning Researchers to projects

Create an Admin user
--------------------

Get started by first creating an Admin user account for your instance of RLCatalyst Research Gateway.

Sign-In Process
---------------
Use details from *`Appendix A`__* for  User Name, Password as per password policy.

Fill the following details 

.. list-table:: 
   :widths: 50 50
   :header-rows: 1

   * - Field
     - Details
   * - Username
     - <Username that is used for login>
   * - Password
     - <Password for this user>
	 
Click on the “Sign-In“ button. We can log in successfully.

.. image:: images/login.png

	
Forgot Password
---------------
A user sees a “Forgot Password” link on the login screen which is under the "Sign In" button.

.. image:: images/login.png

On clicking the link the user is navigated to the reset password screen.  

.. image:: images/forgot.png

Fill the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Field
     - Details
   * - Username
     - <Username that is used for login>
   * - E-mail address
     - <Registered Email ID>
   
Click on "Send Resend link" button. If the provided details are valid, he will get a verification link that has been sent to his email to reset the password. On clicking the link in the email, the user is prompted to change password screen.  

.. image:: images/verificationemail.png

The password change is either successful or unsuccessful (this will be like verification success and error screens).  The user is then redirected back to the login screen.

.. image:: images/password.png

.. image:: images/success.png

Sign-Up process
---------------

An Administrator can add a new user to the system. See the :ref:`Adding Users<Adding Users>` section for details.
When an Administrator adds a user to the systen, the user will receive a verification email with a link. When the user clicks on the link he is led to a page where he should change his password.

The password needs to conform to the password policy. 

.. image:: images/verificationemail2.png

On successful validation, users  will be allowed to login into the Research Gateway. 

.. _`Adding Organizational Units`:

Adding Organizational Units
---------------------------

To plan the creation of a new Organization, use the planning sheet in *`Appendix A`__* to collect all the information required upfront. Login into the Research Gateway. User landed to the  main dashboard.

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
   * - Account ID
     - <Select ID> [Multiple AWS accounts to be  linked.Here we have a list]
   * - Principal
     - <Select Principal ID > [Select from the list one or more users with the Principal Investigator role]

Click on the **“Add Organization”** button. The new organizational unit should be added successfully.

**NOTE**:We are selecting a specific AWS account when adding new organization. This links the account to organizations. The organization form allows multiple Account IDs and multi-select on the Principal Investigators list.


The Organizations page of the Research Gateway lists all the existing organizational units created, with some details of each organization displayed on the card. Clicking on a specific organization shall lead to “View Organization Details” window .

.. image:: images/ViewOrganizationDetailsPage.png


.. _`Adding AWS Accounts`:

Adding an AWS account to use in a project
---------------------------------------------

Login into the Research Gateway. Click on dropdown bar which is above the header. Choose the  “Settings” option


.. image:: images/Providersettings.png 
   :name: Provider Settings menu item

Click on  the  “Settings” menu item. Provider settings page is opened.

.. image:: images/Provider2.png 
   :name: Provider Settings Page

Click on  the  “+Add New” button. The Add Provider Setting dialog-box is opened.

.. image:: images/AddProviderNew.png 
   :name: Add Provider Settings screen

Fill the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Attribute
     - Details
   * - Account Name
     - <Account Name>
   * - Account Key
     - <Account Key>
   * - Secret Key
     - <Secret Key>
   * - Region
     - <Region>
   * - Account Number
     - <AWS Account Number>


Click on the “Add” button. AWS account was added successfully and will show in the table of providers in the Provider Settings page.

On each line item there is a contextual menu. Through this we can edit, delete or sync the account.

.. image:: images/Project.png

Click on the 3-dotted icon which is available at the right side of the account details page and select “Edit” option. Provider settings page is opened.
Update the fields and click on “Add”. Provider setting is updated successfully.

.. image:: images/Editprovider.png 
.. image:: images/editprovider2.png


Click on the 3-dotted icon which is available at the right side of the account details page and choose “Delete” option. A confirmation dialog box is opened. On confirmation the account will be deleted. You can only delete provider settings that are not linked to any project or Organization.


.. image:: images/deleteprovider.png


Research Gateway works in conjunction with AWS Service Catalog. To synchronize the Service Catalog to your project, select the Product Sync option.
Click on the “Sync Now” button. Once the synchronization is complete you should see the “Sync completed” message.

.. image:: images/sync1.png

.. image:: images/sync2.png

.. _`Adding a new project`:

Adding a new project
-------------------- 

Login to the Research Gateway as a Principal Investigator. Click on the  “+Add New” button. Project application form is opened.

.. image:: images/principalaccount.png

.. image:: images/addproject.png


Fill in the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Attribute
     - Details
   * - Project Name
     - <Project Name>
   * - Budget Available
     - <Budget to allocate to this project (cumulative)>
   * - Account ID 
     - <Account ID>
   * - Project Description
     - <Description about the project> 
   * - Add Researchers
     - <Select researchers from the list>


Click on the “Add Project” button. Added a new project successfully.

**Note**:When adding a project we are  passing researcher information. Through this we are linking researchers to the project. The project form allows multi-select addition of researchers while creating a project.

**Note:  The project is independent of the researcher. We can create an empty project and add researchers later**

*My Projects* page of the Research Gateway lists all the existing projects created along with other details. Clicking on a specific project shall leads to a project details page.

.. image:: images/projectdetails.png 
