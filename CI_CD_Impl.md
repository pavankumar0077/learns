To find which service running on which port
Ex: Jenkins

ps -ef | grep jenkins 
------------------------
Will show on which port jenkins is running 


Befault AWS will bot allow all the port to run like allowing the traffic from any port is not allowed 
Instance details -- Security -- Security groups -- Edit inbound rules 
---> Add rule
-- Customemr TCP port range anywhere 

Now open instance details and check jenkins is working or not
Copy public ip and port of jenkins here it is 8080 and check jenkins 

--> Install suggested plugins
--> Configure admin pwd 
--> now jenkins is ready to use



