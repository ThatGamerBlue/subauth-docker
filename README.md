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
- Fill out the env.json file in `webapp/env.json` according to the spec in the [server readme](https://github.com/ThatGamerBlue/subauth-server/blob/master/README.md)  

Minecraft Component:
- Build the [subauth-backend-plugin](https://github.com/ThatGamerBlue/subauth-backend-plugin) project  
- Put the resulting jar file in `minecraft/plugins/`  
- Grab the latest PaperMC from [their website](https://papermc.io)  
- Put the jar file in `minecraft/paper.jar`  
- Fill out the backend plugin config in `minecraft/plugins/SubAuth-Backend/config.yml` according to the [readme](https://github.com/ThatGamerBlue/subauth-backend-plugin/blob/master/README.md)  

Postgres Component:
- Set the postgres password in postgres.env  

Running:
- Run `docker compose up -d`  
The webapp service will be exposed on your machine's port 32400  
The minecraft service will be exposed on your machine's port 25565 