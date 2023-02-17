# Nginx Location Protect

> Nginx Security by location, blocking uris what are used usually in attempts hacks

## Suggested use

Add a personalized log_format in http directive

```
log_format hacker '$remote_addr $request_method $request_uri [$time_local] $http_host $scheme $status - Referer: "$http_referer" UserAgent: $http_user_agent';
```

Add the file `/etc/nginx/security_action.conf` with the actions what you would like to do for location trackers

Some examples:

- Return Status 200 with a beautiful text

```
log_not_found off;
access_log /var/log/nginx/hackers.log hacker;
add_header Content-Type text/plain;
return 200 "Fck u hacker";
```

Install a crontab to get the automatic updates

```
0 0 * * * wget -O /etc/nginx/default.d/security.conf https://raw.githubusercontent.com/jysperu/nginx-location-protect/main/security.conf
```