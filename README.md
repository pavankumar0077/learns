CI/CD
=========
Continous Integration == Process set of tools or process that we follow before delivery the application or deploying the application.

Continous Delivery == Is the process where you deploy your application and delivery the application to specific platform 

Ex: App dev (personal laptop)  ---> Customer laptop
Tested -- Scanned -- Reports -- deploy -- Customer will access it

Unit testing
============
--> Dev's testing their own code 
--> Testing own code with specific conditions

Static code analysis
===================
Syntax check
formatting check
indentation check

Ex: In an application if we are declared lot of variables but only using few then 
wastage of memory is there, To reduce that we have to do static code analysis

Code quality/Vulnerability
========================
Code quality testing any vulnerablity with new version 

Automation testing
=====================
Functionality testing on end to end testing on application for example addition function is not implacing sub or mul function 

Reports
========
Esstential 
Reports of code quality and other stuff

Deployment state
================
Deployment is available to the customer to access it





![image](https://user-images.githubusercontent.com/40380941/232177809-56eca833-c894-4e61-afde-fe77c11d5a77.png)

Step. 1) Dev pushes or commit the code to github -- CI/CD tool Jenkins will watch the github for any specific repo branch and if it finds any commits then it will trigger jenkins pipeline -- Here we are taking a java application    -- Using Maven build tool
                                                             -- Junit/Jacoco -- testing
                                                             -- Sonar for code quality testin
                                                             -- ALM/Reporting
                                                             -- K8's/Docker image/EC2
                                                             
                                                             
![image](https://user-images.githubusercontent.com/40380941/232178164-183527f4-2f5a-4b96-8426-c2b15dd79d81.png)
                                                            
                                                        
Step. 2) App --> Github --> Jenkins -- Dev
                                    -- Stage
                                    -- Prod
      Jenkins will take care of deploying our app'n in multiple env's.
      If everything is working fine in Dev(deploy EC2 example.. single node for testing) then it will be moved in Stage(deploy Kubernets example more nodes for       tesing ) and .... Prod(more nodes and higher cost required)
      
      Now Everthing or services are with microservices
     ![image](https://user-images.githubusercontent.com/40380941/232178213-2d007a4c-4d83-4f73-8a5e-10b72c3a8898.png)
     
     Compute is very costly 
         -- RAM
         -- CPU
         -- Hardware
         
     Costly Maintainence
            -- Scale up
            -- Scale Down
            
      ![image](https://user-images.githubusercontent.com/40380941/232178505-177e9959-9b6c-47ec-b547-f3ccbef5c2b1.png)

 
      1. We need to look for automatice setups which are used for scale up and scale down
                                                                  -- Zero master nodes
                                                                  -- For example on weekends if we don't want to use any vm's then it is not possible using jenkins
                                                                  -- Jenkins is not at all recommend
                                                                  
                                                                  --> Kubernets will manage this things open source
     
   GitHub Actions == Another way of doing CI CD just like jenkins 
   Example : Kubernets github repo more than 5k contributors and it will manage by using github actions to test whether the job failed or success
   Whenever code change is made it will run -- Kubernets pod/Docker container  and everything will gets executed on Docker container 
   If docker container is not in use or execution completed then the container will be used for some other projects to run and execute like shared resources
   
   Runners == Worker nodes from microsoft
   
   Github actions and if we are using runner form github itself 
   -- OR we are using runner from microsoft
   -- Microsoft will created containers for you or kubernetes pods for you on microsoft servers or azure servers itself. So don't even know where the servers are      created. Public project or open source project we will get it for free.
   
   -- Incase if we don't want to using microsoft runner or any other runner then 
      -- Make a service on aws or kubernets cluster anywhere in the world
      -- Whenever dev making any of the change in the repo's then we can create kubernets pod on this kubernets cluster after execution is done just delete the pod then i will free so that any other project can use the kubernets cluster.
      
      Note: Instead of creating resouce for each and every project, Instead of creating jenkins instances for each and every project
      We can create one common github actions, Which can be used across multiple project in your organization or multiple project in your organization.
      So we can save our resources and save our compute, if nobody is using it then no wastage becoz the service size is shared acorss everone litterally we are using zero compute instances when their is no code change 
      
      Scaling up is easily done here
      
      
      
      
      Alternative of CICD
      ===================
      Github Actions (Many advantages)
      GitLab
      Cricle CI
      Tervis CI
      
