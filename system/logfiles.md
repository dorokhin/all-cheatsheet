# How to monitor log-files in real time:

```sh
less +F /var/log/log_name.log
# or
tail -f /var/log/log_name.log
```


### The `tail -F` will keep track if new log file being created and will start following the new file instead of the old file.
```sh
tail -F /var/log/log_name.log
```
