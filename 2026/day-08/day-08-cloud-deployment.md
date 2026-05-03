Launch Ec2 > Connect
yum check-update
yum update
yum install nginx -y
systemctl enable --now nginx

Check in Websever its working or not

http://13.233.69.11:80 (its working)
tail -f /var/log/nginx/access.log > /root/nginx_logd.txt
tail -f /var/log/nginx/error.log > /root/nginx_logd.txt

sudo cp /root/nginx_logd.txt /home/ec2-user/
cd /home/ec2-user
sudo chown ec2-user:ec2-user /home/ec2-user/nginx_logd.txt

chmod 777 nginx_logd.txt



