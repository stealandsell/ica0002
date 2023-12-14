------------------------------------------[Backup coverage]

+ Backup covers only InfluxDB and MySQL services, which cannot be restored once lost

------------------------------------------[RPO (recovery point objective)]

+ The incremental backup system restores data prior to the point where it was lost

+ The maximum amount of data we can lose is 23 hours

------------------------------------------[Versioning and retention]

+ Full backup - every Friday at 00:00 - kept for one month.
+ Incremental backup - (Monday -> Saturday) 00:30 - kept for one week.

------------------------------------------[Usability checks]

+ Checked by using administration tools on virtual environment once a week

------------------------------------------[Restoration criteria]

+ Executed if data is lost in any possible case

------------------------------------------[RTO (recovery time objective)]

+ Recovery can take up to 2.5 hours
