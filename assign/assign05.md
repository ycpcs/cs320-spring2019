---
layout: default
title: "Assignment 5: Use Cases"
---

**Due: [See Assignment Schedule](index.html)**

This is a **team** assignment

# Your Task

Your task is to write use cases which document the requirements for the system your team will implement.

## Use cases

A use case describes a scenario in which one or more actors (agents external to the system) use the system to accomplish a goal. One of the actors involved in the use case must be an initiator of the use case.

Each use case should have a name. The name should indicate which actor is the initiator of the use case, and what goal is accomplished. For example, in the TicTacToe system, we might have a use case called "Player takes a turn."

The use case should list a sequence of steps which accomplish the goal. If there are important options that might be encountered, such as error conditions, these can be listed in "nested" steps.

So, our "Player takes a turn" use case for TicTacToe might look like this:

> **Player takes a turn**
>
> **Actor**: a human player
>
> **0.** Precondition: it is the player's turn
>
> **1.** The player chooses a location on the board in which to place a piece
>
> **2.** System checks to see if the player has won the game, or if a draw has resulted
>
> Extensions:
>
> > **1a.** If the location is already occupied by a piece, issue error message and go back to step 1
>
> > **2a.** If a player has won, indicate which player
> >
> > **2b.** If a draw has occurred, inform players

Note that TicTacToe is a pretty simple example: for a more complex problem, a use case might be be more involved.

**You should write *as many use cases as necessary* to document the important behaviors of your system, as experienced by the relevant actors.**

**Use the example format given in the [Use Case lecture](../lectures/lecture08.html) for the Use Cases you provide for this submission.**

# Submitting your work

Create a Google Doc for your group's Use Case document, and name it **assign05-www-xxx-yyy-zzz**, substituting the YCP user names of your project team members.  Place the Use Case document under your shared Google Drive Group Project folder.

<div class="callout">
<b>Important</b>: Your submission <i>must</i> be a Google Doc, shared via your Group Project folder.
Do not submit a file in any other format.
</div>
