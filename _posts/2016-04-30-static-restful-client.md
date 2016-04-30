---
layout: default
title: Static RESTful Client
---

#Static RESTful Client

*It's been a while since I blogged anything if at all. I think for the next couple weeks I will make an effort to blog regularly at least a weekly basis.

This is currently an idea in progress.

##Origins

It all started when I began working on a new project with a friend. I originally began my work setting up servers with Ansible on Amazon Web Services. I currently use my laptop as host machine to launch and provision instances. Using a laptop to run deployment scripts is fine, but I wanted something that was more...mobile?

###Ansible Phone App?

I started thinking about running deployment processes through a phone instead of a laptop, but that will require installing Ansible in phones. This seems mediocre of an idea: requires lots of effort and resources to build.

###RESTful Mobile Client/Ansible Server

This seems a lot easier. A headless Ansible server with RESTful JSON interface that requires authentication would be sufficient. A RESTful mobile client app that would locally store authentication credentials will interact with the Ansible Server to deploy and run script to manage AWS instances.

I ran a basic app and online search for RESTful mobile clients in iOS app store. They seem rather...tedious? So many fields for headers and configuration to make requests to urls. I'm not a UI/UX professional, but I think options and fields ought to be abstracted if not obscured as contextual options like right click buttons. Having too many fields and text input is too distracting and generates too much clutter. Futhermore, many of these apps don't store these requests like structured data; instead these are store by history.

I suppose I could complain, but I figured I might as well create my own ideal RESTful client setup. I'm not experienced in mobile development, so that brought me to the idea of a static RESTful web app client.

##My Ideal RESTful Web App Client

Here is my wishlist:

* persistance: I can store the previous requests I've made locally in browser database (either LocalStorage or IndexedDB)
* structured data: RESTful APIs, if done, correctly, should represent a tree. Root is the url with a string, followed by child resources (/{resource/{id}), followed by request type, and lastly payload.
* meta-data/configuration: with a structured data, each node should have a configuration setting (headers, etc.). Each node of the tree will either inherit the parent, override, or add additional meta prior to become processed.
* client-side authentication: store simple username and password on the browser side. These should credential generated on the Ansible server side and not credentials provided by AWS services.
* intuitive UI/UX designs: making requests should be simple gestures; little or no typing necessary

I suppose this is a lot to ask for, but mentally it seems very ideal and intuitive for people looking to make simple/beautiful requests to servers.


