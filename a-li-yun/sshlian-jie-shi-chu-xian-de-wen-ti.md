# SSH连接时出现的问题

<hr/>

## 1、问题1

```json
[root@cache001 swftools-0.9.0]# ssh 192.168.1.90
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that the RSA host key has just been changed.
The fingerprint for the RSA key sent by the remote host is
05:25:84:ea:dd:92:8d:80:ce:ad:5b:79:58:fe:c9:42.
Please contact your system administrator.
Add correct host key in /root/.ssh/known_hosts to get rid of this message.
Offending key in /root/.ssh/known_hosts:10
RSA host key for 192.168.1.90 has changed and you have requested strict checking.
Host key verification failed.
```

**解决方案**： `vi ~/.ssh/known_hosts`
