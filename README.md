# bosh-nginx

Simple Bosh release for Nginx

1 - Configure Bosh CLI v2

2 - Install Bosh lite on VirtualBox

3 - Upload Stemcell for ubuntu
```bash
bosh -e vbox us https://s3.amazonaws.com/bosh-core-stemcells/warden/bosh-stemcell-3468-warden-boshlite-ubuntu-trusty-go_agent.tgz
```
4 - Clone repository
```bash
git clone https://github.com/bila-olavo/bosh-nginx
```
5 - Upload release to Bosh directory
```bash
bosh -e vbox ur https://github.com/cloudfoundry-community/nginx-release/releases/download/1.13.12/nginx-release-1.13.12.tgz
```
5 - Deploy Simple Nginx with BasicAuth ( admin / avarteq;123 )

```bash
bosh -e vbox -d nginx deploy nginx.yml
```
