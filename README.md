# SubAuth Dockerization
Prerequisites
---
You need a machine with docker installed and set up

Usage
---
Clone this repository to a folder on your machine  

WebApp Component:  
- Build the [subauth-server](https://github.com/ThatGamerBlue/subauth-server) project  
- Put the resulting jar file in `webapp/subauth.jar`  
- Copy `webapp/env.example.json` to `webapp/env.json` and fill it out according to the spec in the [server readme](https://github.com/ThatGamerBlue/subauth-server/blob/master/README.md)  

Minecraft Component:
- Build the [subauth-backend-plugin](https://github.com/ThatGamerBlue/subauth-backend-plugin) project  
- Put the resulting jar file in `minecraft/plugins/`  
- Grab the latest PaperMC from [their website](https://papermc.io)  
- Put the jar file in `minecraft/paper.jar`  
- Copy `minecraft/plugins/SubAuth-Backend/config.example.yml` to `minecraft/plugins/SubAuth-Backend/config.yml` and fill it out according to the [readme](https://github.com/ThatGamerBlue/subauth-backend-plugin/blob/master/README.md)  
- Install the latest versions of ViaVersion and ViaBackwards.  

Postgres Component:
- Copy `postgres.example.env` to `postgres.env` and set the postgres password inside 
- This compose file comes with adminer pre-installed. It will be exposed on your machine's port 32500 by default, but only on interface 127.0.0.1.

Running:
- Run `docker compose up -d`  
- The webapp service will be exposed on your machine's port 32400, but only on interface 127.0.0.1. Make sure you place it behind a reverse proxy of some sort to provide SSL encryption and public access.  
- The minecraft service will be exposed on your machine's port 32401. This is publically accessible by default, if you wish to proxy it via bungee or similar, add `127.0.0.1:` before the port in the `docker-compose.yml`, and configure bungee to connect to the server on the port.  
- The adminer service will be exposed on your machine's port 32500, but only on interface 127.0.0.1. You can either place it behind a reverse proxy with appropriate security settings, or leave it as default to access the service only from the machine it's running on.