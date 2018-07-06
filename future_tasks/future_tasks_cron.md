## Scheduling one-time tasks with at
```sh
$ atq
```
- Scheduling a job to run at 15:00 tomorrow, using the g queue.
```sh
$ at -q g holiday tomorrow
at> touch /home/student/holiday
at> Ctrl+D
```
- Check the pending jobs
```sh
$ atq
```
## Jobs with cron
>- crontab -l       ## List all Jobs   
>- crontab -r       ## Remove all Jobs
>- crontab -e       ## Edit Jobs

- crontab editor
```sh
$ crontab -e
```
- example
> 0 0 2 2 *  <file_path..
- Execute at exactly 9 am on February 2nd,every Year
# References
- crontab(5) man pages
- crontab(1)  man pages
