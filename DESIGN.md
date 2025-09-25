# CS 454 Project 1

## Overview
This service uses a REST API through Node.js/Express to convert a pound value to a kilogram value.

## How it works 
In the code in the server.js file, a GET request in used to retreive the pound value from the "/convert" path of \
the url. 

## Error checking
The code in server.js checks to verify that the value specified in the url is a non-negative and number value. If \
the value is negative, a 422 error code with a message is returned. If the value is not a number, like a letter, or a \
value was not specified, a 400 error code with a message is returned.

## EC2 Design information- Includes security group rule summary
A t3.micro Amazon Linux EC2 instance was created to deploy this service. The security groups for this service were \
configured to allow SSH (20) from my IP and allow TCP inbound traffic on port 8080. This service was ran using   
either the "node <filname>" command or systemctl command. To run the service using the systemctl command a .service  
file was created in the /etc/system/systemd/ directory. To be able to run the service as a non-privileged user by \
using the sudo systemctl start <service_name> command, the default EC2 username was used for the User specification \
in the [Service] section in the .service file. 
