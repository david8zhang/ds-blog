---
toc: true
layout: post
description: Building a Fire Emblem + management sim using React Native
categories: [markdown]
title: Guild Manager Devlog 1
---

# What is Guild Manager?

Guild manager is a tactical turn-based strategy game crossed with a fantasy sports / management simulation game. What do I mean by that? Well, the README I have on the [github repo](https://github.com/david8zhang/guild-manager-v2) sums it up pretty well - Like Fire Emblem crossed with NBA 2k MyGM.

# Why am I making this?

**Ramble alert:** _TL;DR - I basically really like the front office management stuff in sports, and I want to put it in a game with a more exiciting setting_

Around my freshman year of college, I started getting super into the NBA. I had always liked basketball. But I started appreciating sort of the more mundane aspects of the sport I had never even known about before - the front office, free agency, and the offseason trades. Teams would augment their existing squads or build brand new ones by signing free agents. It was fun watching organizations succeed or fail at putting all the pieces together to build a winning basketball team. It was as though they were optimizing a machine, swapping different parts out in hopes of making something that could spit out a championship.

![img](https://sportsarefromvenus.com/wp-content/uploads/2019/09/AP19205743244243.jpg)

The draft was also one of my favorite things to watch. I liked the idea of young kids training, learning and growing to become future superstars. It was like watching a real life RPG. These young prospects, barely college freshmen, would level up (or in some cases, fail to level up) and gain new skills and abilities after every season.

![img](https://media4.giphy.com/media/l4FGp18irsicMWBC8/source.gif)

And that was when I thought to myself, why hasn't all of this front office stuff been adapted into video games outside of the sports simulation genre? Despite being into the NBA draft and free agency, I was never really all that into the MyGM modes or fantasy sports or anything. It all seemed too overwhelming, like to know what to do I would have to study all the players' real life statistics and all that. And then my immersion in the simulation would be shattered when my super star guy in the fantasy team would end up being garbage in real life.

![img](https://usercontent.one/wp/www.newsgroove.co.uk/wp-content/uploads/2019/09/NBA-2K20-MyLeague-Worst-Teams-to-Start-With.jpg)

Plus, game settings can be so much more exciting than the boring ass real world. Why not have it be in a magical fantasy land or a crazy alien planet or something. I wanted to take these sim mechanics and spice it up a little by putting it in a different setting.

# Existing games and inspriation

I actually think the game that all this front office stuff most reminded me of was actually Pokemon. There's trading, battling, and training in Pokemon, much like trading, playing games, and player development in sports. There's also sort of "drafting" in that you "draft" a new pokemon when you catch it. And there's the team building / syngerizing aspect of it as well.

![img](https://i.ytimg.com/vi/hkV4UmFTNiw/maxresdefault.jpg)

But it's not _really_ the same. Unless you're doing nuzlocke, Pokemon is mostly permanent - your mons never grow old and level _down_. You have a ton of control over who you can "draft" unlike in sports. It's the same with trading. Maybe it's just my personal experience, but trading to make your team "better" is sort of pointless if you're just playing the story mode, since the story is so easy. And because it's so easy, the need for having a super strong team aren't really there.

![img](https://i.ytimg.com/vi/z30vEtLo7ag/maxresdefault.jpg)

# Guild-Tycoon, (My first, failed attempt)

My first attempt at making a game that would incorporate all of these elements was a pokemon-like clone. I called it Guild Tycoon - a game where you would manage a guild of fantasy heroes. You would start with a randomly generated team of heroes each with standard RPG-like stats (attack, defense, health, magic, etc.). They would have their own move-pool, which was comprised of both offensive damage-dealing moves and defensive buff moves. The battle system was a 3 vs. 3 turn-based system.

Though I had some familiarity with Unity for 2D game development, I considered myself a full-stack web developer specializing in building front end apps with ReactJS. The game was not going to have that much in the way of real-time graphics updates and was mostly going to be UI anyways. Since I really didn't like the Unity UI system, I ended up just building a web-game using what I already knew best - ReactJS.

After several months of development, I pumped out [this](https://github.com/david8zhang/guild-tycoon)

I encountered a variety of problems. For starters, the game just wasn't very fun. Turns out the pokemon turn based battling system, without all the bells and whistles and fun pokemon designs, was pretty boring. The free agency stuff, with its unintuitive, spreadsheet-like UI was this overcomplicated mess that was not much fun to look at. Ironically, that was one of my main complaints with 2k's MyGM UI. Without any UI flair or polish, it didn't much feel like a game, more like an accounting job.

![img](https://thumbs.gfycat.com/CheerfulPopularAmoeba-small.gif)

From a technical perspective. I bit off a bit more than I could chew when trying to implement all the Free Agency, Trading, and Drafting functionality. There were so many bugs and problems with all the mechanics I had tried to cram in. I didn't put enough thought into how all the classes and modules would be organized, so the code became spaghetti and hard to modify.

Frustrated, I decided to just salvage the pokemon battle mechanics piece, the one part I had actually spent a lot of time carefully designing and testing. I took that and spun that out into its own little mini-game. I even made it so that you could upload your own "pokemon" and movesets in this admin / CMS tool.

[Random battler](http://random-battler.s3-website-us-west-1.amazonaws.com/)

[Random battler Admin tool](http://random-battler-admin.s3-website.us-east-2.amazonaws.com/)

Of course, this wasn't really what I had in mind. After spending months trying to make this work, I got too ambitious and scope creeped the project to the detriment of the code quality. I should have started small, or at the very least put some more time into the design of all the different systems I was implementing.

# Guild Manager v.2, my second (and current) attempt

After a few months of working on a few other unrelated projects, I'm now working on a second version of this game. I'm building on React Native this time, since I spend more time playing NBA 2k20 Mobile than any other game, in all honesty.

For the second attempt, I've made a few changes:

- The battle system is now a turn based Fire Emblem style system. This really opens up more strategizing and gameplay variety

- The teams are somewhat pre-set. I wanted to maybe incorporate a narrative to this game, so I have a set list of teams and logos to give the game some more personality instead of just having RNG take care of everything

- Characters can level up their stats after every match. This adds a sense of progression. Later, they may also regress after they surpass a certain age

- There's actually a post-season playoff bracket. Increases the stakes and makes it more exciting

- There will be "announcers" for matches and also outside of matches to add some added flair and personality to all the things that are happening.

As I'm writing this, I've actually been developing the game for over three months. I'm a bit of a ways from just starting out now. But I figure it might be good to document the dev process so that I don't make the same mistakes I did with the first iteration. I'm planning on recounting every major feature I developed over the past 3 months in a series of blog posts. This one will be the first in that series, although this one is mostly just background information and motivation for why I'm even building this.

I'm thinking as a rough outline for how I'll document the features I developed:

1. Setting up regular season matchups
2. Battle system 1 - Turn based movement
3. Battle system 2 - Attacking, deaths, scoring
4. Battle system 3 - Skills
5. Battle system 4 - Respawning and invulnerability
6. Battle system 5 - Post match stats, stat gains
7. Playoff Bracket implementation
8. Offseason training camp
9. Contract management
10. Art and animation

Anyways, stay tuned for the next blog post, where I'll be talking about setting up the game, team rosters, and initializing regular season matchups between teams.
