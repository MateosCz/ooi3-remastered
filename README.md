![Header](https://raw.githubusercontent.com/EnderQIU/ooi3-remastered/4.2.0.2/static/img/logo.png)
# OOI v3 Remastered
Online Objects Integration (OOI) system based on flask & requests.

## Features
1. Updated various of python packages.
2. Flask-caching static files with redis.
3. HTTPS Supported.
4. Running in 2nd Sequence (HTML5 game mode).

## 4.2.0.2 Branch
This branch use API version 4.2.0.2 and its default iframe plugin is html5 which is 
supported by all modern desktop and mobile devices. Since its a new API version, I'm quite
not sure what would happen under it. Any issue or pull requests are welcomed.

## Demo Website
You can visit this [demo website](http://ooi.enderqiu.cn/) with part of features except HTTPS.
We highly recommend you deploy this site on the VPS owned by yourself with HTTPS if you are worried
aboute some security problems.
~~The real reason is the demo site uses CDN to accelerate traffic which can incur a high cost.~~

## Dependency
- The memory is suggested to be higher than 512MB if you switch on the Redis-File-Cache.
- Ubuntu 16.04 with bbr. (Recommend, other OS is ok. BBR can show a better traffic performance.)
- Nginx
- Supervisor
- uwsgi
- python 3.5 or higher

## Deploy
Please refer to the config files in the `doc/` directory.

## Trouble Shooter
1. Q: Any *Permission Denied* error:

A: `chown -R www-data:www-data /srv/ooi3-remastered/`

2. Q: Got `local.Error: unsupported locale setting`:

A: `export LC_ALL=C`

3. Q: How to use proxy?

A: Set the environment variables: `HTTP_PROXY` or `HTTPS_PROXY` e.g. `export HTTP_PROXY="http://127.0.0.1:1087`.

4. Q: No data caught by POI when start in POI mode using HTTPS?

A: Don't forcefully redirect HTTP to HTTPS because POI can't catch HTTPS data.
