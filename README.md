# spring-boot-tomcat-deployment

Example project to deploy a spring boot application into a tomcat instance

## setup empty AWS EC2 instance

* create a new EC2 instance
  * create/reuse a security group with TPC port 80 open
* connect to the instance (via SSH or the web interface)
* run this command:
    ```bash
    curl -s https://raw.githubusercontent.com/bartfastiel/spring-boot-tomcat-deployment/main/provisioning.sh | bash -s
    ```

* you can now publish your war files like this (change password and url accordingly)
    ```bash
    curl --user admin:s3cret --upload-file backend-0.0.1-SNAPSHOT.war "http://ec2-11-111-11-111.eu-north-1.compute.amazonaws.com/manager/text/deploy?path=/myapp" -v
    ```

🚀 The app is deployed to http://ec2-11-111-11-111.eu-north-1.compute.amazonaws.com/myapp/ 
