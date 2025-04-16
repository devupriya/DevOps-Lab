# Day 1 – EC2 + Linux Setup

## What I did:
- Created an EC2 instance (Amazon Linux 2)
- SSH'd into it using .pem key
- Installed and started NGINX
- Verified web server is working via public IP

## Screenshots / Commands:
- `ssh -i my-key.pem ec2-user@x.x.x.x`
- `sudo yum install nginx -y`
- ![image](https://github.com/user-attachments/assets/f198d2a4-ee8d-49c6-b63b-c6b81ec88496)


## Reflections:
- First time connecting to a remote Linux server.
- Got more comfortable with the terminal.
- Ready to build on this tomorrow.

# Day 2 – Git + Bash Script

## What I did:
- Practiced Git branching, merging, and pushing
- Created and executed a Bash script to install NGINX on EC2
- Pushed the script to GitHub with a README

## Script:
```bash
<add your script code here>
#!/bin/bash

echo "Updating packages..."
sudo yum update -y

echo "Installing NGINX..."
sudo amazon-linux-extras install nginx1 -y

echo "Starting NGINX..."
sudo systemctl start nginx
sudo systemctl enable nginx

echo "NGINX is running. Access via EC2 public IP."
```

Make it esecutable
```
chmod +x install_nginx.sh
```

Run it on your EC2
```
./install_nginx.sh
```
# Day 3 – S3 Static Website

## What I did:
- Created a static HTML page
  ```
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My S3 Hosted Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #0073e6;
            color: white;
            padding: 1rem 0;
        }
        main {
            padding: 2rem;
        }
        footer {
            background-color: #333;
            color: white;
            padding: 1rem 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to My S3 Hosted Website</h1>
    </header>
    <main>
        <p>This is a simple static website hosted on an Amazon S3 bucket.</p>
        <p>Feel free to customize this page as needed!</p>
    </main>
    <footer>
        <p>&copy; 2023 My Website</p>
    </footer>
</body>
</html>
  ```
- Hosted it using AWS S3
- Configured bucket permissions and policies
  ```
  {
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```
```
- Made the site publicly accessible



