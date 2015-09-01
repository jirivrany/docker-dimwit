dimwit
======

Dynamic Image Manipulation Service with Nginx

Forked from (https://github.com/asgoodasnu/docker-dimwit)

With proxy_pass_request_headers  on;

Features
=========
Uses the [HttpImageFilterModule](http://wiki.nginx.org/HttpImageFilterModule) to dynamically process remote images into cropped, rotated and resized derivatives based on remote source images.
Derivative images are created only once per unique url and stored locally.  Duplicate requests are served directly from disk.

Setup
=====
Build and run
```
docker build -t dimwit .
docker run -d -p 80:80 dimwit
```

Usage
=======
```
# resize example
http://<dims-host>/resize/100x100/http://2.bp.blogspot.com/_nm9ySucveA8/TEYgGu9DIgI/AAAAAAAAAO4/XI1q38FFlxw/s1600/unicorns2q.jpg

# crop example
http://<dims-host>/crop/200x200/http://4.bp.blogspot.com/_nm9ySucveA8/TEYgGSJi7sI/AAAAAAAAAOw/XK4VjrHPybw/s1600/unicorns-5-magical-animal.jpg

# rotate example
http://<dims-host>/rotate/90/http://3.bp.blogspot.com/_nm9ySucveA8/TEYgGF9iEWI/AAAAAAAAAOo/uC62nczWcEk/s1600/unicorn1.jpg
```
