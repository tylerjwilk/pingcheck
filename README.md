# pingcheck
bash script tool to monitor a network ip and alert when host is unreachable

## Usage
```
Usage: ./pingcheck [network ip address] [network nickname]
Example: ./pingcheck 192.168.1.1 Home"
```

## Cron
You need to run the following commands to enable cron to launch a gui tool (notify-send). These will add localhost to the access control list, then enable the access control we created

```
$ xhost +local:
$ xhost
```


The we need to update cron for the user this will run under

```
$cron -e -u username
```


Add this to your cron file
```
* * * * * env DISPLAY=:0.0 /home/username/bin/pingcheck 192.168.1.1 HomeRouter 2>&1
```
