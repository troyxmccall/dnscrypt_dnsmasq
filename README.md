DNSMasq and DNSCrypt all in one, with OpenDNS
=====================

# PRE-REQUIREMENT

***[Docker-Compose](https://docs.docker.com/compose/)***

For ubuntu & Mac OSX

```bash
sudo pip -H install --upgrade docker-compose
```

# INSTALL

```bash
git clone https://github.com/thiswind/dnscrypt_dnsmasq.git

cd dnscrypt_dnsmasq

docker-compose up
```

Then you can point your dns server at 127.0.0.1 (or 192.168.1.33 for example)

```bash
$ dig google.com @192.168.99.100 -p 53

; <<>> DiG 9.8.3-P1 <<>> google.com @192.168.99.100 -p 53
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 50260
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;google.com.			IN	A

;; ANSWER SECTION:
google.com.		300	IN	A	216.58.221.78

;; Query time: 134 msec
;; SERVER: 192.168.99.100#53(192.168.99.100)
;; WHEN: Mon Aug 24 21:54:13 2015
;; MSG SIZE  rcvd: 55
```
