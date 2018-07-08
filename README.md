# bosh-nginx

Simple Bosh release for Nginx

#### Step by Step ####

----

1 - Configure Bosh CLI v2

2 - Install Bosh lite on VirtualBox

3 - Preparing your Private Cloud
```bash
bosh -e vbox update-cloud-config ~/projects/avarteq/bosh-deployment/warden/cloud-config.yml
```
4 - Upload stemcells
```bash
bosh -e vbox upload-stemcell https://bosh.io/d/stemcells/bosh-warden-boshlite-ubuntu-trusty-go_agent?v=3586.24  --sha1 32c1e09391d509d24026e55555df07a166f8b8eb
```
5 - Upload release NGINX
```bash
bosh -e vbox ur https://github.com/cloudfoundry-community/nginx-release/releases/download/1.13.12/nginx-release-1.13.12.tgz
```

6 - Clone Respository
```bash
git clone https://github.com/bila-olavo/bosh-nginx
```

7 - Deploy Simple Nginx with BasicAuth ( admin / avarteq;123 )

```bash
bosh -e vbox -d nginx deploy nginx.yml
```

8 - Check your machine routes. Eg. Linux Ubuntu 16.04 latest
```bash
sudo ip route add   10.244.0.0/16 via 192.168.50.6
```
9 - Browse to <http://10.244.0.34/>;
