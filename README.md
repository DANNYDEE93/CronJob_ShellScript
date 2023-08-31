#### <ins> Cron Job Bash Script <ins/>
###### Danielle Davis
###### Date: 8.30.23

##### <ins> Bash Shell Script Guidelines: </ins>

1. The script should run automatically every Friday at 11 pm.
2. Updates the server.
3. Creates a new file to add the outputted upgradable packages.
4. Number the list of upgraded packages.
5. Append the current date of when the script runs onto the end of the new file name.


###### <ins> Purpose: </ins>




###### <ins> One liner command:</ins>  sudo apt-get > /home/ubuntu/upgrad.pack.txt | awk '{print FNR "."$0}' /home/ubuntu/upgrad.pack.txt > /home/ubuntu.pack.txt.$(date +'%m%d%Y') && echo 'the script is complete' && 'the system file has updated' && cd ~ 

###### <ins> Bash Script </ins> 
![bashscript](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/bash_script.png)


###### <ins> Creating Cron Job <ins/>
![crontabs](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/crontab_e%20run%20command.png)


###### <ins> Script Execution </ins>
![run script](https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)https://github.com/DANNYDEE93/CronJob_ShellScript/blob/main/CronJobBashScript/executed_script.png)
