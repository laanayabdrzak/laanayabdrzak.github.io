---
layout: post
title:  Mobile Application Architecture2
feature-img: "img/background_post_2.jpg"
---

Hi! After a modest number of projects I've decided to give you some of the things that experience made me learn, I mean the hard way.

Here is the selection:

- Think twice before adding any third party library, it’s a really serious commitment

- Don’t use a database unless you really need to

- Hitting the 65k method count mark is gonna happen fast, I mean really fast! And multidexing can save you

- RxJava is the best alternative to AsyncTasks and so much more

- Retrofit is the best networking library there is

- Shorten your code with Retrolambda

- Combine RxJava with Retrofit and Retrolambda for maximum awesomeness!

- I use event Bus and it’s great, but I don’t use it too much because the codebase would get really messy

- Package by Feature, not layers

- Move everything off the application thread

- [lint](http://developer.android.com/tools/debugging/improving-w-lint.html) your views to help you optimize the layouts and layout hierarchies so you can identify redundant views that could perhaps be removed

- Use Gradle and its recommended project structure

- Put passwords and sensitive data in gradle.properties

- Don't write your own HTTP client, use Volley or OkHttp libraries

- Use styles to avoid duplicate attributes in layout XMLs

- Do not make a deep hierarchy of ViewGroups

- Monitor power source and battery (more data updates while charging? Suspend updates when battery is low?)

- Monitor connectivity and type of connection (more data updates while on wifi?)

- Use the Account Manager to suggest login usernames and email addresses

- Give your methods a clear name for what they are going to do

- The launch screen is a user’s first experience of your application

- Do not show the launch screen if you don’t have to

- Tests are great for performance: Write slow (but correct) implementation then verify optimizations don’t break anything with tests

- Keep your colors.xml short and DRY, just define the palette

- Also keep dimens.xml DRY, define generic constants

- In reality perfExternal is rarely used as an application on the external storage is stopped once the device is connected to a computer and mounted as USB storage

- Use StringBuffer or Stringbuilder classes when there is a lot of modifications to string of characters

- Drain battery is **30%** (image, animation, ...) and **70%** (Analytics, ads, maps, gps)

- Avoid using splash screen, if it's necessary use launch screen

