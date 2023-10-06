To learn AWS cloud in detail I had several online courses. One of these courses was the following one:
https://www.udemy.com/share/101Jp83@_dmQvnRXF9dlkK09-1R1CcDahpn3pvDZDXsATaQ_BAbjcyVVmXE3Be0u1OMHr-sA-Q==/

Capstone project was really complex and it was giving the full picture of how to use different services effectively. The course is just in Turkish and there wasn't any GIT repository (other languages are not available, so that I have decided to put everthing I did in English and make it public). The lambda functions were in the source section, I got them and pushed into my repository.


Building a PHP based web application with high availability and fault tolerance by using AWS services:

Virtual Private Cloud (VPC), AWS S3, AWS IAM, Amazon EC2, Amazon Elastic File System (Amazon EFS),
Amazon RDS, Amazon Elastic Load Balancer (Application Load Balancer), Amazon EC2
Autoscaling, Amazon CloudFront and Amazon Route 53.

This application allows users to upload contact information (name, address, phone) and 1
picture. The uploaded image is uploaded to the file system (EFS) which is used by EC2 servers.
Contact information is also stored in the RDS database. 

In the next step, the uploaded image is
copied to an S3 bucket. Any image uploaded to the bucket, triggers a lambda function. The
lambda function shrinks this image to 100x100 and uploads it to the 2nd bucket.

The application runs on EC2 instances which are launched in the autoscaling group.
Autoscaling group launches at least 3 instances (1 in each public subnet), (if CPU usage
exceeds 90%, it continues with a total of 5 instances). 

Traffic distribution is ensured by placing
all instances behind a load balancer. CloudFront distribution is created for global access of this
load balancer. As a final step, Route 53 is used to access this web-based application via an URL
such as www.project.com.
