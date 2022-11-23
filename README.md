# Linux_learn_iptables
防火牆設定 iptables

- 參考 :
    
* (https://www.cyberciti.biz/faq/linux-disable-firewall-command/)
    
* [iptables 指令入門 - Linux 技術手札](https://www.ltsplus.com/linux/iptables-command)
    
* [Linux的iptables防火牆設定記事](https://blog.pulipuli.info/2011/07/linuxiptables.html)
    
* [iptables 的安裝與設定](http://120.105.184.250/cswang/thit/Linux/iptables.htm)
    
* [iptables實用知識 ，一文學會配置linux防火牆](https://iter01.com/525635.html)
    
* [CentOS 7 關閉防火牆及 SELinux - Linux 技術手札](https://www.ltsplus.com/linux/centos-7-disable-firewalld-selinux)
    
* [What can be the reasons of connection refused errors?](https://stackoverflow.com/questions/2333400/what-can-be-the-reasons-of-connection-refused-errors)
    
* [https://www.quora.com/How-do-you-open-port-80-on-Linux](https://www.quora.com/How-do-you-open-port-80-on-Linux)

```
iptables
可以設定主機 ip 白名單與黑名單
限制來源提升安全性
port 也可以做設定
```

查看 : iptables -L
---

規則 先後順序 : 先設定有優先級
---

範例 : 先開通 10.40.40.20 port 80 ， 在封鎖 10.40.40.20 網段

10.40.40.20 port 80 還是可以通

先封鎖 10.40.40.20 網段 ， 在開通 port 80

10.40.40.20 port 80 被擋住

設定 : 
---

開啟 22 port : 

`iptables -A INPUT -i ens192 -p tcp -s 10.40.53.191 --dport 22 -j ACCEPT`

開通

測試可以直接輸入指令 不用重啟防火牆

process 沒有 pid
---

參考 : 

* [How to identify a process which has no pid?](https://unix.stackexchange.com/questions/97752/how-to-identify-a-process-which-has-no-pid)

`netstat -antlp | grep 45136`

`ss -apn|grep :111`

`netstat --program --numeric-hosts --numeric-ports --extend`

`find -inum 152555007`

