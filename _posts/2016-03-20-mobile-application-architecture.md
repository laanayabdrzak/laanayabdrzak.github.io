---
layout: post
title:  Mobile Application Architecture
---
Broadly, there are **two categories** of mobile apps available:

* **View-heavy data-driven**
  - Email, Social, News, Todo
* **Graphics-heavy drawing**
  - Games, Creative Art, Photo Editing 

In this post I'm gonna focus on **data-driven** apps.

## Screen Archtypes

- **Login**
- **Register**
- **Stream**
- **Detail**
- **Creation**
- **Profils**
- **Settings**
- **Maps**

## Application Architecture

- Learning to build real **data-driven** apps requires a few core concepts:

  - **Views:** Common Controls and View Layout

  - **Events:** Interaction and Event Handling

  - **Navigation:** Screen Flows and Navigation

  - **Data:** Models, Networking and Persistence

  - **Platform:** OS Services, Hardware, Accessing Sensors

- Real **data-driven** apps usually require an API.

  - Apps **display data** and this comes from a **source**.

  - Most mobile apps rely on **server-side APIs** for data.

  - When developing mobile, consider what sources your app's data is coming from / being saved to.  

  - Many apps **leverage existing APIs** while others require a custom server-side component.

## Mobile Client Architecture

![Mobile_Client_Architecture](/img/Mobile_Client_Architecture.png)
 
## Server Side API

![Server_Side_API](/img/Server_Side_API.png)

## Full Application Architecture

![Full_Architecture_Application](/img/Full_Architecture_Application.png)



