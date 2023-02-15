# Nginx Location Protect

> Nginx Security by location, blocking uris what are used usually in attempts hacks

## Suggested use

Add the log_format in http directive
```
log_format hacker '$remote_addr [$time_local] $http_host $request $status $scheme "$http_referer" $http_user_agent';
```

Install a crontab to get the automatic updates
