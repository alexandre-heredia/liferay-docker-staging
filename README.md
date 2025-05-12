# Docker implementation of Remote Staging on Liferay

A Docker Compose environment to create a Remote Staging/Live scenario using Liferay DXP Quarterly Release images and MySQL database.

Because of the limitations of the environment, in order to this to work, the containers should have static IPs

You can change both DXP and MySQL versions editing the ```docker-compose.yaml file```

**Pre-requirements:**
Docker Engine or Docer Desktop installed

**Steps:**

1. On the root folder, run ```docker compose up --build -d```
2. PUB (Live): 
	- Control Panel - System Administration - API Authentication - Tunnel Authentication - /api/liferay/do - Allowed Hosts: 127.0.0.1,SERVER_IP,10.5.0.5,10.5.0.6
	- Left Menu - Configuration - Site Configurations - Platform - Site Configurations - Site URL - Virtual Host: pub

3. STG
	- Control Panel - System Administration - API Authentication - Tunnel Authentication - /api/liferay/do - Allowed Hosts: 127.0.0.1,SERVER_IP,10.5.0.5,10.5.0.6,pub
	- Left Menu - Publishing - Staging - Remote Live
	- Remote Server IP: pub
	- Remote port: 8080
	- Remote Site ID: 20117
