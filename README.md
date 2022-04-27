# Portainer-NGINX
Install portainer inside a NGINX container. 

## Original yml file

The file from which we derive
```{bash}
$> curl -L https://downloads.portainer.io/portainer-agent-stack.yml -o portainer-agent-stack.yml
```

## Steps

### Step 1: Create conf.d folder
Create a copy of the conf.d.example folder with the name conf.d in the same directory.

### Step 2: Configure your main domain in conf.d/site.conf
Basically, you need to change the example.com and www.example.com references to your domain.

### Step 3: Configure portainer domain under conf.d/portainer.conf file
Change the portainer.example.com references to your domain. Or adapt the file to your requirements.

### Step 4: Configure subdomains
Configure other subdomains in independent files with *.conf extension under the conf.d folder.

### Step 5: Configure environment variables
Create a copy of the .env-example file in the same directory with the name ".env". Set the variables values with your config.

### Step 6: Start docker stack
```{bash}
docker stack deploy --compose-file=portainer-agent-stack.yml portainer
```

### Step 7: Test certificate creation and update
Inspect if all configured certificates has been created correctly with the next command:
```{bash}
docker exec -it [NGINX_CONTAINER] certbot certificates
```

Execute manually the renewal process to check for errors:
```{bash}
docker exec -it [NGINX_CONTAINER] ./scripts/run_certbot.sh force
```

If you don't see any errors nginx and certbot is successfully installed and working!
