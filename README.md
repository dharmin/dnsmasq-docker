# dnsmasq-docker

`dnsmasq-docker` is the simplest and smallest dnsmasq docker container.

### Useage

```sh
$ docker run \
    --name dnsmasq \
    -d \
    -p 53:53/udp \
    -v /home/dharmin/dnsmasq/confs:/etc/dnsmasq.d \
    --restart always \
    dharmin/dnsmasq
```

Now create configs in mounted volume directory; In my case `/home/dharmin/dnsmasq/confs`

```sh
$ cd /home/dharmin/dnsmasq/confs
$ echo "address=/example.com/192.168.0.164" > example.com.conf
```

Now test,
```sh
$ nslookup example.com 127.0.0.1
Server:		127.0.0.1
Address:	127.0.0.1#53

Name:	example.com
Address: 127.0.0.1
```
