---
layout: post
title:  "Open worlds in unity"
date:   2018/04/15
author: Oscar Johnson
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/nOdQnMDJMpI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---
### About
The goal of this project was to make a modular, node based system that would allow developers to easily create open worlds in unity.

This was achieved by allowing the creation of 'sectors', a collection of unity assets that make up a chunk of an open world map. These sectors are saved a JSON files and can be loaded and unloaded dynamically as the player navigates the world, allowing for an infinitely sized world to be streamed in real time at a relatively low system cost.

The system is designed to be as open as possible to allow developers to create sectors of any size, with any number of objects and can work on top of unity's AI plugins so that navigation meshes can be baked directly to the world map. This allows devs to seamlessly create game worlds that work with their existing AI implementations.


This project was coded in C# for unity by myself as a part of my Advanced technologies course and is an ongoing project.
The project can be viewed and downloaded from my github repository [here](https://github.com/JohnnersUK/AT-Open-World) and added to any existing unity project for easy, customizable open worlds. 

