# Infrastructure Description


### AWS RDS

1. PostgreSQL Engine
1. Security group with rule to allow access from any IP
1. Publicly accessible

### Amazon S3

1. URL: http://udacitytask4bucket.s3-website-us-east-1.amazonaws.com
1. Uses Static Website Hosting
1. ACLs are enabled and can be used to grant access to this bucket and its objects
1. Permissions: 
```
{
"Version":"2012-10-17",
"Statement":[
  {
      "Sid":"Stmt1625306057759",
      "Principal":"*",
      "Action":"s3:*",
      "Effect":"Allow",
      "Resource":"arn:aws:s3:::udacitytask4bucket/*"
  }
]
}
```
1. CORS: 
```
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "POST",
            "GET",
            "PUT",
            "DELETE",
            "HEAD"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": []
    }
]
```
1. Redirect:
```
[
    {
        "Condition": {
            "HttpErrorCodeReturnedEquals": "404"
        },
        "Redirect": {
            "HostName": "udacitytask4bucket.s3-website-us-east-1.amazonaws.com",
            "ReplaceKeyWith": "index.html"
        }
    }
]
```

### Elastic Beanstalk

1. URL: http://udagram-api-deploy.us-east-1.elasticbeanstalk.com/


## License

[License](LICENSE.txt)
