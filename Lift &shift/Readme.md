This project shows how to deploy a multi-tier web application stack[Vprofile] on AWS cloud for production by using lift and shift strategy.
Set Up a domain name on AWS(Route 53) and Generate an SSL certificate(Certificate Manager) and link both together(Creating a CNAME record in the DNSZone/Hostedzone in AWS). This would be useful with the load balancer.
Create a Security group from the EC2 Instance that will be used by loadbalancer( Allow traffic from http & https port 80 from anywhere), Webserver(Tomcat)![Alt text](vprofile-app-sg.png) (Allow traffic only from the security group for load balancer)  and backend services security group( Allow traffic from the mysql/aurora-3306,11211-memcache, 5672 - RabbitMQ)![Alt text](vprofile-backend-sg.png). Added anothetr inbound rule to the webserver security group to allow traffic from internal ports. Enable port 22 and 8080 on application security group for direct access via SSH to the application. Add port 22 for ssh acces to the backend server service group.
Set up the keypair

EC2 instances
ELB
Autoscalling
Route53
S3 /EFS
Amazon certicate Manager

Setup 2MFA via IAM
Setup User 