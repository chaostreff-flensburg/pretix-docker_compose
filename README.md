# pretix-docker_compose
A full config to run pretix with docker-compose

Create folderstructure
```
mkdir -p /mnt/docker/pretix/data
mkdir -p /mnt/docker/pretix/conf
chown -R 15371:15371 /mnt/docker/pretix/ 
mkdir -p /mnt/docker/pretix/mariadb
```

Put your config file for the pretix installation to 
```
/mnt/docker/pretix/conf/pretix.cfg
```

Than run the docker-compose file and create a new cronjob to run the internal pretix jobs.

```
15,45 * * * * /usr/bin/docker exec pretix_app pretix cron
```

After starting the stack navigate to:
https://pretix.yourdomain.com/control/

The default user is: admin@localhost

And the default password is: admin

Change this settings!