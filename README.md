# linuxscripts
Collection of useful scripts

## emailCheck.sh
Low tech tool to cleanup mailing lists from unwanted emails.
Performs various checks on a list of email adresses:
1. Checks address' compliance against RC822, if not, deletes email
2. Checks address' domain for known typos and corrects them
3. Checks if email domain has MX records, if not, deletes email
4. Checks if email contains words like example or test, rendering them ambiguous, and puts them into a separate file

Usage:
emailCheck.sh /path/to/email_list

Script has commented out lines for the while loop in order to read simple lists or CSV files
Warning: Using files comming from windows need prior conversion with dos2unix tool. 

## ddsplit.sh (quick and dirty dd backup)
Performs disk backups via dd, compresses and splits into file chunks.
Restores the splitted files to disk.

Usage:
ddsplit.sh --backup /dev/sdX /mnt/myFile 1G
ddsplit.sh --restore /mnt/ddsplit.1G.main.myFile.gz /dev/sdY

## ssh_jail.sh
Creates a full ssh jail with basic commands like cp, mv, etc
