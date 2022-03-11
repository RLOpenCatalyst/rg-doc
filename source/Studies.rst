.. _`Studies`:

Studies
========

You can connect to Open Data like the AWS registry of open data. The “Study” details page will show a tabbed area with the following tabs:

	a. Study details : The “Study details” tab will show all the details of the study available in the collection. Actions associated with the study will be shown in an actions bar on the right side of the page.
	b. Resource details: The “Resource details” tab will show the details of the associated product (S3 bucket). This will replicate the product details page of the associated S3 bucket and show the same actions associated with the s3 bucket.
											
 .. image:: images/sc3.png
 
 .. image:: images/public.png
  
**Explore Action**

You can see the files/folders which are  related to the datastore.

.. image:: images/ex1.png

**Link/Unlink Action**

1. A user will be able to link a study to a compute resource using the “Link” action in the Actions bar. This action item should be a pop-up that will have the list (dropdown) of active sagemakers for that user.
2. You can see an icon similar to the shared icon for showing that this S3 bucket is linked with sagemaker.
3. You can link the study with multiple sagemaker notebooks.  Through the “unlink resource” you can unlink with compute resources
4. If there are no active sagemaker products we are showing the following message to the user **There is no provisioned Sagemaker product. Please Launch a sagemaker product from the available products page first, before linking to an s3 bucket**.
 
 .. image:: images/link2.png
 
 .. image:: images/unlink.png
 
 .. image:: images/unlink2.png
  
 .. image:: images/link1.png  