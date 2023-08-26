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
#cp utils/redis_init_script /etc/init.d/redis_6379
#cp redis.conf /etc/redis/6379.conf
#mkdir /var/redis/6379
Edit the configuration file(/etc/redis/6379.conf), making sure to perform the following changes:

Set daemonize to yes (by default it is set to no).
Set the protected-mode no
Set bind ip from 127.0.0.1 to 0.0.0.0
Set the pidfile to /var/run/redis_6379.pid .
Set the logfile to /var/log/redis_6379.log
Set the dir to /var/redis/6379 (very important step!)


```

2. Update the BindIP from `127.0.0.1` to `0.0.0.0` in config file `/etc/redis/6379.conf`
3. add the new Redis init script to all the default runlevels using the following command
 
   update-rc.d redis_6379 defaults


4. Start Redis Database

```
# /etc/init.d/redis_6379 start

```

