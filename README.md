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
