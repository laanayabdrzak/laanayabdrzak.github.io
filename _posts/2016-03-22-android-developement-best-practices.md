---
layout: post
title:  Android Development — Some of the best practices
feature-img: "img/background_post_5.jpg"
---

Hi! After a modest number of projects I've decided to share with you some of the things that experience made me learn, I mean the hard way.

Here is the selection:

- Think twice before adding any **third party library**, it’s really a serious commitment

- Don’t use a **database** unless you really need to

- You can think about [realm](https://realm.io/) it's really awesome!

- Hitting the 65k method count mark is gonna happen fast, I mean really fast! And **Multidexing** can save you

- **RxJava** is the best alternative to **AsyncTasks** and so much more

- **Retrofit** is the best networking library there is

- Don't write your own **HTTP** client, use **Volley** or **OkHttp** libraries

- Shorten your code with **RetroLambda**

- Combine **RxJava** with **Retrofit** and **RetroLambda** for maximum awesomeness!

- I use **event Bus** and it’s great, but I don’t use it too much because the codebase would get really messy

- Package by **Feature**, not **layers**

- Move everything off **the application thread**, that's can save you from **ANR**

- [lint](http://developer.android.com/tools/debugging/improving-w-lint.html) your views to help you optimize the layouts and layout hierarchies so you can identify redundant views that could perhaps be removed

- Use **Gradle** and its recommended project structure

- Put passwords and sensitive data in **gradle.properties**

- Use **styles** to avoid duplicate attributes in layout XMLs

- Do not make a **deep hierarchy** of **ViewGroups**

- Monitor **power source** and **battery** more data updates while charging? Suspend updates when **battery** is **low**?

- You can think about **JobScheduler**

- **onLowMemory()** it will be called when the whole System runs low on memory, not your App, so you can't exactly avoid OOMs with it.

- **Drain battery** is **30%** (image, animation, ...), and **70%** (Analytics, ads, maps, gps)

- **Monitor** connectivity and type of connection (more **data** updates while on **wifi?**)

- Use the [Account Manager](http://developer.android.com/reference/android/accounts/AccountManager.html) to suggest login usernames and email addresses

- Give your **methods** a **clear name** for what they are going to do

- The **launch screen** is a user’s first experience of your application

- Do not show the **launch screen** if you don’t have to

- **Tests** are great for performance: Write slow (but correct) implementation then verify optimizations don’t break anything with tests

- Keep your **colors.xml** short and **DRY**, just define the palette

- Also keep **dimens.xml** **DRY**, define generic constants

- In reality **perfExternal** is rarely used as an application on the **external storage** is stopped once the device is connected to a computer and mounted as USB storage

- Use **StringBuffer** or **Stringbuilder** classes when there is a lot of modifications to string of characters

- To avoid **Memory Leaks** :

  - Don't reference **View** inside **AsyncCallback**

  - Don't reference **View** from **static** object

  - Avoid putting views inside collection that's don't have clear memory pattern, you can use **WeakHasMap**
  
- **FlatBuffers** is an **efficient** cross platform serialization library, so use it

- **Serializable** it's simple to implement, but in term of performance it's really bad :(




