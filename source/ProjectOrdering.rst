.. _`Project ordering`:

Project ordering
================
Login to the Research Gateway as a Principal Investigator/Admin. 

If Principal Investigator/Admin logs as a first time, you can view the welcome screen. Click on the "Let's get Started" button it will navigate to the "Add Account" screen. 

.. image:: images/welcome.png

Click on the  “+Add New” button in the My Project page or use details from :ref:`Appendix A<Appendix A>`  to create account. Once account creation is successful it will navigate to "Create Project" screen. The project application form is opened. 

.. image:: images/projectcreation.png

Fill in the following details

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Attribute
     - Details
   * - Project Name
     - <Project Name>
   * - Project Description
     - <Description about the project> 
   * - Budget Available
     - <Budget to allocate to this project (cumulative)> 
   * - Account Details
     - <Select an Account ID from the list. If accounts are not listed create a new account through "Add Accounts" button.> 
   * - Add Users
     - <Select users from the list or create new collaborators through "Add Users" button.> [optional]
   * - Add Products
     - <Select any one of the catalog type from the list>


Click on the “Create Project” button. Added a new project successfully.

**Note**: While creation of project, if you select "Standard catalog" option it will create 6 products(Amazon S3, Amazon EC2-Linux, Amazon EC2-Windows, RStudio and Nextflow-Advanced). If you select "Bring your own catalog" option it will pull all the products in the portfolio of the AWS account.

Project Storage
---------------

Research Gateway will set up a shared S3 bucket(Project Storage) where the team members can store data. This shared storage will be mounted into all supported workspaces. Storage costs will be accounted for at the project level. For a lot of scientific research, data is stored in file format (e.g. fasta, fastq files for Genomics research). The natural choice for storage of this data could be S3 (inexpensive, highly elastic) or Elastic Block Storage (access is extremely fast). As part of project creation we are creating project storage(i.e., S3 Bucket) and sharing with users. At the same time, we would also like individual users to be able to access personal storage from their computing resources. 

1. The Project level storage will be listed as a product in the My Products tab inside the project as an S3 bucket. There is explore action inside the S3 bucket<<There is a folder called “Shared”.
   Note: It is a common folder(only accessible by user unless shared)  and it  is available to all users.

.. image:: images/projectstorage.png   

.. image:: images/shared.png  

2. You can able to view, upload and delete objects in the storage.
3. While launching any EC2 based product, the user will be prompted whether to mount the Project and User level storage.
4. The Storage will be mounted as a specific folder inside the EC2 machine which the user can use to perform any tasks on. Any data written to the folder will be synced back to the storage and will be accessible to the user on exploring.

Initially project is in creating state. Once project creation completed the status will be changed to "Active". Click on the project in "My Projects" list.

.. image:: images/myprojects.png 

Once you click on the project, you can see the budget in the cards and remaining details will show a tabbed area with the following tabs:

   1. Project Details
   2. Events
   3. Available Products
   4. My Products

Project Details Tab
-------------------

1. You can view the project details here. 
2. If the project was a failed state, you can repair the project through the “Repair” option.
3. Click on the “Pause” action which is available on the right side. When you click on "Pause" action,  all the researchers under this project would be affected. In a Paused state new provisioning is not allowed. Users can continue to use already provisioned resources as before. All the available products would be visible but the “Launch Now “ button would be hidden.
4. Click on the “Resume” button which is available on the right side. The project status changed to “Active”. In the Active state, team members can launch new products from the catalog of Available Products.
5. Click on the “Stop” button which is available on the right side. In a Stopped state, all underlying resources will be stopped and the user will not be able to perform actions on them but you are able to terminate the product. You need to manually start the resources except for the s3 product.
6. Click on the “Sync” button which is available on the right side. It should sync the catalog. You can see related events in the events tab.
7. Click on the “Manage” option under the **Assigned Researchers** field. Once clicked on that, enable the checkbox beside the researcher emails and click on the “Update List” button. It should add collaborators to the project.

.. image:: images/projectdetails.png 

Note: Whenever you clicked on the budget it will navigated to researcher-wise budget details page.

Events Tab
----------

You can see the project-related events here.

.. image:: images/events.png


Available Products
------------------

1. You can view the Available Products information here and you can see products in a table view also.
2. You can search based on product name and description. You can filter the products. We have following filter options:
      
	  a. **All** - You can see the all products here.
	  b. **Research** - You can see the products realted to compute and analytics here. Eg: Amazon EC2
	  c. **IT Applications** - You can see the products related to storage and database here. Eg: Amazon S3
	  
.. image:: images/availableproducts.png	 
	 
My Products
------------

1. You can view the provisioned products details here and You can see products in a table view also.
2. You can search the product name and description of the product.
3. You can filter the products. We have following filter options:
      
	  a. **All** - You can see the all(i.e., active,terminated,stopped and failed) products here.
	  b. **Active** - You can see all the active products here.
	  c. **Terminated** - You can see all terminated products here.
	 
.. image:: images/myproducts.png

**Note**:

a. When adding a project we are passing collaborators information. Through this, we are linking collaborators to the project. 
b. The project is independent of the researcher. We can create an empty project and add researchers later. Once project is active, we can add researchers through the "Manage" option which is at the project details screen.

*My Projects* page of the Research Gateway lists all the existing projects created along with other details. Clicking on a specific project shall leads to a project details page.

.. image:: images/projectdetails.png 