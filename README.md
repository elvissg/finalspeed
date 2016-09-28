# finalspeed
finalspeed
服务器TCP双边加速软件可达到90%的物理带宽利用率


安装脚本：

rm -f install_fs.sh
wget https://raw.githubusercontent.com/leesiyang/finalspeed/master/install_fs.sh
chmod +x install_fs.sh
./install_fs.sh 2>&1 | tee install.log

FinalSpeed介绍、服务端、客户端安装部署（完整说明）
http://www.168520.com/software/finalspeed-server-client.html


---


命令行客户端使用方法：`sudo java -jar client.jar`。如果在 Windows 下，则需要使用管理员运行。

配置文件 - clien_config.json
```
{
    // 下载速度，单位是 B，字节。这里换算起来就是 11MB。请把这里改成本机的下载速度
    "download_speed": 11200698, 
    // 协议：tcp 或 udp。注意：服务端如果是 OpenVZ 架构的话，则只支持 udp。
    "protocal": "udp", 
    // 服务器地址
    "server_address": "1.2.3.4", 
    // 一般不需要更改，保持默认即可。
    "server_port": 150, 
    // 不需要更改，保持默认即可。
    "socks5_port": 1083, 
    // 上传速度，单位是 B，字节。
    "upload_speed": 357469
}
```

配置文件 - port_map.json
```
{
    "map_list": [
        {
            // 要加速的服务器端口
            "dst_port": 12345, 
            // 本地端口
            "listen_port": 1099, 
            // 备注信息
            "name": "ss"
        }, 
        {
            "dst_port": 23456, 
            "listen_port": 2200, 
            "name": "ssh"
        }
    ]
}
```
