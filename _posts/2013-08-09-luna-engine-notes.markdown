---
layout: post
title:  "[E] Luna Engine Notes"
date:   2013-08-09 10:54:00
tags: ['rpg', 'maker', 'vx', 'ace', 'luna', 'engine']
description: "Some notes you should know when using Luna Engine for RPG Maker VX Ace."
---

Luna Engine, an GUI overhaul scripts series for RPG Maker VX Ace, is going to be released soon. 
In this post, I will note something you should know before using it for your projects.

1. **Installation:**  
For the best performance, you should place scripts in this below order:
  * Configurations for both Menu and Battle Luna, any change in order does not cause any problem.
  * Lunatic Configurations for Menu Luna.
  * Battle Luna Core.
  * Menu Luna Core.
  * Battle Luna Add-ons:  
     - Actor Commands.
     - Damage Popup.
     - Image Popup
     - Escape Command.
     - Skill & Item List.
     - Disable Party Commands.
     - Circular Bars.
     - Shaking HUD.
     - Lunatic Face.
  * Menu Luna Add-ons:
     - Grid Status.
     - Lunatic Background.

2. **Compatibility:**  
Because of the huge changes to RGSS3 in Luna Engine, it would cause some compatibility matters 
to other scripts (mostly big Battle System and GUI-relating scripts). Fortunately, due the large 
usage of Yanfly Engine, Kread Scripts, we decided to make a compatible patch for Luna Engine and 
those above Engine. Of course, Symphony Engine is included in compatible patch as well.
  * **Kread Scripts:**  
  Put them below Luna Engine but above Kread Compatible Script.  
  For Animated Battlers, in Battle Luna Configuration, find `:animation_on_hud` and set to `false`.
  * **Symphony Engine:**  
  Put them below Luna Engine.  
  For Battle Symphony, in Battle Luna Configuration, find `:animation_on_hud` and set to `false`.
  * **Yanfly Engine:**  
  Except YEA - Core Engine and YEA - Battle Engine, put them below Luna Engine but above Yanfly Compatible Script. For those 2 exceptions, put them above Luna Engine.  
  For YEA - Free Turn Battle, in Yanfly Compatible Script, find `:arrow_battler` and set to `true`.
  * **Other sideview scripts:**  
  In Battle Luna Configuration, find `:animation_on_hud` and set to `false`.

3. **Configuration:**  
The configurations for Luna Engine are huge, so you should check the note we made in configurations carefully and read some GUI presets we made for more information before asking us why and how. However, there are still some notes we have to write there:
  * **Resources:**  
  For configuration that use an external picture instead of default draw, please put them in Graphics/System folder.
  * **Options:**  
  There are some options in configuration which would cause some confusion to users so we have to note them there.
     - `:z` This option is used for layering, higher value will be drawn above other.
     - `:center` This option appears in Battle Luna (inside `BATTLER_HUD`) and Menu Luna (Main Menu configuration, inside `BATTLER_STATUS`), set this to `true` to center battler HUDs.
     - `:cursor` This option appears in Menu Luna configuration, set this to `false` to disable default cursor of window.
     - `:padding` This option appears in Menu Luna configuration, this will change the spacing between window's border and window's contents. Default value is `12`.
  * **Lunatic Options for Menu Luna:**  
  These options are only available for users who have some coding knowledge. For more information, please read notes in each Lunatic Configuration script and our premade GUI.  
  To disable Lunatic Options, you shouldn't remove those lunatic scripts, instead, you should put 
  this line inside each method `return nil` or remove all contents inside each method.