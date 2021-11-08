## Original file from

```{bash}
$> curl -L https://downloads.portainer.io/portainer-agent-stack.yml -o portainer-agent-stack.yml
```
## Steps

### 1 - Define your sites-available files

### 2 - Define your snippets files
Download the script to your working directory as init-letsencrypt.sh:
```{bash}
curl -L https://raw.githubusercontent.com/wmnnd/nginx-certbot/master/init-letsencrypt.sh > init-letsencrypt.sh
```

### N - Start server
```{bash}
docker stack deploy --compose-file=portainer-agent-stack.yml portainer
```
