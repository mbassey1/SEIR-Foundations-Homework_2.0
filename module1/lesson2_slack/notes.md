**Answers to questions in each script:**

Script 2
Q: Which severities arrived, and WHY those?
A: All severities arrived because when I <nano>'d into the hw2 python file, a conditional statement told it to print out all of the severities at once and did not set conditions on whether one should appear vs. another.

Script 3
Q: How many hours apart are server time and YOUR wall clock?
A: The current time is 3:13 PST, or 23:13:14 UTC. The times on my wall clock and server are in sync. 


Script 4
Q: Why is a quiet INFO here GOOD design, not a failure?
A: Quiet info is a good design and not failure because it gives me a status update without restricting what I can and can't do in an application.

Script 5 
Q: What would make this number spike on the Balerica bank?"
A: This number would spike on the Balerica bank at times of high usage for financial transactions. Examples of this would be during holidays like Thanksgiving and Christmas. 

Script 6 
Q: Which of these fake incidents deserves to wake a human at 3 AM?
A: We should wake someone at 3pm if the ledger is unreachable and maybe if the rejection rate is above 5 percent. This is because these signal errors that a computer can't rectify on its own but rather are issues that require a human being to fix. 

**Prediction vs. Result from Experiment 1:**
Prediction 1: When I change alert severity to critical then run script I predict only 1 of the messages (for critical) will arrive. This is because the conditional statement has been changed for the function and no other function has been issued for the other conditions. 

Result: My prediction was correct. 

Prediction 2: When I change alerts enabled to false then run script 1, I predict I won't get any alerts.

Result: I did not get any Slack alerts and I got a message in the EC2 saying that slack alerts enabled must be false and slack alert severity must equal info. 

A kill switch like this is useful during maintenance windows for multiple reasons: (1) it lets you make changes without flooding channels with unnecessary messages; (2) you can edit agent actions without taking the agent down entirely; and (3) it lets you safely test and run different scripts without putting unnecessary notifications into the channel. 

Prediction 3: When I change the warning threshold for script 4 then rerun the script, I predict my severity will change to a "WARNING." This is because I set the usage threshold to below my current threshold at the time, which is 25.5%.

Result: Yes, the severity did change to "WARNING."

