---
layout: post
title: "防火墙NAT映射FTP服务器到公网"
date:   2020-03-14 12:57:00 +0800
categories: [network]
---   
* any list
{:toc}

### FTP服务器映射需求  
　　公司项目需求FTP服务器要映射到公网访问，外网映射使用非默认端口(21)8245,防火墙配置了域间策略和NAT端口映射，还是提示无法访问，但内网访问正常，外网访问提示没有权限。  
![](/static/img/posts/fw_ftp_port/fw_ftp_port01.png)
### 原因分析  
* 20端口，数据连接端口  
* 21端口，控制连接端口  
内网21端口映射到公网端口为8245后，公网连接其实只是使用到了8245端口，数据传输端口，并没有映射出去，所以没有数据传输，所以会报错。  
<div align="center">
　　<img src="/static/img/posts/fw_ftp_port/fw_ftp_port02.png" height="295" width="613" />  
</div>
### `完整配置命令`

```bash
#NAT端口上配置内网映射成公网
[fw-GigabitEthernet2/3/1]nat server protocol tcp global 121.9.2.246 8245 inside 10.0.3.9 21
#开启指定或所有协议类型的NAT ALG功能(ALG（Application Level Gateway，应用层网关)
[fw]port-mapping application ftp port 8245
#port-mapping：用来配置通用端口映射(指定端口映射的应用层协议，名称必须标准且能够被设备识别，不区分大小写）
[fw]nat alg ftp  
#通常情况下，NAT只对报文头中的IP地址和端口信息进行转换，不对应用层数据载荷中的字段进行分析和处理。然而对于一些应用层协议，它们的报文的数据载荷中可能包含IP地址或端口信息，这些载荷信息也必须进行有效的转换，否则可能导致功能不正常。
例如，FTP应用由数据连接和控制连接共同完成，而数据连接使用的地址和端口由控制连接协商报文中的载荷信息决定，这就需要ALG利用NAT的相关转换配置来完成载荷信息的转换，以保证后续数据连接的正确建立。
```
<div align="center">
　　<img src="/static/img/posts/fw_ftp_port/fw_ftp_port03.png" height="523" width="450" />  
</div>
转载请注明：[20.Cent的博客](https://www.20cent.cn) » [防火墙NAT映射FTP服务器到公网](https://www.20cent.cn/2020/03/fw_ftp_port)    
