openstack log colorizer
=======================

Very simple OPS tool to color and filter openstack's logs in your term.

Openstack's logs can be very verbose and parse a huge unicolor text bloc could be painful.

openstack log colorizer is a small script with "no depends" (just standard python libs like re) that provide :

  * Color log lines
  * Filter log by level


Quick setup
============

Just add the script in your path :
```
wget -O /usr/local/bin/openstack_log_colorizer https://raw.githubusercontent.com/gaelL/openstack-log-colorizer/master/openstack_log_colorizer
chmod +x /usr/local/bin/openstack_log_colorizer
```

Usage
======

Color log from a file :

```
openstack_log_colorizer < logfile
```

Color log from piped output like from tail :

```
tail -F logfile | openstack_log_colorizer
```

Screenshot
===========

![ScreenShot](https://raw.githubusercontent.com/gaelL/openstack-log-colorizer/master/screenshot/colored.png)
