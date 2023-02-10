* [INDEX](../index.md)
* [Joyent Index](./index.md)

# Base Image for containers for Joyent developers and devops

This images is to be created with (Centos 7) to maintain compatibility with the underlying hosts in SPC Ceres-v2

## Tickets | project:joyent +baseImage +devops +containers 
* [X]  test task  #d78ed411
* [ ] DEVOPS-3026 Build base image for all Dev Teams !! (2023-02-10 17:00:00)  #b1447454
    * [X] Collect Version of programs for install  #c6243a0e
        * [X] Collect Version of Python for Base Image  #8d19a430
        * [X] Identify all packages that need to be included in Base Image  #9818f6b7
        * [X] Collect Version of ansible for Base Image  #a5a3b548

## List of packages and Version

| Packages  | Version | Dependencies |
|-----------|---------|--------------|
| Python    |         |              |
| ansible   |         |              |
| awscli    |         |              |
| go-lang   |         |              |
| terraform |         |              |
| JQ        |         |              |
| 


+ Based on  Reply in Jira [CER-1392](https://jira.joyent.us/browse/CER-1392)
 
``` 
When SPC Dev team wants to use Github Action - DevOps team will have a docker image/Virtual image base image that Dev team can use to build through packer and docker build.
Terraform Version : latest version v1.3.7 
Ansible Version: latest core 2.12
Node.js version: latest  18
Python Version: latest 3.10
(cc: BK Kwak Emilio )
```
    
    1. Do we want this images to have all of these packages at these versions for all application, even when not needed?  
    2. Would it not be better to use a base images is OS alone, Then add all packages that are needed for the application?  
    3. golang programs would probably not need terraform or Node.js for example, so why install those packages?
    4. What Happens when the version of python on the bloated image too young or too old for the application being installed on top of it?
    5. What base OS should be used ?  alpine? centos? Other?
    6. I know that the latest version of ansible will not run our hermes playbook, nor will it deploy any of the gage or smaug playbooks.  In fact the gage and smaug require python2 and a really old version of ansible.  Reference question 4 above.
    7. How often are we going to Update this image? Quarterly?

BK response on [CER-1392](https://jira.joyent.us/browse/CER-1392)
- Base image is a Joyent Base image on top of a Host or container base image



