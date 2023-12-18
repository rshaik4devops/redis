# REDIS

Redis is used for in-memory data storage and allows users to access the data over API. 

## Manual Installation of Redis.

1. Install Redis.

```
#yum install gcc make
#cd /opt
#wget https://download.redis.io/redis-stable.tar.gz
#tar -xzvf redis-stable.tar.gz
#cd redis-stable
#make
#make install
#mkdir /etc/redis
#mkdir /var/redis

#cp redis.conf /etc/redis/redis.conf
#mkdir -p /var/lib/redis/
Edit the configuration file(/etc/redis/redis.conf), making sure to perform the following changes:


Set the protected-mode no
Set bind ip from 127.0.0.1 to 0.0.0.0
Set the pidfile to /var/run/redis_6379.pid 
Set the logfile to /var/log/redis_6379.log
Set the dir to /var/lib/redis (very important step!)


```




2. Start Redis Database

```
Create a redis.service file under /etc/systemd/system then add the below content in the file  and save the file.

[Unit]
Description=Redis
After=syslog.target

[Service]
ExecStart=/usr/local/bin/redis-server /etc/redis/redis.conf
RestartSec=5s
Restart=on-success

[Install]
WantedBy=multi-user.target

3. Start the servie 

# systemctl enable redis.service
# systemctl start redis

```

