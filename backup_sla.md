------------------------------------------[Backup coverage]

+ Backup covers only InfluxDB and MySQL services, which cannot be restored once lost

------------------------------------------[RPO (recovery point objective)]

+ The incremental backup system restores data prior to the point where it was lost

------------------------------------------[Versioning and retention]

+ Local backup - once a day at 01:00 - deleted once a day right before new backup is made.
+ Full backup - every Sunday at 01:30 - kept for one month.
+ Incremental backup - (Monday -> Saturday) 01:30 - kept for one week.

------------------------------------------[Usability checks]

+ Checked by using administration tools on virtual environment once a week

------------------------------------------[Restoration criteria]

+ Executed if data is lost in any possible case

------------------------------------------[RTO (recovery time objective)]

+ Recovery can take up to 2.5 hours
