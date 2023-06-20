Secure Research Linux Desktop 
==============================

The Secure Research Linux Desktop is a product offered by Research Gateway, that provides authenticated and authorized users access to workspaces that handle sensitive datasets for processing and analysis while minimizing the risk of exposing sensitive data.   

The Secure Research Linux Desktop only works in a project enabled for secure research. Follow these steps to enable secure research projects. 

1. Create a Setting in RG using your AWS account. 

2. Create a stack and Secure VPC using the cft provided (rg-tre-account-onboarding.yaml which is available in bucket “ rg-prodenvironment-instancefiles-london" of eu-west-2 region of 977461429431 account) in the project account in the same region where the setting is created. 

.. note:: secure VPC will be created as part of stack creation. 

3. Create an ALB in the VPC created above using the following steps: 

  a. Log in to your AWS console for the account you are using as a project account.  

  b. Navigate to the EC2 services page and choose Load Balancers in the left pane. 

  c. Choose the "Create new load balancer" button. 

  d. In the form that opens add the name of the load balancer in the “Load balancer name” field 

  e. select the IP address type of the VPC created 

  f. enter the VPC Id (output of step 2) in the VPCId field.  

  g. Mappings: Select the Availability Zones which will be shown in the section based on VPC selected. 

  h. Search for the “EntryPointSecurityGroup” which will be available in the Outputs tab of Stack created in Step number 2 in the Security groups field and select the value 

  i. Select HTTPS port 443 as Listener and select forward to the target group which you have created using the VPC id in the same region where VPC is created. 

  j. Secure listener settings: select the recommended “Security Policy” and select “Default SSL/TLS certificate”: “Select the certificate for your domain” example: *.rlcatalyst.com

   .. note:: If you are not able to see any certificate please contact the support

  k. Once you complete filling all the necessary parameters in the form click on the “Create Load Balancer” button which is available at the end of the form.  

  l. This will successfully create the ALB using the VPC id provided  

4. Provide the below details of the CFT outputs to the RG support team to enable secure research. 

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - ALB Details 
     - Network Details
   * - loadBalancerArn
     - vpc
   * - dnsName 
     - publicSubnet1
   * - listenerArn
     - publicSubnet2
   * - securityGroupId
     - privateSubnet
   * - certificateArn
     - entryPointSG
   * -
     - workspaceSG
   * -
     - interfaceEndpointSG


5. Create a project from the UI. Ensure no products are created in the catalog. Also, uncheck the option to create a project storage as this is not supported in secure research projects. 

6. Provide the details of the project to RG support team to enable secure research in the project. 

7. Assign the Secure Research Linux Desktop product to the secure research project. 

A project enabled for secure research only uses Secure Research Linux Desktop product in the catalog. To provision this workspace, launch the product using the following parameters. 

Parameters
-----------

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name 
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. 
   * - Study Selection 
     - Expand the section to select studies to mount to your workspace. Select one or more studies to mount to your workspace from the dropdown list (Maximum of 2) 
   * - EBSVolumeSize 
     - The initial size of the volume (in GBs) EBS will use for storage. 
   * - InstanceType 
     - Choose the instance type for this instance. e.g., t3. medium 

.. image:: images/SecureResearchLinuxDesktop_Launchform1.png

.. image:: images/SecureResearchLinuxDesktop_Launchform2.png


Steps to launch
----------------

1. Click on the project on the “My Projects” page. 

2. Navigate to the available products tab. 

3. Click the “Launch Now” button on the “Secure Research Linux Desktop” Product card. 

4. A product order form will open. Fill the details in the form and click the “Launch Now” button. 

5. You will see a Secure Research Linux Desktop being created. In a few minutes, that product should appear in the “Active” state. 

Expected time to provision: 10 Minutes 


Steps to connect
------------------

1. Click on “Remote Desktop” under the “Connect” list on the right side of the page. You will be able to see a colored theme. 

2. You can de-provision the product through the “Terminate” option. 

 
Other considerations
----------------------

You can stop your instance using the “Stop” button on the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”. 

You can share the product with all the members of the project using the “Share” button on the product details page of your product. If you share the product with the project, you will have to share the PEM key file outside of Research Gateway. 
