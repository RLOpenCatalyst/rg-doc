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
3. Connect URL button showing for stopped workspaces of type NICE DCV
4. Change Icon for FSx product
5. Subnet ID mismatch when multiple subnets are required in the CFT input
6. In Users Screen: Download CSV format action is not working
7. Studies : Public Study : Explore : Folder: Page Refresh is showing Create new button
8. Studies Page : explore action : Folder : showing no data available : once click on refresh action which is available in the UI it will show content
9. For workspaces that connect to DCV, the button should read "Remote Desktop" rather than "Connect DCV"
10. PI Login : Archive project : Delete project storage S3 bucket
11. Subnet ID mismatch when multiple subnets are required in the CFT input
12. UI changes required in Public studies.
13. s3 : explore: upload: create an audit trail event for failure.
14. PCluster:Latest AMI causing stack to fail if there is a fileSystemId as input parameter when scheduler is aws batch, need to fix

