---
description: Let's look at what you'll find in the tutorial and what you're going to build
---

# Before We Begin

## Overview

In this tutorial, we are going to be looking at what Juicebox is and how to use it, and then we are going to build something using a lot of the core features you are likely to encounter in the Juicebox apps you will build here. This tutorial is a guide that teaches you to think like a Juicebox developer and give you the tools necessary to help you solve issues as they arise. While the base tutorial won't get into all of things that the platform can do, we will be creating advanced tutorials that will help lay out a more exhaustive base for you to build on.

{% hint style="info" %}
If you have any ideas on advanced topics that you'd love to see covered in the advanced tutorials, feel free to reach out to Seth \(seth.williams@juiceanalytics.com\) about making that. We'll see what we can do.
{% endhint %}

## Section Breakdown

### [Part 1 - Getting to Know Juicebox](tutorial-part-2.md)

In this section, we are going to be looking at some core concepts, the layout, and some common blah blah blah \(UPDATE ME WHEN THIS PART IS WRITTEN\). If you want a bit of a deeper look at the concepts, head[ over here](../concepts/). Becoming familiar with this will be very helpful for the tutorial, but not necessary.

### [Part 2 - Folder Structure and App Configuration](tutorial-part-3.md)

Here we will go over how to create a Juicebox app, what the different options mean, and what you'll see once you create your first Juicebox app.

### [Part 3 - Building Data Services](part-3-building-data-services.md)

In Part 3, we'll look at how to build out data services, how to interact with the database, and dive into how picking the right ingredients and recipe can be crucial when creating an app. We'll also talk about how the frontend and backend are connected and how seamlessly you can move from one to the other. **This will be the meatiest section of the tutorial, so make sure you're ready to dive in deep when you get here.**

### [Part 4 - Building the Slices](part-4-building-the-slices.md)

Part 4 is going to teach you how to work with several common types of slice, what their configurations look like, and how you can manipulate them to do what you want.

### [Advanced Tutorials](advanced-tutorials.md)

The last section is going to be a collection of advanced tutorials that will teach you some of the finer points of the platform and really help you unlock the hidden power that Juicebox has. 

{% hint style="info" %}
Each advanced tutorial, unless noted, will build off of your base finished product from the tutorial, so make sure you create new branches for each tutorial you want to try
{% endhint %}

## What Are We Building?

In this tutorial we will be building an app that uses [this dataset](https://www.kaggle.com/pavanraj159/olympics-history-1896-2016) to look at the history of The Olympics to see which countries are the most dominant in the winter and summer games, and which countries are trending up/down in medal counts. 

One of the hardest parts about working with data is ingesting and cleaning it. Usually intricate systems are built to take data from its source and transform it into something we can use. Luckily, in the Olympics app the data is already in our database and ready to be used. One of the [advanced tutorials](advanced-tutorials.md) will look at how to clean and structure data and things to look out for in that regard, but we'll cross that bridge later.

## Prerequisites

There are a few tools you will need access to and basic familiarity with in order to effectively follow this tutorial and begin developing with Juicebox:

* **git** and/or [**GitHub Desktop**](https://desktop.github.com/) for managing your app’s code repository.
* An **IDE** for writing and editing code. ****[**PyCharm**](https://www.jetbrains.com/pycharm/) ****is widely used for application development at Juice. While it isn’t a requirement for building Juicebox apps, using PyCharm may help our team support you in troubleshooting should any troubles arise.
* \*\*\*\*[**Devlandia**](http://devlandia.net/en/), the Juicebox development environment that will allow you to host, manage and test your app locally. Getting into Devlandia will be part of your initial computer setup, but if you haven't done that for some reason, reach out to the Ops team.

Alright, so now that we've got all of that out of the way, let's dig in a bit.

