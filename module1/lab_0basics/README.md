Deployment	Public IPv4 address	Connection method	Screenshot	       Instance terminated?
1	        18.118.21.210               SSH	    screenshots/deployment-1.png	Yes
2	        3.145.150.44	            SSH	    screenshots/deployment-2.png	Yes
3	        18.188.237.80	            SSH	    screenshots/deployment-3.png	Yes 

Deployment 1

To connect this EC2, I typed in 'Instances' in the AWS search bar then went to an instance I created. I then right-clicked and pressed 'Launch instance from Template.' I selected my original instance, 'Rinnegan,' as my source template. I kept all of my defaults the same, then I pressed 'Launch instance.' The dashboard displayed 'SEIR Foundations' at the top then a table of my current uptime, CPU, load average, memory, root disk, instance ID, instance type, and AWS zone. 

Deployment 2
To connect this EC2, I typed in 'Instances' in the AWS search bar then went to an instance I created. I then right-clicked and pressed 'Launch instance from Template.' I selected my original instance, 'Rinnegan,' as my source template. I kept all of my defaults the same, then I pressed 'Launch instance.' The dashboard displayed 'SEIR Foundations' at the top then a table of my current uptime, CPU, load average, memory, root disk, instance ID, instance type, and AWS zone.  

Deployment 3
To connect this EC2, I typed in 'Instances' in the AWS search bar then went to an instance I created. I then right-clicked and pressed 'Launch instance from Template.' I selected my original instance, 'Rinnegan,' as my source template. I kept all of my defaults the same, then I pressed 'Launch instance.' The dashboard displayed 'SEIR Foundations' at the top then a table of my current uptime, CPU, load average, memory, root disk, instance ID, instance type, and AWS zone. 

CPU tells me what percent of my available processing time is currently being spent performing a task. Memory tells me how much space my CPU has to hold data and programs at a given moment. Disk tells me how much permanent storage space I have available for files, operating system, applications, and data. Uptime tells me how long my operating system has been running since the last start of the instance. This resets when I stop and start the instance. 

One thing that became easier after repeating the process was creating instances. Once I figured out which presets to leave alone and which ones to configure, it became easier to create and deploy them. At first, I encountered an error that said 'Failed to connect to instance. SendSSHPublicKey failed.' I resolved this issue by going back to my root user account and changing the permissions so my CLI Admin account would be able to have the privileges required to connect to an EC2 instance. 

I know I retained the launch template because when I go into AWS and click 'Launch templates' then select a source template, the original template I created is still there. I know it would also show up if I navigated to the 'Instances' tab but I terminated it to save compute spend. I cleaned up the practice instances by going to Instances, right clicking on the practice instance, then clicking "Terminate (delete) Instance." This stopped the instance from running and prevented unnecessary spending. 