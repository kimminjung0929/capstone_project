# Yeungjin University team8 capston design
* Team name : Infinite
* Project name : baribari
* Department : computer information
* Major : web database
 
## Introduction to the Project
The goal is to develop a self-driving delivery system within a limited area, such as campus, government offices, etc.

## Project Purpose
* Currently, most of the deliveries on campus and in government offices are delivered directly by motorcycles and walking. 
* This can cause motorcycle accidents and it takes time to deliver them directly.
* We started the project to reduce these accidents and time consumption.

## Project characteristic
* Deliver the goods you wish to deliver via RC car
* User focused, convenient screen configuration
* The administrator directly manages stops and routes in a flexible manner.
* Identifying traffic through statistical graphs of delivery information
* View current delivery status and RC car status at a glance


## Part
My part is back end and communicated with RC car, web, and app using socket.io in node.js. 

* Server <-> Web
  * Communicate the status of the operation to the control page of the web in real time.
  * Send RC car operation status, delivery status, delivery waiting status, RC car error notification, RC car gps to web
  
* Server <-> App
  * Delivery operation
    * Store the delivery operation information sent by the sender in the database
    * Show recipients delivery acceptance alerts and current delivery wait rank
    * The sender and receiver can cancel the pending delivery.
  * Notification
    * Send notification of departure, loading, and completion of delivery of RC car assigned to the sender
    * Send notification of delivery start, delivery arrival to recipients
    
* Server <-> RC car
  * Send task information received from the sender to RC car
  * When the RC car arrives at the origin and destination, it receives a signal and notifies the user.
  * If an error occurs in the RC car, it receives a signal and sends the RC car number and the error content to the web.
