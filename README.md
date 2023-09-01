#### <ins> Cron Job Bash Script <ins/>
##### Danielle Davis
##### Date: 8.30.23
________________________________

##### <ins> Purpose: </ins>

&emsp;&emsp;&emsp;&emsp;  To create a Bash script to automatically update the server, create a new file to input the outputted packages of data, list the new updated data numerically, and to add the current date of each update to the end of the new file created. Most importantly, these requeirements were to update the server every Friday at 11pm, which allows developers to automate their software to create, debug, and execute source code, in order to automatically update data to their database.
____________________________
###### <ins> One liner command:</ins>  sudo apt-get > /home/ubuntu/upgrad.pack.txt | awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt >> /home/ubuntu.pack.txt.$(date +'%m%d%Y') && echo 'the script is complete' && echo 'the system file has updated' && cd ~ 
_________________________________________________


#sudo apt-get > /home/ubuntu/upgrad.pack.txt

**sudo apt-get** downloads package data from all configured sources in the server & the **'>'** symbol into the **path** to the file I want the updated date to go into

#awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt >> /home/ubuntu.pack.txt.$(date +'%m%d%Y')

**awk '{print FNR "."$0}'**  numbers the list of packages in the file i created that contains the updated packages **/home/ubuntu/upgrad.pack.txt**, then **>> /home/ubuntu.pack.txt.$(date +'%m%d%Y')** adds the date at which each update occurs from the updated package file onto the end of the name of the file whih allows the user know the server updated every Monday morning. 

**&& echo 'the script is complete'** lets the user know the script has been completed & **echo 'the system file has updated'** lets the user know the system file has been updated & **cd ~** redirects the user in to the home directory in which the updated package file is located


###### <ins> Bash Script </ins> 
![bashscript](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/bash_script.png)

____________________________________

<ins> # { 0 23 * * 5 } /home/.ssh/cron.job.sh</ins> 

The purpose of the Cron Job allows my script to automate at a certain time. { 0 23 * * 5 } represents "minute", "hour", "day of the month", "month", "day of the week". This cron schedule notation creates the automatic execution of my **cron.job.sh** bash script every week on Friday at 11pm.

###### <ins> Creating Cron Job <ins/>
![crontabs](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/crontab_e%20run%20command.png)

_______________________________

The script came back with no errors, let the user know the updates I commanded it to, and redirected the user to the home directory to shorten their path to the updated package file.

###### <ins> Script Execution </ins>
![run script](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)
