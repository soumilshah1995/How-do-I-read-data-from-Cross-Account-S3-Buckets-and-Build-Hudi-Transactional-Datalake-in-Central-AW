
How do I read data from Cross Account S3 Buckets and Build Hudi Transactional Datalake in Central AWS Account

![sada drawio (1)](https://user-images.githubusercontent.com/39345855/224491471-d6765cfe-06f8-48e4-9cb8-c59d2a89364d.png)

### Steps 
* Since data Team want to access data from order and payment team S3 Buckets. Admin of Order and payment team need to add following policy 
```

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::<ACCOUNT OF DATATEAM>:root"
            },
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::<BUCKET NAME THAT DATATEAM IS TRYING TO ACCESS >",
                "arn:aws:s3:::<BUCKET NAME THAT DATATEAM IS TRYING TO ACCESS>/*"
            ]
        }
    ]
}
```
