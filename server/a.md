# 1
~~~~
ssh my@192.168.1.2 "mkdir -pv /home/my/test"
~~~~

# 2

# 3

~~~~
#!/bin/sh

pname="sshd"  ## process server
msg="the msg here"
sub="the subject"
pid=`ps aux| grep $pname | grep -v grep | sed -n  '1P' | awk '{print $2}'`
if [ -z $pid ]; then
echo "$pname begin restart,please waiting..."
echo $msg | mail -s $sub jiangtao@tao-studio.net
sudo /etc/init.d/tomcat6 restart
exit 1
else
echo -e "$pname exist ,don't need restart"
fi

~~~~
