# Table of Contents
- [1. Introduction](#1-introduction)
  * [1.1 Project Summary](#11-project-summary)
  * [1.2 Project Purpose](#12-project-purpose)
- [2. Object Classification](#2-object-classification)
  * [2.1 Object Diagram](#21-object-diagram)
  * [2.2 Entity Objects](#22-entity-objects)
  * [2.3 Control Objects](#23-control-objects)
  * [2.4 Boundary Objects](#24-boundary-objects)
- [3. Further Steps](#3-further-steps)
  * [3.1 User Event Loop](#31-user-event-loop)
  * [3.2 Device Controller Event Loop](#32-device-controller-event-loop)  
  * [3.3 User Controls](#33-user-controls)  
- [4. Non Functional Attributes](#4-non-functional-attributes)
- [5. Classes](#5-classes)
- [6. Message Protocol](#6-message-protocol)
- [7. Versions](#7-versions)
- [8. Authored By](#8-authored-by)

# 1. Introduction
## 1.1 Project Summary
_Shout!_  is a bluetooth low energy (BLE) mesh-based messaging application that is supported on Android and iOS. It allows users to talk to other users within a single messaging room as long as they are all connected to the same bluetooth mesh.

## 1.2 Project Purpose
This document will cover all of the analysis needed for _Shout!_ and will describe all of its features and how they work.

The intended audience for this document will be the client (David Brown) and the project team. They will use this document to be reminded of the analysis of the project. The document will also be used as the basis for the project.
			
# 2. Object Classification
						
## 2.1 Object Diagram 

<img src="https://cp317s18.github.io/analysis/analysis-object-diagram.png" align="left" hspace="70" />

## 2.2 Entity Objects
- User - A user of the _Shout!_ application
- Message - User generated text to be broadcasted to other _Shout!_ users
- Device -  The basis for the Bluetooth LE software and its connections 


## 2.3 Control Objects 
- Connection Interface - Coordinates all matters related to the exchange of messages between users
- User Controller - Coordinates all matters related to user data

## 2.4 Boundary Objects
- Relay Node - Enables the user to pass along messages to or from other users
- Send - Enables the user to export or send messages to other users 
- Receive - Enables the user to obtain or receive messages from other users
- Connect - Establishes the first connection between relay nodes 
- SetUsernameView - The UI of the application, connects the user to the application backend 

# 3. Further Steps 

## 3.1 User Event Loop
<img src="https://cp317s18.github.io/analysis/User-Event-Loop.png" align="center" hspace="70" />

## 3.2 Device Controller Event Loop
<div style="width: 800px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://www.lucidchart.com/documents/embeddedchart/044b7b86-ad07-43b7-a05d-4d036c6b927e" id="8rBOi4gD83Z_"></iframe></div>

## 3.3 User Controls 
<img src="https://cp317s18.github.io/analysis/User-Controls-Event-Loop.png" align="center" hspace="70" width="400" height="400"/>

# 4. Non Functional Attributes
 - User will see a searching screen then will join mesh network as soon as a nearby device is found
 - User will see when disconnected
 - Messages will be seen by all users in mesh in under 3 seconds
 
# 5. Classes
<div style="width: 800px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://www.lucidchart.com/documents/embeddedchart/c69ce3f8-67ac-4a84-aca1-aacb30c9be36" id="YWMJamWYOgXw"></iframe></div>

# 6. Message Protocol
- MessageType (enum)
	- ChatMessage (0)
	- ConnectionMessage (1)
	
- Message (dictionary)
	- type (MessageType.ChatMessage)
	- username (String)
	- content (String)
OR
- Message (dictionary)
	- type (MessageType.ConnectionMessage)
	- username (String)

# 7. Versions
- Version 0.1 6/03/2018 `Document outline created` 
- Version 0.2 7/06/2018 `Added message protocol` 
- Version 0.3 8/14/2018 `SQA items corrected`

# 8. Authored by: 
- Jayanth Koroth
- Emily Hryb
- Tiffany Chan
- Greg Murray
- Delina Ghebrekristos
- Andrew Badali
- Adam Benwood
- Alex Keats
- Benjamin Segall

