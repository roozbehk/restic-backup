# restic-backup
## backup.sh
```
#!/bin/bash

source  ~/.restic-keys

echo -e "\n`date` - Starting backup...\n"

export RESTIC_REPOSITORY="s3:https://s3.us-east-2.wasabisys.com/techguys.io.web"


/home/master/restic/restic backup /home/533180.cloudwaysapps.com --no-cache

echo -e "\n`date` - Running forget and prune...\n"

/home/master/restic/restic forget --prune --keep-daily 7 --keep-weekly 4 --keep-monthly 6

echo -e "\n`date` - Backup finished.\n"
unset AWS_ACCESS_KEY_ID
unset AWS_SECRET_ACCESS_KEY
unset RESTIC_PASSWORD
unset RESTIC_REPOSITORY

curl https://betteruptime.com/api/v1/heartbeat/SvChSJpvtqAHYLunUT8dP2fg


```

`.restic-keys`

```
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export RESTIC_PASSWORD=""
export RESTIC_REPOSITORY="s3:https://s3.us-east-2.wasabisys.com/"

```
