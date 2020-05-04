# yi-hack-support
This fork is a supporting script for whom using hacked rom of Xiaomi Yi Smart camera

(https://github.com/TheCrypt0/yi-hack-v4)

# How to use:
## upload_to_ftp.sh

Copy `sd/scripts/upload_to_ftp.sh` to folder `scripts/` on SD card

Open file `scripts/upload_to_ftp.sh` on SD card and change the FTP server configuration:
```
ftp_dir="/path/to/folder/on/ftp"
ftp_host="192.168.1.1"
ftp_port="21"
ftp_login="ftp_username"
ftp_pass="ftp_password"
```

## Start the setup

```
ssh root@<camera_ip>

# /tmp/sd/scripts/upload_to_ftp.sh setup
[.OK.] Create Log dir
[.OK.] Create mem file. Start upload videos of last 10 days
[.OK.] Create PID file
[....] Create cron job
[INFO] Try to add the cron
[INFO] After above done, let use "/tmp/sd/scripts/upload_to_ftp.sh status"
[.OK.]
```

## Check the status
```
ssh root@<camera_ip>
# /tmp/sd/scripts/upload_to_ftp.sh status
[.OK.] Check mem file
[.OK.] Check log directory
[.OK.] Check crond daemon
[.OK.] Check cron job existence
[.OK.] Check FTP server 192.168.1.1
```

## Extra config
This value in script can be edited to match the parent folder for cron.

```
yi_hack_dir="/home/yi-hack-v4/"
```

For the script the standard path for cron is:

```
$yi_hack_dir/etc/crontabs/root
```