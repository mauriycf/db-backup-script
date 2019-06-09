# db-backup-script

This script is designed to save all the databases and create the logs that have been made with the database backup automatically, the databases and logs will be saved in the following path: (/ data / db- backups) / (logs / db-backups).

at any time you can modify the routes in the script, you can also add different functionalities or data that we want to save in the logs.

in the log section of the script we have two functions, logStart and logEnd. which will create Log File with the variable $ LF, each time this function is called it will save the data that we have selected as the name of the database to the host that we are entering and of course the date each time it is executed .

We also have the function called GetDBList, which is responsible for saving all the available databases in a variable, this part can be modified to save only one or the databases that we only want to backup.

The last function that is one of the most important is the one that is responsible for making the backup, which is called DoBackup (). this is created with the intention of supporting the databases create a logfile and save the databases in the selected folder, you can modify this part to have better results and more security, but that depends on what we need.

Finally, if we want this script to run automatically every day, at a certain time, we have to do the following:

first we need that the script that we have created, can be executed by the root user with the following command

chmod 744 /exampleRuta/example/backup.sh

for the automation of this script we will use the crontab application, we will write it in the terminal as well as crontab -e that will open the application and will ask us to open it with the text editor we want, I recommend nano which is the easiest

Once this is done we will write the following in the last line:

30 22 * ​​* * /usr/local/bin/mysql-backups.sh> / dev / null 2> & 1

Basically this will enable the script to run at 10:30 pm every day. It will also hide any output from the program as the program logs to disk.

If you want to run this script at a different time, I recommend that you read more about the use of crontab.

Well this script is made to be used in your test server, I do not recommend that it be used in a production server because it has security flaws, but if you make the correct modifications to the script and harden the script, it is possible to use it without any problem .

Thanks for taking your time reading this, enjoy your script.

