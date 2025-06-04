**About High-Level Architecture of a Telecom Mission Control SaaS Platform for enterprises**

* User enters a URL
* The request goes to the DNS and resolves the domain name to an IP

* Static content can be served from CDN for fast delivery
* CDN caching helps with quick UI loading and service workers cache for offline support of the application.

* Load Balancer is used to handle the request and distributes them across multiple web servers for reliability and scalability. Every web server can   host the FE app with static resources
* User authentication is handles in Security gateway

* Api gateway is a single point to access all the micro services, Authenticated users request will be redirected to the respective services

* Each domain has its own microservcies and its dedicated DB which helps with scalability. Api entities and endpoints are discussed later.

* Caching is used to store frequently access data which could improve performance.

* An established websocket connetion is needed for real time updates for the Dashboard component.

* Accessibility and Globalization: Using Semantic HTML and following WACAG guidelines helps with building accessible UI components that is user friendly. And Localization using I18n can be implanted for loading the UI  globally.

** WorkFlow**

* A Real Estate developer adds new towers and carriers information.
* Then a POST/tower API call is made to save this info in the backend.
* The UI then uses a GET/tower API to retrieve and display the list of towers and their carriers information.
* A device tries to connect to a nearby tower.
* This triggers a backend call that sends device info and updates the database with the new device record.
* The system detects app usage by a device/user
* Tower captures app usage and checks GET/policies based on user roles.
* If its accepted, the dashboard is updated with realtime data to the UI (this can be achieved by establishing a Websocket connection)
* If its denied, it ends in a failure node

* 
