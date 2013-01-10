#!/usr/bin/env python
#
# Author: Grzegorz Wieczorek 2013
# Runs haproxy with multiple .cfg files

import sys,os
from subprocess import Popen, PIPE
  
p = Popen(['ls', '/etc/haproxy/conf.d/'], stdout=PIPE, stderr=PIPE, stdin=PIPE)
output = p.stdout.readlines()
params = ""
for i in output:
	k = i.split(".cfg")
	if len(k) > 1:
		params += " -f /etc/haproxy/conf.d/" + i[:-1]


cmd = "/usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg" + params + " -p /var/run/haproxy.pid -D"
print cmd
os.system(cmd)
