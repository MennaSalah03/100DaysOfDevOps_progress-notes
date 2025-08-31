For this task, we are supposed to create something called a cron job. It basically is a 'job' or task done *periodically* as specified in it's setting. 
It sounds like a nice solution to many issues, but It's not fail proof and can't be corrected real time. If it failed then the system moves on, so it's not used for time-critical processes or jobs

1. The first step was to install a package called cronie and start the sevice
```bash
sudo yum install -y cronie
systemctl start crond
```

 Example of job definition from crontab file:
```
# .---------------- minute (0-59)
# | .------------- hour (0-23)
# | | .---------- day of month (1-31)
# | | | .------- month (1-12) OR jan,feb,mar,apr ...
# | | | | .---- day of week (0-6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# | | | | |
# * * * * * user-name command to be executed
```
2. Use `contab` command to view create the specified job
```bash
# view
crontab -e
# create by adding the specified line to the file
*/5 * * * * echo hello > /tmp/cron_text
```
3. Restart the `cronie` service and see the status
```bash
sudo systemctl restart crond
sudo systemctl status crond
```

## Resources
- [cronie - Timed Tasks - Documentation](https://docs.rockylinux.org/guides/automation/cronie/)