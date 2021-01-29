---
title: "Working With Godot 2, Developing VRMN NVZN"
date: 2021-01-29
tags: ["games", "design", "godot"]
# photo:
# description:
draft: false
---

As my latest videogame, VRMN NVZN, comes to its near finish, I have been thinking a lot about my experience developing it. I spoke on a [podcast][4] about the game, and in one question the host asked me, "how did this project start?" It sent me backwards through time:

2018\. I am searching for a partner to work with in the Godot engine, roughly right around the time of release of Godot 3. I met Chris DeBoy, a pixel artist with previous work in 3D modelling and texturing with Blender. We started working on a game called [Star Raid][1]. It had 3D graphics, an extremely simple flight model, and a really good targeting system.

Star Raid was my first real endeavor into 3D games and Godot, in general. The architecture was... terrible. I can't express in words how poorly written some of the code was, and how the project was oriented. The issue with Godot is that while it is very easy and simple to get things working, it is very hard to get things *right*. You need to study Godot project and code architecture, make sure you use inheritence and signals properly. There are some minor rules which are simple to know, but challenging to apply. All the pitfalls of object oriented design are present.

A new developer may end up with a project that has spaghetti architecture -- scripts jump around to other nodes local in the scene; the paths hardcoded into the script files. After working on two or three games in Godot, and close to a year of total experience, I think I finally know how I should organize my projects. The next game I make will be gently coded together, sewn from the silk of a butterfly's fingertips. A sweetness amalgamated from pain and frustration. How beautiful.

We found Star Raid to be too big of a project, and canceled it. We could have simplified the goals, so that our work was not wasted. Almost any project that is too complicated can be simplified. We wanted an open-world, dynamic fights, DOOM-style boots-on-ground combat, and many types of AI enemies -- from ground units, to trucks, turrets, mechs, and other jets. These very difficult objectives made developing Star Raid tireless and ultimately defeating. Our expectations were far too high for what we could do in a reasonable time. We could have done away with everything but air-to-air combat and predefined scenarios (levels). We would have sold a game! Not wasted our time!

Later, I picked up Chris' older project from around 2016: VRMN NVZN. He based it on some kind of scrolling shooter template. The original project had asteroids and one very bland level. It was a good starter project, the branding was there and it was ready for additions. But one issue stuck out like a sore thumb: it was based on Godot 2.1.7. And not only that, but also used features only found in that version of Godot, like bitmap fonts and atlases. One attempt was made at updating the codebase to Godot 3.0. After a few days, I failed miserably. Scene files broken, dependency hell, code had to be rewritten, the iconic bitmap font had no place in Godot 3 -- [bitmap fonts backlogged to Godot 3.1][2] because the importer was "really complex and hacky."

After days of unresolved errors, I decided it was not worth porting the game to a newer version of the engine, and I very happily continued using Godot 2. It required a further understanding of the engine. Of anyone, I should be the most appreciative of the improvements 3 brought, as opposed to what I had. Everyone had already upgraded to Godot 3, and as the days passed they slowly forgot about all the little improvements over the past versions. It left every developer still using Godot 2 slightly in the craphole because nobody could seem to be bothered that you had a question or concern about an older version of the engine! I asked on the Godot Discord server a little before the release of 3.1 about a problem I was having in my game. Nobody bats an eye at an old version of an engine -- they see it as the most insignificant thing to exist in their life, at that moment in time. The only relief users of Godot 2 get are in the few forum threads and scattered relics of documentation. Unfortunately for them, it is the least documented version of the engine.

I pressed on with the development of [VRMN NVZN][3]. I spent many hours programming the new and essential features: the rail system, player controls, checkpoints, (an admittably terrible) save system, and powerups which are used very seldom in the final game. Although, I plan to make a minor adjustment which makes powerups more essential to the experience! Chris did several more of the assets including the bees and the wasps before eventually quitting the development. He went to work on his own funky title I can't remember the name of. Truth be told he is quite quick to give up on projects! When I needed art, it was too slow to ask him for help, so I did it myself. That was when I added lasers and two of the first levels.

I took two breaks during the development of VRMN NVZN. Each may have been a few months at most. These were due to changes of interest and also loss of appetite. Recently, I have garnered the attention of friends, family, and strangers with my game! I am extremely fortunate people seem to adore it, and are so supportive of my work. I always had these doubts about my abiltiies -- that I wasn't making something people could find enjoyment in. This attention has truly revived my passion for the game, and given me faith in the game's success. I tell my closest friends, "This is my last trial. I have to finish the game now."

Now just two weeks later, I'm on the podcast trying to explain the idea of this game -- one I can barely compose anymore. I designed the entire game, mostly on-the-fly, but if you ask me what it's about, it's hard to get past, "Well it's a scrolling shooter." This game has gone through about three story reiterations. I don't want to say anything about the story because I barely remember what's true. I don't know how the game will end yet. I work on each level in order, and finish it before starting the next. In each level, I decide the story and program cinematics. That's the pipeline.

I hope that everything I work on isn't for waste.

[1]: https://fivemoreminix.itch.io/star-raid
[2]: https://github.com/godotengine/godot/issues/10184#issuecomment-342136133
[3]: https://fivemoreminix.itch.io/vrmnnvzn
[4]: https://open.spotify.com/episode/7IaHpzEXUJhvzvR6v1e9Jh?si=ENxXuuALQQ2qAh62Njba8w
