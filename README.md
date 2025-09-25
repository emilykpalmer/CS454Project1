# CS 454 Project 1
This is a service that uses a REST API through Node.js/Express to convert pounds to kilograms.

## Run the service locally in bash  
  1. npm install (only have to run once
  2. node server.js

## Test the service locall in bash:
  1. Run the service locally in bash
  2. curl 'http://localhost:8080/convert?lbs=<pounds_value>'

## Deploy the service using an EC2 instance 
  1. Launch an AWS t3.mirco Amazon Linux EC2 instance \
       a. Allow SSH (20) from your IP \
       b. Modify security group to allow inbound TCP/8080 \
  2. Connect to the EC2 instance 
  3. Install Node.js and npm
  4. Clone this repo into the EC2 instance 
  5. Run 'npm install'

## Run and test the service using EC2 instance and curl command
  1. In the repo directory, run 'node server.js'
  2. Open a second EC2 instance terminal, and run the command:
     curl 'http://<EC2_Public_IP:8080/convert?lbs=<pounds_value>' 

## Run and test the service using EC2 instance and web browser
  1. In the repo directory, run 'node server.js'
  2. Open a web browser tab and type the url:
     http://<EC2_Public_IP:8080/convert?lbs=<pounds_value>

## Test cases and results
  1. http://<EC2_Public_IP:8080/convert?lbs=0\
     Result: {"lbs":0,"kg":0,"formula":"kg = lbs * 0.4359237"}

  2. http://<EC2_Public_IP:8080/convert?lbs=150\
     Result: {"lbs":150,"kg":68.039,"formula":"kg = lbs * 0.4359237"}

  3. http://<EC2_Public_IP:8080/convert?lbs=0.1\
     Result: {"lbs":0.1,"kg":0.045,"formula":"kg = lbs * 0.4359237"}

  4. http://<EC2_Public_IP:8080/convert\
     Result: {"error":"Query param lbs is required and must be a number"}

  5. http://<EC2_Public_IP:8080/convert?lbs=-5\
     Result: {"error":"lbs must be a non-negative, finite number"}

  6. http://<EC2_Public_IP:8080/convert?lbs=NaN\
     Result: {"error":"Query param lbs is required and must be a number"}


