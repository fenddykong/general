Slack integration with Sentinl
============

This is continuation after you install Sentinl plugin to Kibana.

Step by step:

 1. Add config to kibana.yml
 2. Restart Kibana service
 3. Configure watcher in Sentinl

**1. Add config to kibana.yml**
------------
Add below setting to your .yml file, make sure that the spacing is correct.
~~~
sentinl:
  settings:
    slack:
      active: true
      username: 'Username Foo'
      hook: 'https://hooks.slack.com/services/Txxxxxxxx/Bxxxxxxxx/3xxxxxxxxxxxxxxxxxxxxxxxx'
~~~
[Reference to above code](https://github.com/sirensolutions/sentinl/issues/432)

*Example of accessing kibana.yml with elk in docker*
~~~
docker>docker exec -it docker_elk_1 /bin/bash
root@a123456789:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@a123456789:/# cd opt/kibana/config/
root@a123456789:/opt/kibana/config# vi kibana.yml
~~~

**2. Restart Kibana service**
------------
Restart Kibana service with below command
~~~
service restart kibana
~~~

**3. Configure watcher in Sentinl**
------------
*Continue setting your watcher with `Actions +slack`*