PCluster
========

PCluster Product of Research Gateway helps you to set up a high-performance computing Cluster based on AWS Parallel Cluster 3.0. 

PCluster enables you to quickly build an HPC compute environment in AWS. It automatically sets up the required compute resources and shared filesystem. You can use PCluster with batch schedulers, such as AWS Batch and Slurm. PCluster facilitates quick-start, proof-of-concept deployments as well as production deployments.

`Watch a video on how to provision a PCluster product. <https://www.youtube.com/embed/TIQANO-DOtg?start=164&end=208&autoplay=1>`_

Parameters
-----------

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. Eg: MedicalResearch
   * - InstanceType
     - Choose instance type in the drop-down list Eg: t2.small
   * - SSHLocation
     - Enter the IP address range that can be used to SSH to the EC2 instances
   * - KeyPair
     - Choose a KeyPair in the dropdown list. Note: If KeyPair is not available in the drop-down, click on the “+” button. A KeyPair creation form is opened. Fill the details in the form and click on the “Create KeyPair” button. Now that KeyPair is available in the list. Remember to save the private key file securely for future use. Do not share this file with others for the security of your account.
   * - CustomAMI
     - Enter the AMI Id of a custom AMI if you wish to use a non-default AMI. e.g. ami-12345678. The AMI Id entered should exist in this project account and region
   * - HeadNodeInstanceType
     - Select Head Node EC2 instance type from the drop-down list
   * - VpcId
     - Select The VPC to create security groups and deploy awsbatch or slurm from the drop-down list
   * - HeadNodeSubnetId
     - Select the Subnet you want your Head Node to launch in from the drop-down list. You must select a public subnet.
   * - FileSystemType
     - Choose the fileSystem type EFS/FSxForLustre/EBS (provisioned earlier) which you want to mount on the head node leave it as NONE if don't want to mount any filesystem.
   * - FileSystemId
     - Enter the File System Id of the EFS/FSxForLustre/EBS file system which you want to use. e.g. fs-12345678. Leave this field to default if you do not want to use any file system
   * - Scheduler
     - Select a Cluster scheduler from the drop-down list 
   * - ComputeNodeInstanceType 
     - Select the instance types to be used to carry out the computation from the drop-down list
   * - QueueCapacityType
     - Select the type of compute resources used in the queue. Supported values are ONDEMAND or SPOT from the drop-down list.
   * - ComputeNodeSubnetId
     - Select the Subnet you want your Batch or Slurm Worker Node to launch in from the drop-down list. We recommend public subnets.
   * - ComputeEnvMinvCpus
     - Enter the minimum number of CPUs to be kept in running state for the Batch/slurm Worker Nodes. If you give a non-zero value, some worker nodes may stay in a running state always and you may incur higher costs.
   * - ComputeEnvMaxvCpus
     - Enter the maximum number of CPUs for the default Batch or slurm Compute Environment
   * - ComputeEnvDesiredvCpus
     - Enter the Desired number of CPUs for the default Batch Compute Environment
   * - SpotBidPercentage
     - Enter the maximum percentage of On-Demand pricing you want to pay for Spot resources. You will always pay the lowest Spot market price and never more than your maximum percentage.
   * - DisableSimultaneousMultithreading
     - Select the true/false value from the drop-down list. If the selected value is true it will Disable hyperthreading on the compute nodes. Works with Slurm Scheduler.
   * - EnableEFA
     - Select the true/false value from the drop-down list. If the selected value is true it will Enable better network performances. Only available for certain instance types, If the user selects the unsupported instance, EFA is assigned to false. Works with slurm Scheduler
   * - PlacementGroup
     - Select the true/false value from the drop-down list. If the selected value is true it will Enable a PlacementGroup. Use with EnableEFA.Works with slurm Scheduler


.. image:: images/Product_PCluster_LaunchForm1.png

.. image:: images/Product_PCluster_LaunchForm2.png

.. image:: images/Product_PCluster_LaunchForm3.png

.. image:: images/Product_PCluster_LaunchForm4.png

.. image:: images/Product_PCluster_LaunchForm5.png

.. image:: images/Product_PCluster_LaunchForm6.png

Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab
3. Click the “Launch Now” button on the  “PCluster” product card. A product order form will open. Fill the details in the form and click the “Launch Now” button. You will see a PCluster being created. Once the cluster provisioning is completed, that product should appear in the “Active” state.

Estimated time to provision - 40 minutes

Steps to connect
----------------

1. Click on “SSH Terminal” under the “Connect” list on the right side of the page. This will open the SSH Terminal in a new browser tab.

.. note:: if you have selected "SpackSetup" as true during launch then you will be able to install spack packages. Click on “SSH Terminal” under the “Connect” list on the right side of the page and run the below commands in SSH Window
  
  a. **ls**  - run this command in the home directory folder and check if you find "spack" in the folder.
  

  b. **spack find**  - this command will show how many packages are installed. Once all the packages are done installing ( usually it will take 2 hours) it will show the message **Spack setup completed**.

  .. image:: images/Pcluster_SSH_SpackComplete.png


  c. **tail -f /var/log/spack-postinstall.log** - run this command in home directory folder. This will show the Sequence of all events and packages installed.

.. note:: 
  
 1. if you have selected "Scheduler" as **slurm** during launch if you want to submit a job and get the output you can follow the below steps and run the below commands in SSH Window

  a. Create a job script file:

    **vi <filename>.sh**

     Enter the contents in the file: 
    
     example:

     **#!/bin/bash**
     
     **sleep 30**
     
     **echo "Hello World from $(hostname)"**

     Save and exit the file.

  b. Submit the job:

     **sbatch <filename>.sh**

     This command submits the job script to the Slurm scheduler for execution. It returns a job ID, indicating that the job has been submitted successfully.

  c. Check the job status:

     **squeue**

     This command shows the status of all jobs in the Slurm queue. Look for your job in the output. The job ID, partition, name, user, state, time, nodes, and nodelist will be displayed.

  d. Wait for the job to finish:
     Allow the job to run for the specified duration in the script (30 seconds in this case).

  e. Check the job status again:

     **squeue**

     Now that the job has been completed, you will no longer see it in the queue.

  f. Check the output:

     **ls -l**

     This command lists the files in the current directory. Look for the `slurm-JOBID.out` file, where `JOBID` is the ID of your submitted job.

  g. View the output:

    **cat slurm-JOBID.out**

    .. image:: images/Pcluster_Slurm_RunJOB_output.png

    Replace `JOBID` with the actual job ID. This command displays the output of your job, which should include the "Hello World" message along with the hostname.

 2. if you have selected "Scheduler" as **awsbatch** during launch if you want to submit a job and get the output you can follow the below steps and run the below commands in SSH Window

  a. Create a job script file:

    **vi <filename>.sh**

     Enter the contents in the file: 
    
     example:

     **#!/bin/bash**
     
     **sleep 30**
     
     **echo "Hello World from $(hostname)"**

     Save and exit the file.

  b. Submit the job:

     **awsbsub <filename>.sh -cf -jn samplejob**

     This command submits the job named samplejob using the script file **<filename>.sh** to AWS Batch for execution. The -cf and -jn options may be custom options specific to your environment or an external tool.
 
  c. Check the job status:

     **awsbstat**

     This command retrieves the status of all jobs in the AWS Batch job queue. It will display information about the submitted job, such as its ID, name, status, and other details.

  d. Wait for the job to finish:
     Allow the job to run for the specified duration in the script (30 seconds in this case).

  e. Check the job status again:

     **awsbstat**

     Now that the job has been completed, you will no longer see it in the queue.

  f. View the job output using **awsbout**

     **awsbout <JOB_ID>**

     Replace <JOB_ID> with the actual ID of the job you submitted. This command fetches the output of the specified job, allowing you to view the job's output or logs.
    
    .. image:: images/Pcluster_awsbatch_RunJOB_output.png

.. note:: 
   a. The commands awsbsub, awsbstat, and awsbout may not be standard AWS Batch CLI commands. They might be custom commands or wrappers specific to your environment or an external tool you are using. Ensure that you have the necessary CLI or tools configured and installed correctly to use these commands in your AWS Batch environment.
   b. Please refer to the official documentation or specific documentation of the tool you are using for further details and the correct usage of these commands in your AWS Batch and AWS ParallelCluster environment.


2. Enter “ec2-user” as the username. Select “Pem file” as the Authentication type. Upload the pem file in the “Pem file” field. Click Submit. You should now be connected to the EC2 instance via SSH. Scroll to the top of the Terminal screen and click the “Terminate” button to end the session. Alternatively, type exit and hit enter in the terminal.
3. You can de-provision the product through the “Terminate” option.
4. Click on "Remote Desktop" under the "Connect" list on the right side of the page. The cluster head-node by default has NICE DCV installed which allows you to connect to the head-node via a GUI interface. This is especially useful to visualize the results of the jobs that you run on the cluster (e.g. using Paraview to view the results of OpenFOAM jobs).

`Watch a video that demonstrates using OpenFOAM on a PCluster product. <https://www.youtube.com/embed/TIQANO-DOtg?start=209&end=370&autoplay=1>`_

Other considerations
---------------------

You can stop your instance using the “Stop” button on the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. 

.. note:: This action will only stop the head node. If the ComputeMinvCPUs (in case of AWSBatch scheduler) or MinimumInstances (in case of Slurm scheduler) is set to a non-zero value, the compute nodes will continue to run in the background and accrue costs.

.. image:: images/Product_Pcluster_StopAction_Dialogbox.png

Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.

You can share the product with all the members of the project using the “Share” button on the product details page of your product. If you share the product with the project, you will have to share the PEM key file outside of Research Gateway.
