# js-bucket-listing

_Block Public Access:_

- go to bucket "permissions"
- find "block public access"
- edit the block to unblock all traffic. there should be 4 options you need to disable.

_Static Website Hosting:_

- go to bucket "properties"
- find the "static website hosting" section
- "enable" static website hosting
- set "index.html" as the index document

_Bucket Policy:_

```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::<bucket name>",
                "arn:aws:s3:::<bucket name>/*"
            ]
        }
    ]
}
```

_CORS Policy:_

```
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET"
        ],
        "AllowedOrigins": [
            "http://<bucket name>>.s3-website-us-east-1.amazonaws.com",
            "https://<bucket name>.s3-website-us-east-1.amazonaws.com"
        ],
        "ExposeHeaders": []
    }
]
```
