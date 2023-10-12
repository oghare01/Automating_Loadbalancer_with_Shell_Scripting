# Automating_Loadbalancer_with_Shell_Scripting

1. Provision an EC2 instancer

An AWS instance running Ubuntu 20.04 was provisioned and run as shown below

![EC2 instance](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/824c4650-82e9-4e0b-9485-ec6ff690d94c)

2. Security group configuration

Secondly the security group inbound rule was modified to allow traffic flow from anyhere on Port 8000

![Inbound rule modification](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/98ce4fa6-3597-4f26-beae-617a5a15253f)

3. Connect to the Webserver

The webserver was connected via the terminal using the SSH client 

![webserver connected into via ssh](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/62d0a5c8-e67d-4268-8cbf-01a6f5e1a7e2)

4. Automation script setup

Next, a script which creates and automates the installation and configuration of apache to listen on port 8000 was written 

![Auomation script](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/0c29720f-bafd-432e-acd3-58d64063d36e)

5. Permision modification

To make the script which was written pass the command and work as intendend, the file permission for the script was changed using the "sudo chmod +x" command
This command should make the file executable. 

6. Running th shell script

Using the ./ commmand, the shell script was run and the result showed that apache2 was running and the script worked perfectly 

![Script 1 running successfully](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/b90a2943-5868-4d3e-a5e5-1873c58dc7b0)

7. Second webserver setup

With the first webserver running apache setup. a second EC2 instance which would be used for the loadbalancer was setup 
For this instance, the inbound rule was modified to allow traffic via port 80 to anywhere as can be seen in the following screenshots

![Loadbalancer instance](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/cb6439c9-b0f8-470e-bf26-a7b7a22a69cf)

![Loadbalancer inbound rule](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/bc125e8f-7de1-4017-872a-e336e6ce351a)

8. Nginx script setup

A script to install and setup the Nginx (the loadbalancer) was written after connecting to the second webserver via SSH 
![Nginx script](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/63d6dae0-5b84-40b3-afb0-cfb55785fce8)

9. File permission and script run

The file permission to enable the script become executable was carried out and the script was run 
The result showed that Nginx was setup successfully by running the script 

![Nginx setup successfully](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/a30cb84f-e139-4125-b87b-2b686c6bf994)

10. Testing the IP addresses

With the two systems setup, a check was carried out for both IP addresses. 
The results revealed that the webserver 1 worked as planned while the Nginx weberserver did not seem to give the intended result 

![web 1](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/02bd0ed5-18f3-4b6a-8545-f626dda27654)

![Web 2](https://github.com/oghare01/Automating_Loadbalancer_with_Shell_Scripting/assets/141191975/89dffecd-b12c-4b40-ac50-91b39dcd03bc)

Further work would be needed to see why the loadbalancer doesn't match the expected result 
