# js-bucket-listing

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
