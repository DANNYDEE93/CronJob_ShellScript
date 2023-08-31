#### <ins> Cron Job Bash Script <ins/>
##### Danielle Davis
##### Date: 8.30.23
##### <ins> Purpose: </ins>

&emsp;&emsp;&emsp;&emsp;  Bash is a programming language often used with the Ubuntu OS under the Linux kernel system and installed on most Linux OS' with Mac OS coming with a default Bash user shell and with Linux system already coming integrated on the Windows 10 OS versions and later. The benefits of Bash extend to various fields, not just technology, due to the fact that its easily accessible by different users. Bash is also easy to create and run mulitple commands which saves engineers from spending time on coding so they can ensure the quality of their deployment process and automation of their CICD pipeline. 

&emsp;&emsp;&emsp;&emsp;  The point of ths script was to implement various Bash commands, to fulfill the provided requirements, that may be asked of you by an employer, as well as to develop skills to upgrade business infrastructures of various companies. This new script need to contain commands in order to allow the system to update the server, create a new file to input the outputted packages of data, number this data in a numerical list form, and to add the current date of each update to the end of the new file. Most importantly, these requeirements were to automatically update the server every Friday at 11pm, so that the engineer/developer does not have to repeat the code maually.  

###### <ins> One liner command:</ins>  sudo apt-get > /home/ubuntu/upgrad.pack.txt | awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt > /home/ubuntu.pack.txt.$(date +'%m%d%Y') && echo 'the script is complete' && 'the system file has updated' && cd ~ 


###### <ins> Bash Script </ins> 
![bashscript](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/bash_script.png)


###### <ins> Creating Cron Job <ins/>
![crontabs](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/crontab_e%20run%20command.png)


###### <ins> Script Execution </ins>
![run script](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)
