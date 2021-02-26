Getting Started
===============

Research Gateway is a cloud-based solution that makes it possible for researchers and other consumers of High Performance Computing to easily access resources in the AWS cloud.
RLCatalyst Research Gateway is designed for simplicity and you can get started very quickly. 
You can access this product either as a `hosted SaaS product`_ or as an Enterprise product.

.. _hosted SaaS product: https://relevancelab.com/2021/02/11/8-steps-to-set-up-rlcatalyst-research-gateway/

If you are using the hosted version, you will be provided a public URL to which you can navigate using your browser. 
You will also be provided with the credentials for the Administrator user.

If you are using the Enterprise version, your IT department will provide you a URL to access the product. You can set up an Administrator user by following the steps below.

Planning your set up
--------------------

Setting up your RLCatalyst Research Gateway for use involves the following steps.

Users with the Administrator role can perform the steps below.

  * `Adding Users`_ - Users can have Administrator, Principal Investigator or Researcher roles.
  * `Adding AWS Accounts`_
  * `Adding Organizational Units`_

Users with the Principal Investigator role can perform the steps below.
  
  * Adding Projects
  * Assigning Researchers to projects

Create an Admin user
--------------------

Get started by first creating an Admin user account for your instance of RLCatalyst Research Gateway.

.. _`Adding Users`:

Sign-Up process
----------------

To sign-up as a new user, click on the “Sign-up for  a new  account “ button on the Sign-in page.

.. image:: images/SigninPage.png


Fill the following details:

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Field
     - Details
   * - Organization Name
     -  <Name of the Organization>
   * - Username
     - <Username that is used for login>
   * - E-mail address
     - <Registered Email ID>
   * - Password
     - <Password> - Choose a password that conforms to the password policy.

.. figure:: images/Registeraccountpage.png
   :scale: 100 %
   :alt: Sign-up page

Image  - Sign-up page

Click on the  “Sign Up” button.

You will see a  success  message and verification email has been sent to the email address registered

.. image:: images/thankyou.png

Check the verification email delivered to the registered email address & click on the verification link to activate the account. 

.. image:: images/verificationemail2.png

On successful validation, users  will be allowed to login into the Research Gateway. By default the user will be assigned a *Researcher* role.
To assign an *Administrator* or *Principal Investigator* role, please contact rlc.support@relevancelab.com

Forgot Password
---------------

In case a user would like to reset his password, the reset password screen can be accessed from the sign in page. Choose the *Forgot Password* link.

.. image:: images/forgotpassword.png

On clicking the link the user is navigated to the reset password screen.  

.. figure:: images/resetpassword.png
   :scale: 100 %
   :alt: Reset password

Fill the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Field
     - Details
   * - Organization Name
     -  <Name of the Organization>
   * - Username
     - <Username that is used for login>
   * - E-mail address
     - <Registered Email ID>
    

If the details provided are valid, he will get a verification link that has been sent to his email to reset the password.
On clicking the link in the email, the user is prompted to enter (and confirm) a new password.  The password change is either successful or unsuccessful (this will be like verification success and error screens).  The user is then redirected back to the login screen.

.. figure:: images/verificationlink.png
   :scale: 100 %
   :alt: Verification Link sent in email.

.. figure:: images/reset.png
   :scale: 100 %
   :alt: Password reset message

**Note:** If a user tries to reset password more than 10 times it should throw the above message **“Attempt limit exceeded. Please try again”**


.. _`Adding Organizational Units`:

Adding Organizational Units
--------------------------------

To plan the creation of a new Organization, use the planning sheet in *`Appendix A`__* to collect all the information required upfront.Login into the Research Gateway..
        
Login to the Research Gateway.User landed to the  main dashboard.

.. image:: images/OrganizationPage.png

Image  - Administrator Landing page lists the Organizational Units

Click the “+” icon  which is at the top right corner.Organization form is opened.

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


Image  - View Organization Details Page

.. _`Adding AWS Accounts`:

Adding an AWS account to use in a project
---------------------------------------------

Login into the Research Gateway.
Click on dropdown bar which is above the header
Choose the  “Settings” option


.. image:: images/Providersettings.png 
   :name: Provider Settings menu item

Click on  the  “Add New” button. Provider settings page is opened.

.. image:: images/Provider2.png 
   :name: Provider Settings Page

Image  - Provider Settings Page


.. image:: images/AddProvider.png 
   :name: Add Provider Settings screen

Image  - Add Provider Settings Page

Fill in the following details

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


Click on the “Add” button. AWS account should be added successfully and will show in the table of providers in the Provider Settings page.

On each line item there is a contextual menu. Through this we can edit, update or sync the account.

.. image:: images/Project.png

Image - Context menu for Provider Setting


1. Click on the “Edit” button. Provider settings page is opened.

.. image:: images/Editprovider.png 

Image  - Editing an Account

2. Update the fields and click on “Add”. Provider setting is updated successfully.

.. image:: images/editprovider2.png

Image  - Edit Provider Settings Page


Click on the “Delete” option. A confirmation dialog box is opened. On confirmation the account will be deleted. You can only delete provider settings that are not linked to any project.


.. image:: images/deleteprovider.png

Image  - Deleting an account

Research Gateway works in conjunction with AWS Service Catalog. To synchronize the Service Catalog to your project, select the Product Sync option.
Click on “Sync Now” button. Once the synchronization is complete you should see the “Sync completed” message.

.. image:: images/sync1.png

Image  - Sync Now menu item

.. image:: images/sync2.png

Image  - Successful synchronization

Sign-out process
----------------

Click on the dropdown bar which is at the top
Select “Sign out”option. Through this user logged out from the portal

.. figure:: images/signout3.png 
   :scale: 100 %
   :alt: Signing out

Image - Signing out