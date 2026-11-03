Run 1 (i-058b825486164ac52): 
I realized mid-run during what was supposed to be my second run that I had incorrectly run the ID line. Therefore, my screenshot for Practice Run 1 will appear as Practice Run 2. To differentiate for the future, my next one will be Practice Run 2a. After that, the run numbers in the txt file will match the run numbers on the screenshots.

 I only copied the whoami and TZ = 'Your/Zone' date but did not see the <ec2-metadata -i> and <uptime -s> commands. During this run what changed was that I learned to keep one instance open at a time. I made the error when selecting my time zone. I entered the template and the outlet didn't register it. I newly understood that if I want to get the time in the time zone I am working in, I can put America, then an underscore between words if my city is more than one word. 

Output line from run: 
(venv) [ec2-user@ip-172-31-23-81 balerica-bank]$ whoami && TZ='Your/Zone' date && ec2-metadata -i && uptime -s
ec2-user
Thu Oct 29 23:52:53 Your 2026
instance-id: i-058b825486164ac52
2026-10-29 23:33:19

Run 2 (i-02c159211383f4c8a):
What changed was that this time I was able to succesfully run the entire ID line. An error I hit was that I originally thought I needed a command to find my uvicorn server PID. My fix was copy-pasting the transcript of this command prompt session and asking AI where my uvicorn ID was. I now understand that the uvicorn id is located on the output line that says <INFO:     Finished server process [number]>. The number inside of that bracketed box represents the uvicorn server PID. I learned that this is used to identify whether a specific server is running. 

Output line from run: 
INFO:     Finished server process [35198]

Run 3 Notes: 
What changed was that I began learning why certain COBOL codes trigger certain responses. Specifically, I learned what the 0, 4, 8, and 12 return codes mean. An error I hit was when I tried pasting evidence from my CLI in AWS. Instead of just taking my command, I copied the primary prompt string. I then tried to repeat that command and it didn't work because Linux read the syntax as incorrect. My fix was that I removed the prompt and only copied the command. I now understand that if text appears on a line before I've even entered a command, that is not part of the actual command; it is simply a prompt. 

Output line from run: 
INFO:     Started server process [35428]

Run 4 Notes: 
What changed was that in this run I began learning the specific differences in some instance configurations. Specifically, I learned why an image is different from an instance type. I did not encounter any errors on this run, therefore, there were no fixes I needed to make. I now increasingly understand that an image represents a blueprint of a server but can also be used to launch other servers. 

Output line from run: 
INFO:     Started server process [35326]

Run 5 Notes: 
What changed was that I learned that the <uvicorn> command triggers a different process ID whenever the process is launched again. An error I hit was when I was attempting to screenshot my evidence for Practice Run 5, I forgot to include my time zone. Because the directions said to do the ID line command before the uvicorn command, I had to close the server process, redo my ID line command, then run the uvicorn command again. Through this process I now understand that because uvicorn is a bridge used to connect Python to COBOL that is not native to the language, I have to 'turn it on and off' in order for the server to properly function. 

Output line from run: 
INFO:     Started server process [36347]

Run 6 Notes: 

What changed was that I started being able to differentiate between commands that let me confirm my prior commands work and commands that allow me to install software. In terms of errors, I forgot to include my specific time zone in the code so I had to run it again with my specific TZ. Because this was the run where I practiced decoding COBOL ledgers, I now understand that in essence, each character represents a 'column' of data. Therefore I can execute <cut -c> commands to determine what columns of data represent.

Output line from run: 
INFO:     Started server process [37535]


Run 7 Notes:
What changed was that I figured out how to easily clone one of my repos from Git. I simply need to enter the <git clone <url of repo>> command. I did not hit any errors. I now understand that Git repos can be cloned and uploaded onto EC2 instances and other servers connected to the cloud. 

Output line from run: 
INFO:     Started server process [35827]


COBOL practice: 

Which run and Instance ID you used: I used run 3, instance ID i-02b1543090947c89f. 
The command and exact output lines for each return code: 
Return code 0 
Command lines: 
(venv) [ec2-user@ip-172-31-22-249 balerica-bank]$ ./cobol/bin/payment_post TXN-MB-0001 100001 125.50 USD INV-1001 125.50 USD INV-1001
echo $?
Output lines: 
TXN=TXN-MB-0001
ACCOUNT=100001
AMOUNT=125.50
CURRENCY=USD
STATUS=POSTED
REASON=APPROVED
0


Return code 4
Command lines: 
./cobol/bin/account_lookup 999999
echo $?

Output lines: 
ERROR=ACCOUNT NOT FOUND
ACCOUNT=999999
4

Return code 8 
Command lines: (venv) [ec2-user@ip-172-31-22-249 balerica-bank]$ ./cobol/bin/payment_post TXN-MB-0002 100001 0.00 USD INV-1002
echo $?

Output lines: 
TXN=TXN-MB-0002
ACCOUNT=100001
AMOUNT=0.00
CURRENCY=USD
STATUS=REJECTED
REASON=AMOUNT MUST BE GREATER THAN ZERO
8

Return code 12
Command lines: 
(venv) [ec2-user@ip-172-31-22-249 balerica-bank]$ cd /tmp
(venv) [ec2-user@ip-172-31-22-249 tmp]$ /opt/balerica-bank/cobol/bin/account_lookup 100001
(venv) [ec2-user@ip-172-31-22-249 tmp]$ echo $?

Output lines:  
ERROR=CANNOT OPEN data/accounts.dat
FILE-STATUS=35
12

Alice's balance decoded by hand: 
5000.00
I did this by moving two places from the right. In COBOL the balance is listed as 12 digits. This means the bank account can hold up to 10 figures of currency. More specifically, for every file in this data folder, columns 1-6 represent the account ID, columns 7-36 represent the customer name, columns 37-44 represent the account status, columns 45-56 represent the account balance with implied decimals, and columns 57-59 represent the currency. 


The journal lines for your own TXN IDs, and whether the balance changed: 
(venv) [ec2-user@ip-172-31-22-249 balerica-bank]$ ./cobol/bin/payment_post TXN-MB-0001 100001 125.50 USD INV-1001
TXN=TXN-MB-0001
ACCOUNT=100001
AMOUNT=125.50
CURRENCY=USD
STATUS=POSTED
REASON=APPROVED

(venv) [ec2-user@ip-172-31-22-249 balerica-bank]$ ./cobol/bin/payment_post TXN-MB-0002 100001 0.00 USD INV-1002
TXN=TXN-MB-0002
ACCOUNT=100001
AMOUNT=0.00
CURRENCY=USD
STATUS=REJECTED
REASON=AMOUNT MUST BE GREATER THAN ZERO

The balance did change.


List of mistakes I made: 
Entering the time zone incorrectly 
Pulling the uvicorn server PID


Commands I know by heart: 
git clone <url> : allows me to clone a repository
ls : allows me to see what is inside of a folder
pwd: print working directory - allows me to know which folder I'm in 

