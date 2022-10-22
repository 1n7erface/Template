<h1 align="center">RequestTemplate</h1>

English | [中文文档](https://github.com/1n7erface/RequestTemplate/blob/main/README_CN.md)
## Always believe that code makes a difference, good projects always need to give users time to discover...

![](https://img.shields.io/badge/KCon-%E5%85%B5%E5%99%A8%E8%B0%B1-red)
![](https://img.shields.io/badge/ReaTeam-%E6%AD%A6%E5%99%A8%E5%BA%93-red) ![](https://img.shields.io/badge/version-1.0.6-brightgreen) ![](https://img.shields.io/badge/author-1n7erface-blueviolet)


# 0x00 Tool introduction

RequestTemplate is a red team penetration tool for both ends and a self inspection tool for Party A. It plays an irreplaceable role in the process of Intranet penetration. The scanning end is made of golang with its exquisite and fast features, which can quickly find a weak link in the intranet. The reproduction end is made of java with its characteristics of ecological stability, cross platform and beautiful UI. The minimum contract amount and the integration verification of the platform are fragile.

# 0x01 Application scenarios
- The internal net weapon of the red team in the red blue confrontation
- Party A's assistant for self inspection of Intranet during construction

# 0x02 Features

- Network segment detection: detects the connected network segment of the current machine
- Horizontal movement: various weak password blasting modules can be accessed through config JSON configuration
- Web scanning: integrating more than 300 kinds of POC detection of Xray
- Vulnerability verification: use the Java side configuration agent to verify the screenshot of the replication of the scanning results

# 0x03 RequestTemplate Client Usage

```bash
root@VM-4-13-ubuntu:~# ./App_darwin -h

 _____                    _       _
|_   _|                  | |     | |
  | | ___ _ __ ___  _ __ | | __ _| |_ ___
  | |/ _ \ '_'  _ \| '_ \| |/ _' | __/ _ \
  | |  __/ | | | | | |_) | | (_| | ||  __/
  \_/\___|_| |_| |_| .__/|_|\__,_|\__\___|
                   | |  by 1n7erface
                   |_|
Usage of ./App_darwin:
  -a string
    	auto check network conn (default "false")
  -b string
    	only brute , not webscan (default "false")
  -c string
    	auto check 192 or 172 or 10
  -e string
    	print error log (default "false")
  -i string
    	IP address of the host you want to scan,for example: 192.168.11.11-255 or 192.168.1.1/24 or /22 /15...
  
```
# 0x04 RequestTemplate Client param explain

- -a true :It will only detect the connectivity of the network segment. The detection includes 10.1.1.1-10.255.255.255 and 192.168.1.1-192.168.255.255 and 172.16.1.1-172.31.255.255

- -b true :By default, the scanning terminal will scan for web vulnerabilities and blast weak passwords. If you need to perform frequent tests on the collected passwords, add this parameter

- -c 192 or 172 or 10 :Test the connectivity of 10.1.1.1-10.255.255.255 and 192.168.1.1-192.168.255.255 and 172.16.1.1-172.31.255.255, and perform vulnerability scanning and service password blasting after the test

- -e true :By default, the scanning end will only print the information about the vulnerability of the surviving IP surviving port. In addition, this parameter can output the detection information, which is usually used for error debugging.

- -i CIDR :This parameter supports CIDR expressions of IP addresses, but if you scan 10/16/8, 192/16/8, 172/16/8, it is recommended to use the -c parameter. This parameter is most commonly used for /24

- The difference between -i and -c: The -c parameter will detect the connectivity of the network segment, and scan after the detection. And -i scans directly

# 0x05 RequestTemplate Server Usage (need JDK1.8)

```bash
root@VM-4-13-ubuntu:~# java -jar RequestTemplate.jar 
 _____                    _       _       
|_   _|                  | |     | |      
  | | ___ _ __ ___  _ __ | | __ _| |_ ___ 
  | |/ _ \ '_' _  \| '_ \| |/ _' | __/ _ \
  | |  __/ | | | | | |_) | | (_| | ||  __/
  \_/\___|_| |_| |_| .__/|_|\__,_|\__\___|
                   | |  by 1n7erface
                   |_|
Opened database successfully

```
# 0x06 RequestTemplate Server param explain

- Agent management
<img width="799" alt="image" src="https://user-images.githubusercontent.com/52184829/174012441-a675348b-e3fd-45de-ad7f-da2b0aa57ec3.png">

- Target management
<img width="796" alt="image" src="https://user-images.githubusercontent.com/52184829/174012776-6fc00c43-0357-4b8f-9353-a4cb657ecacd.png">

- Exploit
<img width="794" alt="image" src="https://user-images.githubusercontent.com/52184829/174012945-4c3b1c10-0b4e-44e1-8964-b38189ef3d4e.png">

# 0x07 config.json param explain

<img width="600" alt="image" src="https://user-images.githubusercontent.com/52184829/174014625-831f94ce-cfb6-4800-889c-771df224abd4.png">

- Place config.json in the same directory as the scanning end, and you can add the dictionary and port of the scanning end
- Note: The program comes with a simple dictionary and port by default. To add an account password, you only need to add the complex password collected from the information. The port should exclude the following default ports for adding.

``` shell
Ports = []int{21, 22, 23, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 98, 99, 135, 139, 443, 445, 800, 801, 808, 880, 888, 889, 1000, 1010, 1080, 1081, 1082, 1118, 1433, 1521, 1888, 2008, 2020, 2100, 2375, 2379, 3000, 3008, 3128, 3306, 3505, 5432, 5555, 6080, 6379, 6648, 6868, 7000, 7001, 7002, 7003, 7004, 7005, 7007, 7008, 7070, 7071, 7074, 7078, 7080, 7088, 7200, 7680, 7687, 7688, 7777, 7890, 8000, 8001, 8002, 8003, 8004, 8006, 8008, 8009, 8010, 8011, 8012, 8016, 8018, 8020, 8028, 8030, 8038, 8042, 8044, 8046, 8048, 8053, 8060, 8069, 8070, 8080, 8081, 8082, 8083, 8084, 8085, 8086, 8087, 8088, 8089, 8090, 8091, 8092, 8093, 8094, 8095, 8096, 8097, 8098, 8099, 8100, 8101, 8108, 8118, 8161, 8172, 8180, 8181, 8200, 8222, 8244, 8258, 8280, 8288, 8300, 8360, 8443, 8448, 8484, 8800, 8834, 8838, 8848, 8858, 8868, 8879, 8880, 8881, 8888, 8899, 8983, 8989, 9000, 9001, 9002, 9008, 9010, 9043, 9060, 9080, 9081, 9082, 9083, 9084, 9085, 9086, 9087, 9088, 9089, 9090, 9091, 9092, 9093, 9094, 9095, 9096, 9097, 9098, 9099, 9100, 9200, 9443, 9448, 9800, 9981, 9986, 9988, 9998, 9999, 10000, 10001, 10002, 10004, 10008, 10010, 10250, 11211, 12018, 12443, 14000, 16080, 18000, 18001, 18002, 18004, 18008, 18080, 18082, 18088, 18090, 18098, 19001, 20000, 20720, 21000, 21501, 21502, 27017, 28018, 20880}
```

# 0x07 Thanks

Thanks to @shadow1ng for answering the questions on the scanning side.
https://github.com/shadow1ng/fscan

Thanks to @j1anFen's project for the reference to the reproducible end.
https://github.com/SafeGroceryStore/MDUT

