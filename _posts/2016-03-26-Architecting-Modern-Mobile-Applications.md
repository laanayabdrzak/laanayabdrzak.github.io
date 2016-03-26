---
layout: post
title:  Architecting Modern Mobile Applications
feature-img: "img/background_post_4.jpg"
---

Hey there! After my post on [Android Development : Some of the best practices](https://medium.com/@laanayabdrzak/android-development-some-of-the-best-practices-27722c685b6a#.de2dny4t6), I decided to give you taste of what I consider a good approach when it comes to **architecting modern mobile applications** (android in this case).

The first resource I would like to present is a superb blogpost by [uncle bob](https://blog.8thlight.com/uncle-bob/2012/08/13/the-clean-architecture.html)

- Good **Architecture** is :

   - Independent of UI

   - Independent of Frameworks

   - Independent of any agency externe

   - Independent of Database

   - Testable

## Why to invest into architecture ?

I would like to start by talking why I think that **apps architecture** is an important topic to discuss and why it is worth to invest time and resources into building one. It is sometimes pretty easy for team to start together working on an application, but this approach cannot scale, It does not work well, so let’s face it.

## Integrating Model View Presenter

In the past few years, several architectural patterns such as **MVP** or **MVVM** have been gaining popularity within the Android community. There are more and more people talking about it. 

#### So why use MVP?

In Android we have a problem arising from the fact that Android activities are **closely coupled** to both interface and data access mechanisms. The main issue with this approach is that the View layer had too many responsibilities, so it becomes impossible to maintain and extend. Ideally the **MVP** pattern would achieve the same logic that might have been completely different and interchangeable views. **MVP** makes views independent from the data source, it divide the application into at least three different layers, which let us test them independently.

- The **model** is the data that will be displayed in the view (user interface).
- The **view** is an interface that displays data (the model) and routes user commands (events) to the Presenter to act upon that data
- The **Presenter** is the **middle-man** and has references to both, view and model.

## ReactiveX approach: [RxJava/ RxAndroid](https://github.com/ReactiveX/RxAndroid)

- Developing an Android app that has lots of network connections, user interactions, and animations often means writing code that is full of nested callbacks, wich I called callback hell. **ReactiveX** offers an alternative approach that is both clear and concise, to manage asynchronous tasks and events.

- **RxJava** is a **JVM** implementation of **Reactive Extensions**, developed by NetFlix, and is very popular among Java developers. 

- **RxJava** is the new hotness amongst Android developers these days. I know it can be difficult to approach initially when you come from an imperative world. But believe me once you get your hands dirty you gonna love the way that **RxJava** can remove the need for having nested callbacks, it's so awesome!

## Dependency Injection approach: [Dagger 2](http://google.github.io/dagger/)

Generally in **Clean Architecture**, code is separated into layers in an onion shape with one dependency rule: **The inner layers should not know anything about the outer layers**. Meaning that the dependencies should point inwards. at this point **Dagger 2** came with this rules:
    
- Components **reuse**, since dependencies can be **injected** and **configured** externally.

-  When **injecting** abstractions as collaborators, we can just change the implementation of any object without having to make a lot of changes in our codebase, since that object instantiation resides in one place isolated and decoupled.

- **Dependencies can be injected into a component**: it is possible to **inject** mock implementations of these dependencies which makes **testing** easier.

At least the advantages for using **Dagger 2**:

- Simplifies access to shared instances. Just as the [ButterKnife](http://jakewharton.github.io/butterknife/) library

- Easy configuration of complex dependencies

- Easier unit and integration testing

- Scoped instances Not only can you easily manage instances that can last the entire application lifecycle

## Lambda expressions approach: [Retrolambda](https://github.com/evant/gradle-retrolambda)

- Is a **Java library** for using **Lambda expression syntax** in Android and other pre-JDK8 platforms. It helps keep your code tight and readable especially if you use a functional style with for example with **RxJava**.


## Testing approach: Espresso/ JUnit/ Mockito/ Robolectric

**Testing your app** is an integral part of the app development process. Testing allows you to verify the correctness, functional behavior, and usability of your app before it is released publicly.

- **Presentation layer**: UI tests with Espresso 2 and Android Instrumentation.

- **Domain layer**: JUnit + Mockito since it is a regular Java module.

- **Data layer**: Migrated test battery to use Robolectric 3 + JUnit + Mockito. Tests for this layer used to live in a separate Android Module, since back then (at the moment of the first version of the example), there was no built-in unit test support and setting up a framework like robolectric was complicated and required a serie of hacks to make it work properly.

## Package organization approach: Package By Feature not Layer

The first question in building an application is **How do I divide it up into packages?**. For typical business applications, there seems to be two ways of answering this question.

- **Package By Feature**
   - In package-by-feature, the package names correspond to important, high-level aspects of the problem domain. Each package usually contains only the items related to that particular feature, and no other feature. For example:

```
abderrazak.com.recycleviewcardview
├─ data
│   ├─ local
│   ├─ model
│   └─ remote
├─ injection
│   ├─ component
│   └─ module
├─ ui
│   ├─ main
│   ├─ detail
│   └─ etc..
├─ util
└─ views
   ├─ adapters
   └─ widgets
```
**Gains and Benefits**

By looking at the structure you can already tell what the app is all about (figure above);

- Higher modularity;

- Easier code navigation;

- Higher level of abstraction;

- Separates both features and layers;

- More readable and maintainable structure;

- More cohesion;

- Much easier to scale;

- Less chance to accidentally modify unrelated classes or files;

- Much easier to add or remove application features;

- And much more reusable modules.


- **Package By Layer**

The competing package-by-layer style is different. In package-by-layer, the highest level packages reflect the various application "layers", instead of features, as in:

```
abderrazak.com.recycleviewcardview
   ├
   ├─ model
   ├─ activities
   ├─ services
   ├─ fragments
   ├─ util
   └─ etc..

```
Here, each feature has its implementation spread out over multiple directories, over what might be loosely called **implementation categories**. Each directory contains items that usually aren't closely related to each other. This results in packages with **low cohesion** and **low modularity**, with **high coupling** between packages. As a result, editing a feature involves editing files across different directories. In addition, deleting a feature can almost never be performed in a single operation.

## Organization build logic approach: Gradle

On Android, we use **gradle**, which is the official build tool system for android development. The idea here is to go through a bunch of advantage of this great build automation system 

- Build different flavours or variants of your app

- Make simple script-like tasks

- Manage and download dependencies

- Customize keystores

- Android Project Structure

- More..



Fortunately, app architecture is a really hot topic lately, and there are more than enough articles and blog posts describing different approaches for building different architectures in Android from classical concepts such as **MVP, MVVM, MVC** to some fancy new approaches like the Square way with **Mortar** and **Flow**. Hopefully that this article gonna helps you to achieve a better architecture for your future apps. Stay tuned for more posts. 
