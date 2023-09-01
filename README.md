#### <ins> **Cron Job Bash Script** <ins/>
##### Danielle Davis
##### Date: 8.30.23
________________________________

#### <ins> **Purpose** </ins>

&emsp;&emsp;&emsp;&emsp;  To create a Bash script to automatically update the server, create a new file to input the outputted packages of data, list the new updated data numerically, and to add the current date of each update to the end of the new file created. Most importantly, these requeirements were to update the server every Friday at 11pm, which allows developers to automate their software to create, debug, and execute source code, in order to automatically update data to their database.

____________________________

#### <ins> One liner command:</ins> sudo apt-get > /home/ubuntu/upgrad.pack.txt | awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt > /home/ubuntu.pack.txt.$(date +'%m%d%Y') && echo 'the script is complete' && echo 'the system file has updated' && cd ~
_________________________________________________

#### <ins> **Bash Script** </ins> 

1. <ins>sudo apt-get > /home/ubuntu/upgrad.pack.txt</ins>

**sudo apt-get** downloads package data from all configured sources in the server & the **'>'** symbol puts the info into a newly created file with the absolute **path** to the file

2. <ins> awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt > /home/ubuntu.pack.txt.$(date +'%m%d%Y') </ins>

**awk '{print FNR "."$0}'**  numbers the list of packages in the file i created that contains the updated packages **/home/ubuntu/upgrad.pack.txt**, then **'>' /home/ubuntu.pack.txt.$(date +'%m%d%Y')** adds the date to each file name that is created by the script for when the update that occurs allowing the user to know the server updated. *(see **Cron Job Notation** for scheduling the script execution)*

3. <ins> echo 'the script is complete' && echo 'the system file has updated' && cd ~</ins>

**echo 'the script is complete'** lets the user know the script has been completed  **echo 'the system file has updated'** lets the user know the system file has been updated & **cd ~** redirects the user in to the home directory in which the updated package file is located. The **'&&'** symbol just lets the script know that it needs to complete the first command on the left of the symbol before completing the second command on the right


![bashscript](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/bash_script.png)


____________________________________

#### <ins> **Cron Job Notation** <ins/>

<ins> { 0 23 * * 5 } /home/.ssh/cron.job.sh </ins> 

&emsp;&emsp;&emsp;&emsp;  The purpose of the Cron Job allows my script to automate at a certain time. { 0 23 * * 5 } represents "minute", "hour", "day of the month", "month", "day of the week". This cron schedule notation creates the automatic execution of my **cron.job.sh** bash script every week on Friday at 11pm. I placed this notation in the crontab directory that can be found in the path **/var/spool/cron/crontabs/** and then used **crontab-e** to open the crontab file text editor once there. In the crontab directory, the user can create and edit commands withint the user's file system without looking for a specific file.

__________________________________
> &emsp;&emsp;&emsp;&emsp;  Placing the timestamp onto the file name within the script as I described under **Bash Script** <ins>and not in the cron job, </ins> decreases reliance on the external factors of the cron job for script execution. The standalone script increases portability, reproductibility and distribution of it among additinal team members. Also, self- containing a script allows for simplicity within the script's deployment and increases security because the code is isolated and separate from the impact of external vulnerabilities. 
____________________________________________________

![crontabs](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/crontab_e%20run%20command.png)


&emsp;&emsp;&emsp;&emsp;  Alternatively, if the user wanted to include the timestamp in the the cron job instead of the script as depicted above, a new file for each update is still created: **<ins> { 0 23 * * 5 } /home/.ssh/cron.job.sh >> /home/ubuntu.pack.txt.$(date +'%m%d%Y') </ins>** This can help the user control the filename format externally so the script does not need to be modified and you can control multiple cron jobs at once. Utilizing cron jobs helps increase resource efficiency, community contributions, and allows users to break code into smaller, more manageable components to be reused for separate concerns of functionality. Using cron jobs can also increase upgradability so when external libraries and packages are updated, the lastest versions can be easily incorporated in the system on an automatic schedule without having to manually manipulate the source code.
_______________________________

#### <ins> **Script Execution** </ins>

The script came back with no errors, let the user know the updates I commanded it to, and redirected the user to the home directory to shorten their path to the updated package file.


![run script](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)

