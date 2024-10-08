# vee-cord
Simple Script to get Discord webhook messages from the Free Veeam Agent for Linux

This script is heavily based on [vee-mail](https://github.com/grufocom/vee-mail) by [grufocom](https://github.com/grufocom/)

vee-cord uses the sqlite database which get's filled from Veeam Agent for Linux Free in /var/lib/veeam/veeam_db.sqlite.
The Linux version from Veeam Agent does not send notification e-mails like the windows version.
So this script reads the data from the sqlite database and sends it over discord to you.

![Example Image](https://github.com/ErdbeerbaerLP/vee-cord/assets/27149563/c2b819cc-4bdc-406f-919f-bb0dc1e5fc9c)

# Dependencies

veeam  
sqlite3 (>= 3.7.0)  
curl 

Webhook POST Requests are done using curl, so curl is necessary here

# Install

- `git clone https://github.com/ErdbeerbaerLP/vee-cord`
- move the directory "vee-cord" to /opt or any other directory you would like to install it into
- change `vee-cord.config` file to your needs.
- `chmod +x vee-cord.sh`

# Use

You can use the vee-cord script as a post-backup script directly in veeam (Configure - select Job, Advanced/Scripts/Post-Job) or start it manualy after the veeam backup has run:

/opt/vee-cord/vee-cord.sh

If you want to use it in an custom post-backup script, make the script run /opt/vee-cord/vee-cord.sh --custom_script_veeam_override

# Release notes

## Version 0.0.2
- Fix a few bugs
- Add --custom_script_veeam_override parameter
## Version 0.0.2
- Added more embed elements

## Version 0.0.1
- Initial release
