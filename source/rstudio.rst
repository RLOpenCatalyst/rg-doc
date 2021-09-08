RStudio
=======

RStudio is an integrated development environment (IDE) for R. It includes a console, syntax-highlighting editor that supports direct code execution, as well as tools for plotting, history, debugging, and workspace management.

Parameters 
----------

 .. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. Eg: MedicalResearch
   * - InitialUser
     - User name for RStudio
   * - InitialPassword
     - Password for RStudio. Please keep in your records as this will not be echoed in the CloudFormation Console
   * - KeyPair
     - Choose the KeyPair in the list. Note: If KeyPair is not available in the drop-down, click on the “+” button. A KeyPair creation form is opened. Fill the details in the form and click on the “Create KeyPair” button. Now that Keypair is available in the list.
       Remember to save the private key file securely for future use. Do not share this file with others for the security of your account.
   * - InstanceType
     - Choose instance type in the drop-down list for RStudio. Eg: t2.micro


 .. image:: images/rstudio.png
 
Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab.
3. Click the “Launch Now” button on the  “RStudio” product card. A product order form will open. Fill the details in the form and click the “Launch Now” button. You will see an “RStudio” being created. In a few minutes, that product should appear in the “Active” state.

Estimated time to provision -  15 minutes

Steps to connect
----------------

1. Click on “Open Link” under the “Connect” list on the right side of the page. This will open the Rstudio in a new browser tab. 
2. Click on the “SSH” button under the “Connect” list on the right side of the page. This will open the SSH Window in a new browser tab. 
3. Enter “ec2-user” as the username. Select “Pem file” as the Authentication type. Upload the pem file in the “Pem file” field. Click Submit. You should now be connected to the EC2 instance via SSH. Scroll to the top of the Terminal screen and click the “Terminate” button to end the session. Alternatively, type exit and hit enter in the terminal.

 .. image:: images/rstudio-actions.png
 
Other considerations
--------------------

You can stop your instance using the “Stop” button in the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.
