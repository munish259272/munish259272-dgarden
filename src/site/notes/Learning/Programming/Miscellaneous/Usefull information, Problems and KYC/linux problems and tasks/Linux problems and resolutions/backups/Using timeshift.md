---
{"dg-publish":true,"permalink":"/learning/programming/miscellaneous/usefull-information-problems-and-kyc/linux-problems-and-tasks/linux-problems-and-resolutions/backups/using-timeshift/","dg-note-properties":{}}
---


Ours# QUESTION 1
HOW DO I TAKE BACKUP USING TIMESHIFT FROM COMMAND LINE USING THE CURRENT CONFIGURATION (NOT THE DEFAULT ONE) AND ALSO ADDING A DESCRIPTION.
# YOUR ANSWER 1


To take a backup using TimeShift from the command line with the current configuration and adding a description, you can use the `timeshift` command with appropriate options.

Here’s how to do it:

1. Open a terminal.

2. Run the following command:
   ```bash
   sudo timeshift --create --comments "Your description here"
   ```

Explanation of the command:
- `sudo`: Runs the command with superuser privileges, which is often required for backup operations.
- `timeshift`: The main TimeShift command.
- `--create`: Tells TimeShift to create a new snapshot/backup.
- `--comments "Your description here"`: Adds a description to the backup. Replace `"Your description here"` with your desired description.

This command will create a backup using your current TimeShift configuration and add the specified description to it.

# QUESTION 2
Some given info:
```text
(base) munish259272@munish259272:~$ ls /etc/timeshift/
default.json  timeshift.json
(base) munish259272@munish259272:~$ cat /etc/timeshift/timeshift.json
{
  "backup_device_uuid" : "69cd1ca7-7277-4e1c-83a3-50ebae797bbc",
  "parent_device_uuid" : "",
  "do_first_run" : "false",
  "btrfs_mode" : "false",
  "include_btrfs_home_for_backup" : "false",
  "include_btrfs_home_for_restore" : "false",
  "stop_cron_emails" : "true",
  "schedule_monthly" : "false",
  "schedule_weekly" : "false",
  "schedule_daily" : "false",
  "schedule_hourly" : "false",
  "schedule_boot" : "false",
  "count_monthly" : "2",
  "count_weekly" : "3",
  "count_daily" : "5",
  "count_hourly" : "6",
  "count_boot" : "5",
  "snapshot_size" : "0",
  "snapshot_count" : "0",
  "date_format" : "%Y-%m-%d %H:%M:%S",
  "exclude" : [
    "/var/lib/libvirt/**",
    "/home/munish259272/**",
    "/media/***",
    "/mnt/***",
    "/proc/***",
    "/run/***",
    "/sys/***",
    "/tmp/***",
    "/var/log/***",
    "/dev/***",
    "/opt/***",
    "/snap/***",
    "/nonexistent/**",
    "/root/**"
  ],
  "exclude-apps" : []
}(base) munish259272@munish259272:~$ cat /etc/timeshift/default.json
{
  "backup_device_uuid" : "",
  "parent_device_uuid" : "",
  "do_first_run" : "true",
  "btrfs_mode" : "false",
  "include_btrfs_home" : "false",
  "stop_cron_emails" : "true",
  "schedule_monthly" : "false",
  "schedule_weekly" : "false",
  "schedule_daily" : "false",
  "schedule_hourly" : "false",
  "schedule_boot" : "false",
  "count_monthly" : "2",
  "count_weekly" : "3",
  "count_daily" : "5",
  "count_hourly" : "6",
  "count_boot" : "5",
  "snapshot_size" : "0",
  "snapshot_count" : "0",
  "exclude" : [
  ],
  "exclude-apps" : [
  ]
}
```

Now, I believe in Debian, the current configuration for TimeShift is stored in the file located at `/etc/timeshift/timeshift.json`. This file contains all the settings and parameters that TimeShift uses to create backups. 
If i take a backup using the command `sudo timeshift --create --comments "Your description here"` , is it going to use `/etc/timeshift/timeshift.json` or `/etc/timeshift/default.json`
# YOUR ANSWER 2


When you run the command `sudo timeshift --create --comments "Your description here"`, TimeShift will use the configuration stored in the file `/etc/timeshift/timeshift.json`.

Here's why:

1. **Current Configuration File (`/etc/timeshift/timeshift.json`)**:
   - This file contains the active or current configuration that TimeShift uses for its operations.
   - The parameters set in this file are based on your specific setup and preferences.

2. **Default Configuration File (`/etc/timeshift/default.json`)**:
   - This file contains the default settings that might be used during an initial setup or if no other configuration is provided.
   - It serves as a fallback or template but is not actively used once a custom configuration exists.

When you create a backup using the command `sudo timeshift --create --comments "Your description here"`, TimeShift will prioritize and use the settings from `/etc/timeshift/timeshift.json` since it reflects your customized and current preferences, whereas `/etc/timeshift/default.json` would only be relevant if no other configuration was available.

So, to summarize: running `sudo timeshift --create --comments "Your description here"` will indeed use the configuration specified in `/etc/timeshift/timeshift.json`.

# QUESTION 3
```text
(base) munish259272@munish259272:~$ sudo timeshift --list
Mounted '/dev/sde1' at '/run/timeshift/74977/backup'
Device : /dev/sde1
UUID   : 69cd1ca7-7277-4e1c-83a3-50ebae797bbc
Path   : /run/timeshift/74977/backup
Mode   : RSYNC
Status : OK
5 snapshots, 190.0 GB free

Num     Name                 Tags  Description                                
------------------------------------------------------------------------------
dg-publish: true
0    >  2024-07-22_12-29-26  O                                                
1    >  2024-07-23_01-03-22  O                                                
2    >  2024-07-24_03-21-24  O                                                
3    >  2024-07-29_21-56-41  O   
```
I ALREADY HAVE 4 SNAPSHOTS AS SEEN ABOVE , DOES THAT MEAN I SHOULD USE `sudo timeshift --create --comments "fixed mount_onedrive_mukesh259272.service"` OR SOMETHING ELSE.
# YOUR ANSWER 3


Based on the information provided, you already have 4 snapshots listed. To create a new snapshot with a specific description, you should indeed use the following command:

```bash
sudo timeshift --create --comments "fixed mount_onedrive_mukesh259272.service"
```

Here's a breakdown of what this command will do:

- `sudo`: Runs the command with superuser privileges.
- `timeshift`: The main TimeShift command.
- `--create`: Tells TimeShift to create a new snapshot/backup.
- `--comments "fixed mount_onedrive_mukesh259272.service"`: Adds the specified description to the backup.

Using this command will create a new snapshot based on your current configuration and add the description "fixed mount_onedrive_mukesh 259272. Service" to it. The number of existing snapshots does not impact whether or not you can add comments; it only determines how many snapshots are currently being managed by TimeShift.

There is no need to modify or use any other commands unless you have specific requirements for the backup that need different options.

# QUESTION 4
DOES DELETING SNAPSHOTS REDUCES SPACE BY REMOVING THE FILES FROM THE TARGET DRIVE WHICH IS CHOOSEN FOR SNAPSHOT ?
# YOUR ANSWER 4

Yes, deleting snapshots using TimeShift will free up space on the target drive where the snapshots are stored. When you delete a snapshot, TimeShift removes the files associated with that snapshot from the backup location, thereby reducing the space used on that target drive.

Here's how it works:

1. **Snapshot Deletion**: When you delete a snapshot, TimeShift identifies and removes all the files and directories unique to that snapshot.
   
2. **Space Reclamation**: The removal of these files frees up disk space on the target drive. This is particularly important if you are running low on disk space or managing a limited storage environment.

To delete a snapshot from the command line, you can use:

```bash
sudo timeshift --delete --snapshot 'snapshot_name'
```

Replace `'snapshot_name'` with the actual name of the snapshot you wish to delete.

For example:

```bash
sudo timeshift --delete --snapshot '2024-07-29_21-56-41'
```

This command will remove the specified snapshot and free up the associated disk space on your backup target drive.


