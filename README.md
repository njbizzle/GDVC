# Geometry Dash Version Control (GDVC), a Discord Chatbot

#### A Discord chatbot that tracks and manages changes in collaborative level creations for the game Geometry Dash.

## Context

This was built for a game called Geometry Dash, in which user-created levels are uploaded to and downloaded from game servers. I've managed many collaborative projects where ten or more people would be communicating over messaging platforms like Discord to work on a single level. The way that levels are shared makes it difficult to manage the most recent versions, which I previously managed manually.

I love leading level collaboration projects, but they need constant maintenance over months. I knew that there would be long periods of time where I wouldn't be able to pay very close attention to the projects. This chatbot was my way of automating some of these tasks.

## Overview

This is a Discord chat bot that takes inspiration from software like Git to implement a version control system for managing large collaborative projects in the game Geometry Dash. The goal was to automate managing multiple projects between multiple communities, tracking working level IDs (which allows people to grab levels off the game servers), and then have the ability to push the edited version back to the project, as well as record information about the changes that were made. Also, in the event that the level splits and branches to form a tree of versions, I wanted to implement the ability to visualize all of the changes and prune unwanted branches.

This is a project where I'm extremely proud of my implementation and the code that I wrote. A lot of thought went into the software design, and it ended up being extraordinarily robust, which was a requirement since I was planning to let anyone interact with it.

## Tools Used

I made use of the Discord.py Python library which uses the asyncio library. Discord.py is an extensive library, but many of its features, that go beyond reading and sending messages, were reimplemented by me for fun.

I also made use of a Raspberry Pi that was configured to run Ubuntu Server, which hosted the Python scripts.

The major tools that I used are the following.

Python 3.12
The Discord.py Python library
The Asyncio Python library
PyCharm as a development environment
Git/GitHub for version control

## JSON Serialization

Due to the amount of information that needs to be stored persistently, I decided to read and write data using file storage. The solution I implemented was to make a system that serialized all my Python objects into JSON files, which were then loaded on startup. With the program supporting projects in different Discord communities and complex commit trees, the problem was complex. However, I think my solution and implementation are elegant.

## The asyncio Library

This is by far my most involved Python project. To implement many of these features I had to research and learn the inner workings of the language, especially for JSON serialization. Much of my research was spent learning the asyncio library, which ended up being much more complicated and interesting than I had initially expected. I didn't make much use of the more advanced asyncio features, but I'm happy this project gave me an excuse to learn the library. It's an interesting and helpful library that operates on a super low-level to run operations asynchronously. 

## Screenshots of the Chatbot Functioning

### A Project is Created, Then the Initial Branch Was Checked Out
![](pictures/create.png)

### All Commits on an Existing Project Are Displayed
![](pictures/view.png)

