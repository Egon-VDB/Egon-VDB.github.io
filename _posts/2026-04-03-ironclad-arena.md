---
layout: post
title:  "Ironclad Arena"
categories: projects
description: "A digital card game I developed with fellow students at Howest featuring online play and deck building."
---
Ironclad Arena is an online trading card game I developed as my final project at Howest together with my fellow students [Pavel Deleersnyder][PAVEL] and [Marwah Al-Shakhli][MARWAH].

The project focused on building a game with online capabilities for players to build decks, collect cards and play against each other. How we implemented it was up to us, with a free choice in architecture and codebase.

## Research & planning
I looked at multiple engines for the research, comparing visual fidelity, network support and technical capabilities. I went from the popular engines like Unreal to more obscure engines like LibGDX, selecting engines based on the card games they had. In the end Unity came out on top, its support for third party plugins and robust network tools sealing the deal.

With our engine selected I moved on towards network protocols and how we'd build the server. I found multiple .NET implementations that would work well with Unity, but one of them kept being recommended on forums, ENet. After some research and a small test project where a .NET server sent requests for the clients to move boxes, we settled on using it.

## Game design
For the game design, we drew inspiration from a variety of trading card games, ranging from Yu-Gi-Oh! and Hearthstone to Queen's Blood. Designing a card game from scratch proved to be a complex challenge, however, so we focused on selecting mechanics that complemented each other while remaining accessible and easy to understand. In the end, the strongest influences came from Yu-Gi-Oh!’s strategic board presence and Hearthstone’s approachable pacing and readability.

The game is played on a battlefield consisting of four rows, with each player controlling both a frontline and backline. Units positioned on the frontline must be defeated before opponents can target the backline or attack the player directly. We introduced this system to emphasize tactical positioning and battlefield control while still keeping the core rules intuitive and easy to follow.

To refine the gameplay loop, we first translated the entire system into a paper prototype. This served as a valuable playtesting phase, allowing us to evaluate the pacing of matches, identify which mechanics worked well, and determine how balanced certain effects felt in practice. The insights gathered from these sessions helped us improve overall gameplay experience.

## Architecture & Gameplay Systems
What makes this project stand out is the combined use of a custom .NET server which communicates with Unity clients. All the game logic is handled on this server as it runs multiple games simultaneously. To this end we wrote our own packet structure, making use of flags and bytes to relay data from card stats to attack targets, with ENet handling the connection logic. 

On top of that we also have a flexible card ability system, utilizing predefined method hooks representing all possible triggers that get called at set points of the gameplay loop. By filling these triggers with logic we can easily implement a variety of card effects, which are recreated from the repository by implementing Domain Specific Language.

The Unity client itself contains no gameplay logic aside from calls to make and packet structure. It cannot influence the game directly, only sending requests to the server and rendering the responses.

## Visual direction & UX
Throughout the project I tirelessly worked every day to draw card after card, ensuring all 101 cards had a distinct appearance. This visual clarity enabled the gameplay loop to progress immensely faster for a smoother experience.

It was important to ensure that cards were readable at a glance, with the player immediately recognizing the card type with its stats. To this end I designed unique card sleeves for the three types: minion, spell and hero. On top of that we added some quality of life to.

## Challenges & Conclusion
This project was an amazing learning opportunity around netcode and game design, where I both had to tackle the challenge of balancing the mechanics and cards, while streamlining online communication to ensure a smooth and consistent game flow.

[HOWEST]: https://www.howest.be/nl
[PAVEL]: https://be.linkedin.com/in/pavel-deleersnyder
[MARWAH]: https://be.linkedin.com/in/marwah-al-shakhli-094566360