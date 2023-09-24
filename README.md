<table align="center"><tr><td align="center" width="9999">
<img src="icons/docker_k8s.png" align="center" width="200" alt="Docker K8s icon">

# cloudlab

</td></tr></table>

Docker compose files for setting up a small home cloud lab including various applications:
* Docker Registry witht Craneoperator
* Portainer for Docker Swarm
* Traefik


# Traefik proxy installation
Install Traefik first as it will be used as reverse proxy for the UI of our deployed docker services.
```
cd docker-traefik && docker stack deploy --compose-file docker-compose.yml traefik
```

# Docker registry installation
Install (insecure) private docker registry with Crane Operator as UI:
```
cd docker-registry && docker stack deploy --compose-file docker-compose.yml docker-registry
```

# Portainer installation
Install Portainer CE:
```
cd docker-portainer && docker stack deploy --compose-file <(docker-compose --env-file .env_portainer_agent config) portainer
```
