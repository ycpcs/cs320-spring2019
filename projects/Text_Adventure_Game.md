---
layout: default
title: "Project: Text-Based Adventure Game"
---

Project Summary
===============
Design and develop a platform for creating and playing text-based adventure games, AKA interactive fiction, as described for [Adventure](https://en.wikipedia.org/wiki/Colossal_Cave_Adventure), the first such game of its kind.  In order to fully understand the concept, as well as the endless possibilities, you should first study the history of the early interactive fiction games, as well as locate an implementation that you can play, to familiarize yourself with the genre.

The game is based upon a player traversing a "map": a collection of locations (rooms), the connections between those rooms, and the commands to move between rooms.  As the player traverses the map, they collect treasures, and are confronted with a number of problems they must solve in order to continue to make progress in the game.  The goal is to traverse as much of the map as possible, collecting as much treasure as possible, removing the treasure to a safe location, and surviving the adventure, while scoring as many points as possible.

Basic Requirements
==================

There must be an established dictionary and vocabulary - the words and phrases that the game engine comprehends.  These fall into the general categories of:

* Direction and movement commands: north, south, up, down, etc.

* Action commands: take, throw, light, drop, run, jump, crawl, etc.

* Status queries: inventory, look, location, score, health, time, etc.

* Questions: queries that the game and user can ask

* Responses: replies that the user and game can give

* Nouns: collection of objects of the game - actors, treasure, weapons, objects

* Descriptions: room and actions descriptions

You will need to create a game "engine" - the functionality that executes the moves and actions that the user enters.  In addition that game engine will need to keep track of score, health, inventory, object locations, rooms that the player has visited, and the locations and movements of any of the other active agents (animals, monsters, etc) that exist in the game.  There may be other functionality that the game engine will need.

There must be an inventory of objects that can be distributed throughout the rooms in the map.  Items consist of tools, weapons, materials, treasures, commodities, machines, etc.  Objects can generally be mamipulated by the user, taken into the user's posession, and/or moved between rooms, but some objects may also be stationary.

There must be multiple actors and agents: the player(s), various creatures and monsters, and benign and/or benevolent characters.  It is possible for the actors and agents to move about the map on their own.  There can be conflict between various actors - sometimes facilitated by objects that the player has, or objects that are contained within a certain room.

There must be logic that requires that certain conditions exist for the player to take certain actions - they must have a lamp to see in the dark - but they must light it first, and thus might need an ignition source.  They must have fresh batteries in order to use a headlamp or flashlight, they must have a canteen to carry water to drink while traversing the map.

There must be multi-step problems and riddles for the user to solve in order to make progress at certain points in the game.

There should also be a method for saving and restoring the game state, and keeping track of the highest scores.

The database for the program will consist of all of the above.

You MUST create your map, plot, and narrative - you cannot copy another text-based adventure game.  You should initialize all of the above lists from text-based CSV files that will initially hold your data.  You will use those CSV files to initialize/recreate your database, and to edit/extend your game.

User Interface
==============

Finally, in addition to the console that accepts keyboard input and displays the text of the game, the game should have a user interface that allows the user to see their score, their health, their current posessions, the treasures they have gathered, the creatures they have "dispatched", etc.

Stretch Goals
=============

For the truly motivated, here are some stretch goals:

* Have the game be able to produce a graphical map for the player of all the locations that they have visited - while excluding those locations that they have not yet encountered.

* Add functionality for a multi-player game - where more than one player can be active in the same game at one time.  You will also need to take into account possible interactions between the players.

* Add pictures and graphics for the various agents, actors, rooms, and objects of the game.

Extensible Features - The project should not only allow the user to play an established "default" game, it should also allow the user to extend that game by adding:

* Locations (rooms) to the games's "map"

* Actors (creatures, monsters, benign and/or benevolent agents)

* Objects (treasure, tools, weapons, commodities)

* Commands (movement, action, queries, replies, status)

* Problems, puzzles, predicaments (sequences of commands and events that lead to conditional progress, or setbacks)

* Scoring metrics associated with the above

Extend the user interface to facilitate creating/extending the game, as above.  In fact, this could be the means by which you can create your initial game for testing and playing purposes:

* Creating and connecting new rooms to the map

* Adding new actions

* Adding new creatures

* Adding new objects

* Adding new problems

* Assigning point values for the above

* Editing the existing components