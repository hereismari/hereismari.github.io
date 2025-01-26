---
title: What is stevedore? and how is it related to Sahara?
author: Marianne Linhares
header-img:
date: 2016-12-10
tags: [Post, Outreachy, OpenStack]
layout: article
category: pre_2017
---

# what is stevedore? and how is it related to Sahara?

### **Before we start…**

This post is considering that:

  1. You know Sahara :)!
  2. You don’t know stevedore :(, or you know it, but feel like you should know more about it or how it relates to Sahara
So If you don’t know Sahara, I can introduce you two, here is [Sahara](http://docs.openstack.org/developer/sahara/). I’ll let you know each other.

### **First, what is stevedore?**

_“Python makes loading code dynamically easy, allowing you to configure and extend your application by discovering and loading extensions (“plugins”) at runtime. Many applications implement their own library for doing this, using __import__ or importlib. stevedore avoids creating yet another extension mechanism by building on top of setuptools entry points. The code for managing entry points tends to be repetitive, though, so stevedore provides manager classes for implementing common patterns for using dynamically loaded extensions.”_ If you’re not familiar with some concepts like _setuptools, entry points, _and how these concepts could be used to make the process of loading code dynamically easier, [this link](http://docs.pylonsproject.org/projects/pylons-webframework/en/latest/advanced_pylons/entry_points_and_plugins.html) can be very helpful. So now we kind of know what is stevedore: **_“stevedore manage dynamic plugins for Python applications”_**. So stevedore is “independent” of OpenStack, it’s used by a lot of projects of OpenStack, but any Python code can use it :)!

### **Okay… but what exactly are Plugins and why should I use them?**

Plugins are software components that add features to an existing computer program (core code)._ “When a program supports plug-ins, it enables _**_customization_**_”_. In other words, a plugin is a piece of code that is not a part of the core code, and because of this fact it can be added or removed easily. And it provides some features, services and operations in a more specific away. And we should use plugins because:

  * We already talked about customization, that means that using plugins you can have “different versions” of the code in an easier way. If I don’t need all the plugins I can install just the plugins and dependencies I need.
  * We will have an improved design. _“Keeping a separation between core and extension code encourages you to think more about abstractions in your design”_.
  * __“Plugins are a good way to implement device drivers and other versions of the Strategy pattern. The application can maintain generic core logic, and the plugin can handle the details for interfacing with an outside system or device.”__
  * __“Plugins also provide a convenient way to extend the feature set of an application by hooking new code into well-defined extension points. And having such an extensible system makes it easier for other developers to contribute to your project indirectly by providing add-on packages that are released separately.”__ 

### **And how Sahara uses stevedore?**

Let’s open [Sahara](http://docs.openstack.org/developer/sahara/) source code and have a look, here is the link: <https://github.com/openstack/sahara> As we discussed plugins are loaded through entry points, the configuration can be seen in a file called **setup.cfg**, search for [entry_points], the syntax is:  **namespace = name = module.path: importable_from_module** By the name of the namespaces we can suppose that exists a driver responsible for SSH, console scripts are implemented with stevedore, cluster’s plugins, a Heat engine and some other things. Feel free to explore these namespaces on your own and see how they work! I may add more details about this with the time :)!

**References**:

* [http://docs.openstack.org/developer/stevedore/ ](http://docs.openstack.org/developer/stevedore/)
* [http://docs.pylonsproject.org/projects/pylons-webframework/en/latest/advanced_pylons/entry_points_and_plugins.html ](http://docs.pylonsproject.org/projects/pylons-webframework/en/latest/advanced_pylons/entry_points_and_plugins.html)
