# 3. Bash

### Example I

**backup files using rsync and crontab**

---

\(1\) Prepare a backup script, for example, "_~/backup.sh_"

```bash
#!/bin/bash

RSYNC="rsync --stats  --compress --recursive --times --perms --links --delete --max-size=100M --exclude-from=/home/zl222/.rsync/exclude"

#1. Local backup  
#backing up /home1/zl222 to /home/zl222/sub_dir

echo "1. Backup of /home1/zl222 start at:"
date

$RSYNC /home1/zl222/ /home/zl222/backup_ncrna_home1/ 

echo "Backup end at:"
date



#2. Remote backup 

RSYNC="rsync --stats  --compress --recursive --times --perms --links --delete --max-size=100M --files-from=/home/backup1/backup_file"

echo "2. Backup 172.22.220.20:/data/ to /home/backup1/ start at:"
date

$RSYNC liushanhu@172.22.220.20:/data/ /home/backup1/

echo "Backup end at:"
date
```

\(2\) Using "crontab" command to execute the backup script routinely, and record in a log file, for example,

execute the command "_~/backup.sh &gt; ~/backup.log_" in 5:10am everyday:

```
1) open crontab and edit it by the following command: 

crontab -e 

2) type in the following lines: 

# minute hour day_in_month month day_in_week command
     10   5  * * *   ~/backup.sh > ~/backup.log 

3) exit and save (like in VIM)
```

### 



