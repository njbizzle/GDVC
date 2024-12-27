# GDVC (Geometery Dash Version Control, a Discord bot)

## Context

This is built for a game called Geometry Dash, where user-created levels are uploaded to and downloaded from game servers. I used to manage a lot of collaborative projects where 10+ people would be communicating over messaging platforms like Discord and working on a single level. But the way that levels are shared makes it difficult to manage the most recent version of the level, and I had to take care of a lot of that manually.

I got the inspiration since I love running these level collaboration projects, but they just need constant maintenance over months, and I knew for a fact that there would be long periods of time where I just wouldn't have the time to dedicate. So this was a way of automating it, allowing me to spend time more intermittently on the creative aspects, rather than constantly just making sure people were not stepping over each other.

## Overview

This is a Discord chat bot that takes a lot of inspiration from software like Git to make a sort of version control to manage larger projects. I wanted to make a bot that would be able to manage multiple projects, and keep track of their working level IDs (which allows someone to copy a level off the game server), and then have the ability to push the edited version back to the project, as well as record information about the changes that were made. There are also features to make sure that only one person checks out the level at a time, and in case the level splits and forms a bit of a tree, the ability to visualize all the changes and prune these extra branches.

Ultimately I dropped the project and it sadly didn't see any use outside of me and a few other people despite being in a working state (last time I checked).

## Tools used

I made use of the Discord.py Python library which uses the asyncio library for asynchronous tasks. Discord.py is a pretty extensive library, but a lot of the features seemed like they would be fun to reimplement, so a lot of the features like commands and arguments are my own implementation.

## Aspects That I'm Proud of

This is a project where I'm very proud of my implementation and the code that I wrote. A lot of thought went into design for this project, and it's ended up being extraordinarily robust, it finds a way to handle pretty much anything you throw at it.

Also since there is a lot of information that needs to be stored in a more permanent way, everything needs to be saved to and loaded from some other file. The solution I came up with was to make a system to serialize all my Python objects into a JSON file and then load all the information back when the program starts up. With features like projects existing in different discord communities, permissions, multiple projects, and complex trees of commits, this became a pretty large task, but I think I came up with some pretty elegant solutions.

This was by far my most involved Python project at the time. To implement a lot of these features I had to do a lot of research into the inner workings of the language, especially for the JSON serialization. I also spent a lot of time learning the asyncio library, which ended up being much more involved than I initially expected. I didn't end up making use of it very much, but it's a really cool library that operates on a super low level.

I also hosted the bot myself. I have a Raspberry Pi which was running the script and I also built a lot of tools to help me maintain the program while it was running. 

## Some Screenshots of It Working

### A project is created, then the initial branch was checked out
<img src="pictures/create.png">

### All commits on an existing project are displayed
<img src="pictures/view.png">

