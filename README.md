1，Docker 创建网络：  
docker network create --subnet=172.18.10.0/24 --gateway 172.18.10.1 MyNET

2，部署固定IP的 ADGuard Home1：  
docker run -d --name AdGuard-Home1 -v /opt/docker/AGH_Docker1:/opt/adguardhome/work -v /opt/docker/AGH_Docker1:/opt/adguardhome/conf -p 3002:3000 --restart always --net MyNET --ip 172.18.10.2 adguard/adguardhome:latest

3，部署固定IP的 ADGuard Home2：  
docker run -d --name AdGuard-Home2 -v /opt/docker/AGH_Docker2:/opt/adguardhome/work -v /opt/docker/AGH_Docker2:/opt/adguardhome/conf -p 3003:3000 --restart always --net MyNET --ip 172.18.10.3 adguard/adguardhome:latest

4，国外DNS：  
https://dns.google/dns-query  
https://cloudflare-dns.com/dns-query  
https://doh.opendns.com/dns-query  
https://dns.quad9.net/dns-query
