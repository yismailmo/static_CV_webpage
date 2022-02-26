Hosting a static webpage with Amazon AWS S3 & AWS Cloudfront
Step 1:
Create a S3 bucket and Under “Block Public Access settings” uncheck “Block all public access”.

Step 2:
Upload the HTML/css file to S3 bucket
Step 3:
Click “Close” and reopen the s3 bucket to navigate to the “Properties” tab

Step 4:
Scroll down until you locate the “Static website hosting” section. Select Edit, then click Enable. This will bring you into the menu where you will be able to type your index document, which is what will be shown as the home page. I updated this file with the web_content file that I uploaded. Click Save Changes.

Step 5:
Scroll down to “Bucket Policy” section. This step is vital in allowing access to the content in this bucket even though access was unblocked in a previous step. Click edit then update the bucket policy with below JSON code and ensuring the “Resource” element references my bucket ( ismailcvstaticsite ). Click Save Changes.

step 6:
Navigate back to the Static website hosting section ( Amazon S3 > ismailcvstaticsite ) within the “Properties” tab and click the link to view the S3 bucket contents for your HTML file to appear. Please aware that the specific name of the AWS S3 bucket is shown in the url. This is not an acceptable practice as we do not want the public to directly access this bucket.

step 7:
use AWS CloudFront to fix this. So I am creating an Amazon CloudFront distribution and configuring it to serve the S3 bucket.

Step 8:
AWS Cloudfront distribution has been completed and is ready to be deployed to user endpoints.

step 9:
In order to properly remove public access for the AWS S3 Bucket, navigate back to the S3 Bucket ( ismailcvstaticsite) console and check block all public access.
( Amazon S3 > ismailcvstaticsite > [Permissions tab] > Block public access ) Click Save Changes, then type “confirm” when prompted.

step 10:
the access is now “Only authorized users of this account”. permission_authorized

Validate access to the content (html file) by using the new CloudFront Domain Name found in the console. Copy the Domain Name into a web browser to test.

step 11:
Testing the domain name…
