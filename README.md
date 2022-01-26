# Portainer-NGINX
Install portainer inside a NGINX container. 

## Original yml file

The file from which we derive
```{bash}
$> curl -L https://downloads.portainer.io/portainer-agent-stack.yml -o portainer-agent-stack.yml
```

## Steps

### Step 1: Configure your main domain in conf.d/site.conf
Basically, you need to change the example.com references to your domain.

### Step 2: Configure portainer domain under conf.d/portainer.conf file
Change the portainer.example.com references to your domain. Or adapt the file to your requirements.

### Step 3: Configure subdomains
Configure other subdomains in independent files with *.conf extension under the conf.d folder.

### Step 4: Start docker stack
```{bash}
docker stack deploy --compose-file=portainer-agent-stack.yml portainer
```
