---
title: Of Maps and Monsters, the Right way to Populate a World
date: 2018-05-11T21:04:42-07:00
author:
  name: Ted Tschopp
  url: https://www.tedt.org/
  avatar: https://www.tedt.org/img/thumb3.jpg

description: 
excerpt: |
   This work is the beginning of a collection of notes on Monsters and Maps.  In the future I will split this out into several different sections.  I wanted to start wtih what I had here and start working my thoughts out while getting some of this out of my head and into a place I can review and look at. 

layout: post
guid: dd7cf62d-9947-46e7-b436-7aafb10027e6
permalink: /2018/05/11/Of-Maps-and-Monsters-the-Right-Way-to-Populate-a-World/
image: 	wp-content/uploads/2018/05/Ebstorfer-stich2.jpg
image-credits: Ebstorf Map by Gervase of Ebstorf 
categories:
  - Role Playing Games
  - Maps
  - Monsters
  - Draft
draft-status: notes
mathjax: true
---

# Contents
{:.no_toc}

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}


# Notes

This work is the beginning of a collection of notes on Monsters and Maps.  In the future I will split this out into several different sections.  I wanted to start wtih what I had here and start working my thoughts out while getting some of this out of my head and into a place I can review and look at.    

# Maps

## Encounter Scale ( )

## Providence Scale (1 Mile Per Hex)
* http://blogofholding.com/?p=6741

## Kingdom Scale (6 Mile Per Hex)


## Continent Scale (60 Mile Per Hex)


## Stellar Scale
In Fantasy Role Playing Games it can not always be assumed that there is a Stellar scale.  When at this scale, the goal isn't to provide a map to allow travelers on the surface of the land mass a means of navigation.  Instead it is to provide an overview of what the landmass looks like from space.  


$$ 

\documentclass[10pt]{article}
\usepackage{pgf,tikz}
\begin{document}
\begin{tikzpicture}
   \newdimen\R
\R=2.7cm
   \draw (0:\R)
   \foreach \x in {60,120,...,360} {  -- (\x:\R) }
 -- cycle (360:\R) node[right] {(3,2,1)}
 -- cycle (300:\R) node[below] {(3,1,2)}
      -- cycle (240:\R) node[below] {(1,3,2)}
 -- cycle (180:\R) node[left] {(1,2,3)}
-- cycle  (120:\R) node[above] {(2,1,3)}

           -- cycle  (60:\R) node[above] {(2,3,1)};
\end{tikzpicture}
\end{document}



d = \sqrt{h(2R+h)} 

$$

* Spherical
* Flat
* Ring
* Sphere
* Hollow World
* Alien Geometries 



# Monsters
One of the aspects of making a sandbox type of role playing game is that many times the monsters that the players run into do not make sense.  These rules are things I am trying to put down to make a computer controlled map generator that can be used to simplify the planning process for people running a game. A lot of this information was inspired and taken from around the web and expanded upon.

## Monster variation
Today in most role playing games monsters are reduced to a handful of stats that do not make them unique.  The first activity that I think is needed for a database of monsters to run into is that these monsters need to have random stats.  Not every player character or human today has the same strength.  The basic idea here is that there is some variation.  Many times this variation is reduced to simplify bookkeeping and that makes sense.  Today however we have rather powerful computers that can work on handing some of that bookkeeping.  Therefore I propose that attributes be replaced with a set of dice.  


### Stats for Exceptional Members of the Encounter

#### Bonuses to stats vs. Bonuses to skill and combat rolls on a given stat

#### Types of exceptional Members

* Leader, Alpha, Commander
* Giant, Monstrous
* Dire, Prehistoric
* Magical, blessed


#### Types of Subnormal Members of the Encounter
* Child, Grunt, Beta, 
* Dwarf, Miniature, Pygmy, Tiny, Teacup, Pixie
* Dire, Prehistoric
* Magical, Cursed


## Close Calls

### Tracks
What sort of tracks do these monsters leave

### Remains
Abandoned lairs, camps, prey or victims

### Markings
What sort of ways do these monsters mark their territory

## Not so Close Calls

### Their Lair 
Perhaps they are social.  Perhaps they are anti-social.  What happens when you meet them in their typical lair. 

### Encountered away from their Lair
Traveling, Hunting, Gathering, Fighting, Trading, Exploring, Patrolling, Scouting?

#### Travel 
Distance they can Travel in one day.  How long will they remain away from their Home. What sort of Travel?

Do they travel by:
* Land
* Air - close to ground
* Air - within ranged combat
* Air - within sight
* Air - Above sight
* Water
* other?

Why are they traveling
* Traveling
* Hunting
* Gathering
* Fighting

### Habitat
What sort of habitat does this creature live and travel in.  

## External Reactions
How do these creatures typically react to others

## How to hunt them
How difficult are these creatures to hunt and what sort of skills and equipment are needed.

## How to cook / eat them
Once they are hunted, how are they cooked.  Are they edible?  Are the poisonousness?  Are they a delicacy? 