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
   * - PipelineName
     - Search and select the pipeline git repository URL. If not found please enter the custom pipeline URL. The repo should contain the nextflow.config file which specifies the name of the docker container image. Eg: https://github.com/seqeralabs/nextflow-tutorial.git
   * - PipelineContainer
     - Public Docker container image of the pipeline to be executed. If you are using a custom pipeline, ensure that the custom container image is publicly available on Docker Hub Eg: nextflow/rnaseq-nf:latest
   * - InputDataLocation
     - An S3 bucket which holds input data for the Nextflow pipeline. The bucket name must respect the S3 bucket naming conventions (can contain lowercase letters, numbers, periods and hyphens).
   * - OutputDataLocation
     - The full path on the local disk where outputs of the pipeline should be stored. The default path above will enable you to view the outputs via the browser. The path should be accessible to the user ec2-user. Alternately, provide an S3 bucket for storing analysis results. The bucket name must respect the S3 bucket naming conventions (can contain lowercase letters, numbers, periods and hyphens). Eg: s3://<BucketName>
   * - InstanceType
     - Head Node EC2 instance type. Eg: t2.micro
   * - HeadNodeEBSVolumeSize
     - The initial size of the volume (in GBs) Head Node EBS will use for storage. Eg: 16 
   * - KeyPair
     - Name of an existing EC2 KeyPair to enable SSH access to the Head Node. Please create a key pair from the key pair screen if they are not available in the dropdown. Remember to save the private key file securely for future use. Do not share this file with others for the security of your account
   * - AllowedSSHLocation
     - The IP address range that can be used to SSH to the Head Node. For the security of your instance, we recommend you allow connections only from your own location. You can find your IP using https://whatismyipaddress.com/ Eg: 0.0.0.0/0
   * - VPCId
     - Choose VPC Id in the drop-down list.
   * - WorkerNodeSubnetId
     - Choose Subnet Id in the drop-down list. Subnet you want your Batch Worker Node to launch in. We recommend public subnets.
   * - ComputeEnvMinvCpus
     - The minimum number of CPUs to be kept in running state for the Batch Worker Nodes. If you give a non-zero value, some worker nodes may stay in running state always and you may incur higher cost. Eg: 0
   * - ComputeEnvMaxvCpus
     - The maximum number of CPUs for the default Batch Compute Environment. Eg: 100
   * - SpotBidPercentage
     - The maximum percentage of On-Demand pricing you want to pay for Spot resources. You will always pay the lowest Spot market price and never more than your maximum percentage. Eg: 100
   * - WorkerNodeInstanceType
     - Specify the instance types to be used to carry out the computation. You can specify one or more family or instance type. The option 'optimal' chooses the best fit of M4, C4, and R4 instance types available in the region. Eg: Optimal 
   * - WorkerNodeEBSVolumeSize
     - The initial size of the volume (in GBs) Worker Node EBS will use for storage.  Eg: 100

   
Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab.
3. Click the “Launch Now” button on the  “Nextflow-Advanced” product card. A product order form will open. Fill the details in the form and click the “Launch Now” button. You will see a  “Nextflow-Advanced” being created. In a few minutes, that product should appear in the “Active” state.

Estimated time to provision -  10 minutes

Steps to connect
----------------

1. Click on the “SSH to Server” button under the “Connect” list on the right side of the page. This will open the SSH Window in a new browser tab. 
2. Enter “ec2-user” as the username. Select “Pem file” as the Authentication type. Upload the pem file in the “Pem file” field. Click Submit. You should now be connected to the EC2 instance via SSH. Run the computation command in.
3. Scroll to the top of the Terminal screen and click the “Terminate” button to end the session. Alternatively, type exit and hit enter in the terminal.
4. You can monitor the pipeline through "Monitor Pipeline" option.
5. You can view the outputs through "View Outputs" option.
6. You can de-provision the product through the “Terminate” option.

.. image:: images/advanced.png

Other considerations   
---------------------

You can stop your instance using the “Stop” button in the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.

