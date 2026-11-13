# Task 2: Static Website Hosting Using Amazon S3

## 1. Project Overview

This project demonstrates how to host a static website using Amazon Simple Storage Service (Amazon S3).

The website files were uploaded to an S3 bucket, static website hosting was enabled, and a bucket policy was configured to allow public read access.

The website was successfully deployed and accessed through the S3 website endpoint.

## 2. Technologies Used

- Cloud Provider: Amazon Web Services (AWS)
- Storage Service: Amazon S3
- Website: HTML
- Access Management: S3 Bucket Policy
- Hosting: S3 Static Website Hosting

## 3. Implementation Steps

### Step 1: Create an S3 Bucket

Created an S3 bucket with the following name:

`pallavi-week2-static-website`

The bucket was created successfully in the AWS S3 console.

### Step 2: Enable Static Website Hosting

Navigated to the Properties tab of the S3 bucket and enabled Static Website Hosting.

Configured the following documents:

- Index document: `index.html`
- Error document: `error.html`

### Step 3: Create Website Files

Created two HTML files for the website.

**index.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Cloud Computing Project</title>
</head>
<body>
    <h1>Welcome to My Website!</h1>
    <h2>Cloud Computing - Week 2 Project</h2>
    <p>This website is hosted on Amazon S3.</p>
    <p>Created by: Pallavi</p>
</body>
</html>
```

**error.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Error Page</title>
</head>
<body>
    <h1>404 - Page Not Found</h1>
    <p>Sorry, the requested page could not be found.</p>
</body>
</html>
```

### Step 4: Upload Website Files

Uploaded the following files to the S3 bucket:

- `index.html`
- `error.html`

Both files were uploaded successfully.

### Step 5: Configure Bucket Policy

Configured a bucket policy to allow public read access to website objects.

The following JSON policy was added under the Permissions tab:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::pallavi-week2-static-website/*"
    }
  ]
}
```

This policy allows users to read objects stored in the bucket.

### Step 6: Verify Static Website

Copied the S3 static website endpoint from the Properties tab and opened it in a web browser.

The website was successfully displayed with the welcome message.

**Website Endpoint:** http://pallavi-week2-static-website.s3-website.eu-north-1.amazonaws.com/

## 4. Project Outcome

- Created an Amazon S3 bucket.
- Enabled static website hosting.
- Created and uploaded HTML website files.
- Configured a public read bucket policy.
- Successfully accessed the website through the S3 website endpoint.

## 5. Conclusion

Successfully deployed a static website using Amazon S3. This project provided practical experience with cloud storage, static website hosting, bucket permissions, and website deployment on AWS.

