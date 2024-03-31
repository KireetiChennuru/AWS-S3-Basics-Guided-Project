# AWS-S3-Basics-Guided-Project

Six learning objectives: 
1. Create your First S3 Bucket
2. Upload Content to Bucket and Manage their Access
3. Understand S3 Encryption and enable it for S3 Bucket
4. Enable Versioning on S3 Bucket
5. Understand S3 Storage classes and Create Lifecycle Rule for objects in AWS S3
6. Create Static Website using AWS S3


Bucket Policies (JSON)

Static website - Image display while accessing static website URL (index.html and Error.html)
<br>
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::mywebsite1945/*"
        }
    ]
}




Encryption - This policy allows only encrypted files to get uploaded in S3 bucket 
<br>
{
    "Version": "2012-10-17",
    "Id": "Policy1710267696891",
    "Statement": [
        {
            "Sid": "Stmt1710267690357",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:PutObject",
            "Resource": "arn:aws:s3:::demoencrypt1996/*",
            "Condition": {
                "StringNotEquals": {
                    "s3:x-amz-server-side-encryption": "aws:kms"
                }
            }
        }
    ]
}
