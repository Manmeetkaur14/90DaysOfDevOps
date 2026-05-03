Commands Used


Launch Ec2 > Connect
yum check-update
yum update
yum install nginx -y
systemctl enable --now nginx

give security to allow traffic in AWS 

Check in Websever its working or not

http://13.233.69.11:80 (its working)
tail -f /var/log/nginx/access.log > /root/nginx_logd.txt
tail -f /var/log/nginx/error.log > /root/nginx_logd.txt

sudo cp /root/nginx_logd.txt /home/ec2-user/
cd /home/ec2-user
sudo chown ec2-user:ec2-user /home/ec2-user/nginx_logd.txt

chmod 777 nginx_logd.txt

go to windows Terminal 

Write this commands 

scp -i "AWSkey.pem" ec2-user@ec2-13-233-69-11.ap-south-1.compute.amazonaws.com:/home/ec2-user/nginx_logd.txt .




Challenges Faced

installed httpd and nginx 
both started using port 80 
and nginx page was not showing content
followed this command

sudo systemctl stop httpd
sudo systemctl disable httpd
sudo systemctl start nginx

echo "----------------------------------------------------------"

What I have learned today is :


“Nginx and Apache are separate web servers. Only one is required; running both on same port causes conflict.”


No ❌ — you do NOT need to install Apache (httpd) for Nginx to work.

✅ Correct understanding
Nginx → standalone web server
Apache (httpd) → another standalone web server

👉 Both do the same job (serve websites)

🚫 Important
You don’t install both normally
Both try to use port 80
Running both together → ❌ conflict (like your error earlier)
✅ What you should do

If using Nginx:

sudo systemctl stop httpd
sudo systemctl disable httpd
sudo systemctl start nginx

