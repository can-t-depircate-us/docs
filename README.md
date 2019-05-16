# Drone/Robot smart trash collector / tree land clearing

## Backend
### People
* Dani ( Spring -> manage and persist data)
* Paul ( aiohttp -> streaming & live data)
* Sebi ( Image recognition, drone command logic) 
### Tech
* Spring
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

## Backend Nodes:
* backend_1: aiohttp python streaming service
* backend_2: aiohttp python Image recognition service
* backend_3: atohttp python default drone commands & admin commands
* backend_persist: spring persist data service

### Spring - persistence backend
* user management
* event management
   
 	Models:
    	
  * User
    ```json
    	{
        	"name": "",
            "role": "",
            "created_at": "timestamp",
            "updated_at": "timestamp",
         	"score": "???"
        }
    ```
  * Event
  	```json
    	{
        	"image": "blob",
            "at": "timestamp",
            "label": "Open/Pending/Closed",
            "": ""
        }
    ```


## Flow 
* streaming (admin) : 
    - connection_flow: frontend -> backend_1 -> token backend_persist -> if OK start coonection frontend<->backend_1 
    - data_flow: drone -> websocket_1 backend_1 -> frontend
* live data(coord, img):
    - connection_flow: frontend -> backend_2 -> start connection
    - data_flow: drone -> backend_2 -> Image Recognition -> if OK http request to backend_persist & (websocket_2 -> frontend)
    
* drone commands (admin): frontend http request -> backend_3 -> backend_persist token validation (persist in memory of backend_2) -> if OK drone command & bigger weight than default drone commands 

* spring admin user for: streaming, commands, clean zone validation


## Extras 
* normal users for score rewarding, notifications and extra security
* vocal instructions !!!!!!! Nice to have !!!!!!!
* mobile app

