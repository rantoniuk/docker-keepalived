# Docker image containing Keepalived

Basic Docker image to run keepalived on host and set additional ip on interface 

To run docker in docker you must add this options:
- --net=host
- --cap-add=NET_ADMIN
- --name keepalived0 (optionally)

You need edit (add) this env:
- **VIP**: 192.168.1.177
- **MASK**: 27
- **ROUTERID**: Router1
- **VROUTERID**: 111
- **STATE**: Master
- **INTERFACE**: eno1
- **PRIORITY**: 100
- **ADVERT**: 1
- **AUTHPASS**: blah
- **SMTPSERV**: mail.test.com
- **NOTIFIEMAILFROM**: keepalived@mail.test.com
- **NOTIFIEMAILTO**: test@mail.test.com

Usage: 
```
docker run --net=host --cap-add=NET_ADMIN -e VIP=192.168.1.175 -e MASK=27 -e ROUTERID=Router1 -e VROUTERID=112 -e STATE=Master -e INTERFACE=eno1 -e PRIORITY=100 -e ADVERT=1 -e AUTHPASS=blah  -e SMTPSERV=mail.test.com -e NOTIFIEMAILFROM=keepalived@mail.test.com -e NOTIFIEMAILTO=test@mail.test.com --name keepalived0 -d  oberthur/docker-keepalived  
```


