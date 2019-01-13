# handbrake-for-plexguide
Handbrake through web interface or VNC for PlexGuide deployment with Traefik integration and Google OAuth security

https://www.timekills.org/pg-apps/

# Google OAuth version (master branch)


#Instructions for a more automated (instead of copy and paste into handbrake.yml) approach

1. Go to the /opt/mycontainers directory (cd /opt/mycontainers)
2. Type the command: git init
3. Type the command: git remote add handbrake https://github.com/timekills/handbrake-for-plexguide.git
4. Type the command: git pull handbrake master
5. rm -r .git
6. (Optional) rm -r README.md if you don't want the README file cluttering up your drectory
7. Run Plexguide

Deploy handbrake app like any other app

Note the port for web use is 5800
