# docs
Technologies used for unihack hackaton.

# Drone/Robot smart trash collector / tree land clearing

## Backend
### People
* Dani ( CI, Spring -> manage and persist data)
* Paul ( aiohttp -> streaming & live data)
* Sebi ( Image recognition) 
### Tech
* Spring  
* AWS EC2
* CI with git and EC2
* Relational Database (Drones/Robots, Coordonates + Photos, Users) 

## Web
### People
* Stefan ( Angular -> frontend)
* Sebi ( Angular -> frontend support)
### Tech
* Angular

## Mobile (optional)
* Android Studio 
* Ionic

## Flow 
### Nodes:
* backend_1: aiohttp python streaming service
* backend_2: aiohttp python Image recognition service & drone commands service
* backend_persist: spring persist data service

* streaming (admin) : 
    - connection_flow: frontend -> backend_1 -> token backend_persist -> if OK start coonection frontend<->backend_1 
    - data_flow: drone -> websocket_1 backend_1 -> frontend
* live data(coord, img):
    - connection_flow: frontend -> backend_2 -> start connection
    - data_flow: drone -> backend_2 -> Image Recognition -> if OK http request to backend_persist & (websocket_2 -> frontend)
    
* drone commands (admin): frontend http request -> backend_2 -> backend_persist token validation (persist in memory of backend_2) -> if OK drone command  

* spring admin user for: streaming, commands, clean zone validation


## Extras 
* normal users for score rewarding, notifications and extra security
* vocal instructions
* mobile app

# HR BOT

## Flow
* start: configuration -> linked in API for members -> start chat
* chat: bot preprocessing -> bot starts chat -> user input for ANN -> refresh ANN -> bot responds -> go to user input for ANN until END 

## Frontend
#### for configurations
* Angular

## Backend
#### for complex processing
* aws lambda functions

## Chat bot ANN
* https://www.luis.ai/home
* google assistant 
* https://aws.amazon.com/lex/

## Linked 
* search users API v2
* chat API v2

# Other ideas
* Statistics in real time for usability in different zones of an article, document, etc, cv.

