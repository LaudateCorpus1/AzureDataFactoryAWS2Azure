### Azure Data Factory Pipeline - copy files from AWS S3 to Azure Blob

#### Permission Policy on AWS S3 bucket 
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:PutObject",
                "s3:GetObjectAcl",
                "s3:PutObjectAcl",
                "s3:ListBucket",
                "s3:GetBucketAcl",
                "s3:PutBucketAcl"
            ],
            "Resource": "arn:aws:s3:::<bucket name>/*",
            "Condition": {}
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListAllMyBuckets",
                "s3:GetBucketLocation"
            ],
            "Resource": "arn:aws:s3:::*",
            "Condition": {}
        }
    ]
}

```

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnavalev%2FAzureDataFactoryAWS2Azure%2Fmaster%2FAzureDeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
