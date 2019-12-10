## 一、华为交换机的配置

# 1、telnet的配置
```shell
stelnet server enable
telnet server enable

aaa
local-user admin password irreversible-cipher your_admin_pass
local-user admin service-type ssh telnet terminal http
local-user admin privilege level 15
quit

user-interface vty 0 4
 authentication-mode aaa
 protocol inbound all
 idle-timeout 35791
``` 
# 2、ssh 登录配置
```shell
 rsa local-key-pair create
 ssh user huawei authentication-type password your_admin_pass
 ssh user huawei service-type stelnet
 q
 save
```
 
# 3、Console 配置
```shell
user-interface console 0
authentication-mode aaa
quit
aaa
local-user admin password irreversible-cipher your_admin_pass
local-user admin service-type ssh telnet terminal http
return
save
```
