## Outcomes
- runs every two minutes between 09:00 and 16:59 on Monday to Friday.
- appends the current date and time to the file
 /home/my_first_cron_job
- Open text editor
 ## Lab activity
```sh
$ crontab -e
```
Insert the Following line:
```sh
*/2 9-16 * * 1-5 date >> /home/my_first_cron_job
```
- Save your changes by;
```sh
:wq
```
- Inspect all of your scheduled cron jobs
```
$ crontab -l
```
# Remove Jobs
```sh
$ crontab -r
```
