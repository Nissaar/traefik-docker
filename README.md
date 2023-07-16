# Traefik
Traefik Docker-Compose setup
## Prerequisites
* Docker & Docker-Compose installed
* Docker Socket Proxy
### Create Network
#### Frontend
```bash
docker network create --driver=bridge -o "com.docker.network.bridge.name=frontend"  --subnet=172.18.2.0/24 --label docker.frontend frontend
```
#### Backend
```bash
docker network create --internal --driver=bridge -o "com.docker.network.bridge.name=backend" -o "com.docker.network.bridge.enable_ip_masquerade=false"  --subnet=172.18.3.0/24 --label docker.backend backend
```
### Authelia
The commented is if will be using `Authelia` with Traefik for SSO

#### Note 
* Email address should be set up for Certificate Resolver
* Change URL for Authelia if it is being used
