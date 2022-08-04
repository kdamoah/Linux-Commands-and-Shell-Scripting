# Linux-Commands-and-Shell-Scripting-Final-Project_IBM-Data-Engineering-Professional-Certificate

This is a project on linux commands and shell scripting as part of IBM Data Enginnering Professional Certificate. 

The scenario of the project is below:

You are a lead linux developer at the top-tech company "ABC International INC." ABC currently suffers from a huge bottleneck - each day, interns must painstakingly access encrypted password files on core servers, and backup those that were updated within the last 24-hours. This introduces human error, lowers security, and takes an unreasonable amount of work. As ABC INC's most trusted linux developer, you have been tasked with creating a script 'backup.sh' which automatically backs up any of these files that have been updated within the past 24 hours.

After the 'backup.sh' script is created, the following codes are run in the terminal.

chmod u+x backup.sh   # To make the script executable

ls -l backup.sh       # Verification that the file is executable

wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/Final%20Project/important-documents.zip	  	# This is a zip file to be downloaded

unzip -DDo important-documents.zip	    # Unzip the archive file

touch important-documents/*		      # Update the file's last modified date to now

./backup.sh important-documents .	    # Test the script to create a file called 'backup-[CURRENT_TIMESTAMP].tar.gz' in the current directory

sudo cp backup.sh /usr/local/bin/	    # Copy 'backup.sh' into the /usr/local/bin/ directory

crontab -e	    # Open crontab editor

0 0 * * * /usr/bin/backup.sh ~/important-documents ~	      # Schedule the /usr/local/bin/backup.sh script to backup the important-documents folder every 24 hours to the home directory (~)

crontab -l	    # List all cron jobs
