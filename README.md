# Portainer-NGINX
Install portainer inside a NGINX container. 

## Original yml file

The file from which we derive
```{bash}
$> curl -L https://downloads.portainer.io/portainer-agent-stack.yml -o portainer-agent-stack.yml
```

## Steps

### Step 1: Configure your server in conf.d/site.conf
Basically, you need to change the example.robotbas.com references to your domain.

### Ste 2 - Start docker stack
```{bash}
docker stack deploy --compose-file=portainer-agent-stack.yml portainer
```
