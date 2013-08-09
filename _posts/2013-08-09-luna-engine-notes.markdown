---
layout: post
title:  "[E] Luna Engine Notes"
date:   2013-08-09 10:54:00
tags: ['rpg', 'maker', 'vx', 'ace', 'luna', 'engine']
description: "Some notes you should know when using Luna Engine for RPG Maker VX Ace."
---

Luna Engine is series of scripts that overhauls the GUI for RPG Maker VXAce. This post notes something you should know before using it for your projects.

1. **Installation:**  
For the best performance and avoiding any issues, you should place scripts based on the order below:
  * Configurations for both Menu and Battle Luna. You can put both Menu and Battle Luna's configuration script on top of each other and it won't cause any problem.
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
Luna Engine might not be compatible with Battle System and GUI-related scripts. This is because of the script's nature to provide flexibility towards customization. Fortunately, we made this compatible with the majority of Yanfly Engine,  Kread Engine and the Symphony Engine.
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
We have provided necessary comments and notes in the configuration script itself. Please check the notes and observe carefully. We will also provide GUI templates for reference and possibly closer to your goal. However, there are some things you should remember:
  * **Resources:**  
  If you want to use images for your GUI, please put them in Graphics/System folder.
  * **Options:**  
  Here are some technical terms that will help you understand Luna Engine better.
     - `:z` This option is used for layering, the higher value will be drawn/displayed above another.
     - `:center` This option appears in Battle Luna (inside `BATTLER_HUD`) and Menu Luna (Main Menu configuration, inside `BATTLER_STATUS`), set this to `true` to center battler HUDs.
     - `:cursor` This option appears in Menu Luna configuration, set this to false to disable the default cursor of a specific window.
     - `:padding` This option appears in Menu Luna configuration, this will change the spacing between window's border and window's contents. Default value is `12`.
  * **Lunatic Options for Menu Luna:**  
  These options are only available for users who have some coding knowledge. For more information, please read the notes in each Lunatic Configuration script and our premade GUI. 
  To disable Lunatic Options, you shouldn't remove those lunatic scripts, instead, you should put 
  this line inside each method `return nil` or remove all contents inside each method.