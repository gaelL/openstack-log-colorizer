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

Basic usage
============

Color log from a file :

```
openstack_log_colorizer < logfile
```

Color log from piped output like from tail :

```
tail -F logfile | openstack_log_colorizer
```

Filter usage
=============

```
usage: openstack_log_colorizer [-h] [-l level] [-e level [level ...]]
                               [-i level [level ...]]

optional arguments:
  -h, --help            show this help message and exit
  -l level, --level level
                        Set log level you want display
  -e level [level ...], --exclude level [level ...]
                        Set log level you want exclude
  -i level [level ...], --include level [level ...]
                        Set log level you only want display
```

You can play with 3 filter feature (level, include, exclude) :

  * All features are not case sensitive
  * By default if log line can't be parsed, the log line is displayed. Whatever options you have used.

**Log level filter** : Display log line with log level greater than or equal to that given log level. (log priority could be found in `LOG_LEVEL` variable.

```
cat log.sample | openstack_log_colorizer --level warning
```

**Include only log level filter** : Display log line with level included in your level list (example with error and trace).

```
cat log.sample | openstack_log_colorizer --include error TRACE
```

**Exclude log level filter** : Don't display log line in your exclude list (example with info and warning).

```
cat log.sample | openstack_log_colorizer --exclude INFO warning
```

Screenshot
===========

![ScreenShot](https://raw.githubusercontent.com/gaelL/openstack-log-colorizer/master/screenshot/colored.png)
