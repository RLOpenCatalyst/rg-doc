Nextflow-Advanced
=================

Use the scalability of AWS Batch to run Nextflow workflows. This is ideal for large workloads and larger data-sets.

Parameters
-----------

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. Eg: MedicalResearch
   * - Namespace
     - Namespace to use to label resources.
   * - PipelineName
     - URL to the git repository containing the pipeline code. The repo should contain nextflow.config file which specifies the name of the docker container image. Eg: https://github.com/seqeralabs/nextflow-tutorial.git
   * - PipelineContainer
     - Docker container image to the pipeline to be executed in the worker node. Eg: nextflow/rnaseq-nf:latest
   * - InputDataLocation
     - Name of existing S3 Bucket in that region.
   * - OutputDataLocation
     - Name of existing S3 Bucket in that region.
   * - WorkDataLocation
     - Name of existing S3 Bucket in that region.
   * - InstanceType
     - Choose instance type in the drop-down list for RStudio. Eg: t2.micro
   * - HeadNodeEBSVolumeSize
     - Amount of storage the Head Node will use. Eg: 16 
   * - KeyPair
     - Choose the KeyPair in the list. Note: If keyPair is not available in the drop-down, click on the “+” button. A keypair creation form is opened. Fill the details in the form and click on the “Create KeyPair” button. Now that keypair is available in the list. Remember to save the private key file securely for future use. Do not share this file with others for the security of your account
   * - AllowedSSHLocation
     - This identifies the IP locations from where connections to this instance should be allowed. For the security of your instance, we recommend you allow connections only from your own location. You can find your IP using https://whatismyipaddress.com/ Eg: 0.0.0.0/0
   * - VPCId
     - Choose VPC Id in the drop-down list.
   * - ComputeEnvMinvCpus
     - The minimum number of CPUs to be kept in running state for the Batch Worker Nodes. Eg: 0
   * - ComputeEnvMaxvCpus
     - The maximum number of CPUs for the default Batch Compute Environment. Eg: 100
   * - SpotBidPercentage
     - The maximum percentage of On-Demand pricing you want to pay for Spot resource. Eg: 100
   * - WorkerNodeInstanceType
     - Specify the instance types to be used to carry out the computation Eg: Optimal 
   * - WorkerNodeEBSVolumeSize
     - The initial size of the volume.  Eg: 100

   
Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab.
3. Click the “Launch Now” button on the  “Nextflow-Advanced” product card. A product order form will open. Fill the details in the form and click the “Launch Now” button. You will see a  “Nextflow-Advanced” being created. In a few minutes, that product should appear in the “Active” state.

Estimated time to provision -  10 minutes

Steps to connect
----------------

1. Click on the “SSH” button under the “Connect” list on the right side of the page. This will open the SSH Window in a new browser tab. 
2. Enter “ec2-user” as the username. Select “Pem file” as the Authentication type. Upload the pem file in the “Pem file” field. Click Submit. You should now be connected to the EC2 instance via SSH. Run the computation command in
3. Scroll to the top of the Terminal screen and click the “Terminate” button to end the session. Alternatively, type exit and hit enter in the terminal.
4. You can de-provision the product through the “Terminate” option.


Other considerations   
---------------------

You can stop your instance using the “Stop” button in the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.

