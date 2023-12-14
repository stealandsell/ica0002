------- MYSQL


Install and configure infrastructure with Ansible:

    ansible-playbook infra.yaml

Restore MySQL data from the backup:

    sudo -u backup duplicity --no-encryption restore rsync://stealandsell@backup.gamblinggreats.io/mysql /home/backup/restore/mysql
    sudo su - root
    mysql agama < /home/backup/restore/mysql/agama.sql

how the result of backup restore can be checked?

1st visually on AGAMA
2nd  by running this command on MYSQL server - sudo mysql -e "SELECT * FROM agama.item" agama


------- INFLUXDB

Restore MySQL data from the backup:

    sudo -u backup duplicity --no-encryption restore rsync://stealandsell@backup.gamblinggreats.io/influxdb /home/backup/restore/influxdb
    sudo service telegraf stop
    influx -execute 'DROP DATABASE telegraf'
    sudo influxd restore -portable -database telegraf /home/backup/restore/influxdb
    

After you have verified that backup was restore successfully, run

    ansible-playbook infra.yaml 
    
to start the Telegraf service.
