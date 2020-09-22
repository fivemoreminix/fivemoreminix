---
title: "To Make an MMO Life Simulator -- Thoughts on One Hour One Life"
date: 2020-09-21T21:23:00-05:00
tags: ["games", "theory", "design"]
draft: false
---

One Hour One Life is captivating to me. I keep the game installed on my computer, but rarely play it. I think so highly of it, but despise its design all the same. How can this terribly drawn and stinky game be such a masterpiece in my mind?

It begins at its core theory: players depend upon players, to make a society.

First you should know the game is written from scratch in C++. I think that's fantastic -- the game runs well, it's stable at its core. The game is top down, with a hand-drawn art style. The whole world is laid out into tiles, and only a single entity can be in one tile. So you can have 10 tiles on screen, but a single plate on each tile. When you're carrying something like a plate, and you want to pick up food, you have to run around to find some tile that isn't occupied so you can put down the damn plate to save yourself from starvation. It's really hectic.

Each minute in the game is a year of your character's life. Outstanding idea -- one hour one life. You really do have enough time to make your contribution to the world -- if you weren't so busy screwing around with confusingly drawn entities. Sounds are literally just noises made by the developers mouth. I get the artistic style, but it's not immersive.

![](/images/ohol/ohol.jpg)

*The art style is good, but cars literally sound like \*chugga chugga chugga chugga\*... Also that screenshot isn't realistic; there would be about fifty random items laying all over the place, and two skeletons.*

Let me cut to the chase, because I'm boring myself of talking about *what's wrong* with the game, rather than *what could be improved*.

## 1. Smaller Tiles
Because One Hour One Life's world is just tiles with a very very simple stacking system, and nowhere to put shit, it makes the real struggle of civilizations become space. If a new game focused on a game world with chests, cupboards, and other spaces which you opened dialogs with to see their inventories -- then space would not be much of an issue. It would feel more comfortable.

Going with a system where you could have multiple entities per tile, or just making tiles smaller, then you could have much more intricate buildings and civilization layouts.

Also, multi-levels. That would be so awesome! Imagine there being basements and homes with multiple stories.

## 2. Detailed Combat (And Better Interactions)
There's currently one way to kill someone in One Hour One Life, for the past few years: pick up a knife by left clicking, hold ctrl and left click somebody and they're dead. Now you can't drop the murder weapon for a whole minute. That's the system of combat... Just sub-par. But that's a by-product of the simple system of movement and interaction in the game.

Imagine instead, being able to aim a bow and pull the string back before you shoot, watching the arrow fly, but the arrow is deflected by the shield they are carrying at their side. That's the kind of top-down Mount & Blade combat I want to see! Make the game require more skill than a point and click adventure, but less than Mount & Blade.

## 3. Change The Perspective?
Let's rule out some awful ideas for perspectives, and see which ones are do-able and maybe really intriguing for this kind of game:

 * 2D top-down - Definitely works... combat and multiple floors make this a challenging experience, though. Great on simplicity and performance.
 * ~~2D side-scroll~~ - Think Terraria as an MMO... not really going to work. Combat is nearly the same, multiple-floors is great, but the world becomes about the ground and the sky? Nope.
 * 2D isometric - Works, may be a better experience than 2D top-down.
 * 3D top-down - Now we're cooking. Combat would be cool, multiple floors is about the same, performance worse, simplicity much worse. Still an interesting experience.
 * ~~3D third-person~~ - With how much you're interacting with items and food up-close, it's not a great idea for camera angles.
 * 3D first-person - If it existed, it would be so badass. Think Mount & Blade as a life sim MMO... Just an ungodly great idea. Would be painfully difficult to develop, as models and textures need to be good quality for seeing up close. Entire world would come to life, and combat could be rivetting. A great challenge, but an even greater outcome if done well by many people.
 * 2.5D isometric - Get the best of both worlds! I guess. This could be implemented in a hundred different ways, but I imagine there could be a 3D environment with 2D characters. Or at least realistically drawn 2D world so that it has shadows and feels like a 3D world. Think Factorio. A fantastic idea.

![Screenshot of Mount & Blade](/images/ohol/mountnblade.jpeg)

*Screenshot of Mount & Blade*

![Screenshot of Factorio and its amazing shadows](/images/ohol/factorio.jpg)

*Screenshot of Factorio and its amazing shadows*

## 4. The Crafting
The current system of crafting in One Hour One Life is actually pretty unique and not bad. You can only combine two items at a time, and you get directions to craft a final product in the lower right corner of the screen. You can press the '/' key and type an item name to get the instructions for crafting that item. Overall not bad, but it's also pretty confusing because you can't see all items well in the art style and perspective. I was going to go into a whole section describing a better system of crafting before realizing that the current system is great after an art style and perspective redesign.

A lot of things in the game are not immediately apparent, and so it's more like a puzzle game because of the combination of awkward crafting and interaction. For example, I was alone and trying to make food for myself. I know you can put a flat rock over a fire to turn it into a place to cook until the fire burns out, and you can't move the rock again. So I tried throwing a flat rock on a blazing fire. Nothing, tried on a lessening fire, nothing. Then when I was confused and losing hope, the fire burned out into hot coals, and I was able to put the flat rock on the fire. I took my goose egg and it went on the hot rock, immediately becoming an egg. Now what? Well, I tried picking it up directly. Nothing. I tried taking a plate and picking it up, nothing. Nothing worked to get the cooked egg off the rock, and after about ten seconds, it became burnt, and glued to the rock.

That's the kind of awkward puzzle survival game we're experiencing here. IRL, I could have burnt myself but at least pushed the egg off the "hot" rock onto my plate I had prepared. And I could have thrown a flat rock over a fire regardless of whether it's blazing or not. Least to say, **the barrier of entry to understanding the game's awkward crafting system keeps new players out of the game.** Especially me, because I have no desire to learn anymore. I feel like I learned nothing playing then, for the last 30 minutes.

## So Where Does One Begin?
If you chose a 2D or 2.5D perspective, then a WebAssembly target would be perfect. Otherwise, a native target would be good. This kind of game would really benefit from the use of a game engine, but could also be done pretty well in a language of choice from scratch, like the author of One Hour One Life did. When Godot 4 is released, it will be a good choice as a WebAssembly framework. Until then, the most reliable option is from scratch with any language that can compile to Web Assembly.

## Conclusion
I really do want to make a game from my vision that utilizes all of the new designs I've mentioned here. If you are interested in working with me on a game, please send me an email or message me using the contact info on my website.
