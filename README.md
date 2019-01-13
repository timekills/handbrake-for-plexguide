# handbrake-for-plexguide
Handbrake through web interface or VNC for PlexGuide deployment with Traefik integration and username/password security
Includes Intel QuickSync and multiple automatic presets based on folder.

# Usage:
Add to /mnt/handbrake/watch/Very_Fast_1080p30 folder for automatic 1080p AAC 2.0 MP4 (Very Fast)
Add to /mnt/handbrake/watch/HQ_1080p30_Surround folder for automatic HQ 1080p 5,1 MP4  (Slow)
Add to /mnt/handbrake/1080mkv folder for automatic 1080p AAC 2.0 MKV (Standard)

For Intel QuickSync, the host /dev/dri folder must exist, and you need to apply chmod -R 777 /dev/dri to change permission on the host /dev/dri folder

https://www.timekills.org/pg-apps/

# Username and password version (default username is plex and default password is guide)

# Instructions for automated install (instead of copy and paste into handbrake.yml) 

1. Go to the /opt/mycontainers directory (cd /opt/mycontainers)
2. Type the command: git init
3. Type the command: git remote add handbrake https://github.com/timekills/handbrake-for-plexguide.git
4. Type the command: git pull handbrake quicksync
5. rm -r .git
6. (Optional) rm -r README.md if you don't want the README file cluttering up your drectory
7. Run Plexguide

Deploy handbrake app like any other app (it will be in the core Box Apps folder if manually installed as above NOT the Community folder!)

Note the port for web use is 5800

# If you want to change the username/password from default plex/guide
1. go to --> http://www.htaccesstools.com/htpasswd-generator/ and create username/password pair. It will give you the plaintext username and hashed password
2. (example username test and password test will give you test:$apr1$n22fgswn$4Wu4q/Dzc7ACcgiLaoU5d/)
3. Edit the /opt/mycontainers/handbrake.yml file (eg. sudo nano /opt/mycontainers/handbrake.yml )
4. Replace the line traefik.frontend.auth.basic: "plex:$apr1$tosnCNtX$XKXnDaIiW7f0y1nwmd.KL0" with traefik.frontend.auth.basic: "yourNewUsername:YourNewHashedPassword."  Example traefik.frontend.auth.basic: "test:$apr1$n22fgswn$4Wu4q/Dzc7ACcgiLaoU5d/"
Go to plexguide and redeploy/reinstall handbrake
