## What I built 

I launched an Ubuntu EC2 instance on AWS, installed NGINX, and made its default page available at http://nginx.alibadribrahim.co.uk. My main domain continues to host my portfolio on Cloudflare Pages


## How the connection works 

Cloudflare DNS has an A record mapping nginx.alibadribrahim.co.uk to the EC2 public IPv4 address. A browser that address to contact the server on HTTP port 80. The EC2 security group permits the request, and NGINX returns the welcome page. 

I used SSH on port 22 to administrator the EC2 instance from my local machine.

## Commands I used on EC2 

```text
sudo apt update 
sudo apt install -y nginx 
sudo systemctl status nginx --no-pager

## Challenges 

My SSH private key initially had permissions that were too open on Windows, so SSH refused to use it. I copied the key into my Ubuntu VM, made my user its owner, and restricted it with 'chmod 400'. I then connected to EC2 successfully. I also kept the private key outside this Git repository.
