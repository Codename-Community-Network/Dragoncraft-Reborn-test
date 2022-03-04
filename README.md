Project MMO Frequently Asked Questions:

Is there a PMMO wiki?
https://harmonised7.github.io/minecraft/pmmo/Features.html

Where is the PMMO config or saved data?
minecraft/config/pmmo-common.toml where common config is stored in 1.15+
minecraft/config/pmmo.conf where common config is stored in 1.12
minecraft/config/pmmo/*.json - where json config is stored
world/data/pmmo.dat - where player data is stored

Is there an easier way to navigate the Common Config?
https://harmonised7.github.io/minecraft/pmmo/Config.html

How do I add a translation? 
https://projectmmo.oneskyapp.com/collaboration/project/174961

I have removed requirements, but they are still there
You are most likely experiencing Auto Value Generation, which comes in 2 types: Standard, and Dynamic. Each can be disabled in the config file

How do I disable the spam/numbers/moving numbers/etc
You can move any part of the GUI, excluding the text at the top left, which can be toggled with the PMMO GUI key (TAB by default)
If you’re not happy still, you can remove the xp drop numbers
Config -> GUI -> Disable xp drops for the numbers at the top

I want to gain more/less xp in all skills
You should modify the xp formula in the config. Here's a guide:
https://docs.google.com/spreadsheets/d/1s-rPg5H1bojVmoneI4yFy7FDZOi5qu4nt_wz2tk2cRg/

I want the maximum level of skills to be higher
You should modify the maxLevel in the config.

I want to gain more/less xp in a skill 
Go to /config/pmmo/xp_multiplier_dimension.json, and under “all_dimensions” entry, add “combat”: 1.5

this will mean that all gained combat xp is multiplied by 1.5, effectively boosting the xp by 50%

I want to disable a skill
Go to /config/pmmo/xp_multiplier_dimension.json, and under “all_dimensions” entry, add “combat”: 0

I want to create my own skill
Go to /config/pmmo/skills.json, and follow the format of other custom skills to add your own

How do I remove a type, or all types of requirements?
Go to /config/pmmo-common.toml, and find configs such as “reqWearEnabled” and set them to false. They all follow the same pattern.

How do I add or modify level requirements, or other pmmo related data?
Highly recommended to check this https://docs.google.com/document/d/1OaNxk1I3PTBfdGV5PlHqUpaENTkr49Tg26YhK3N5zTQ/edit?usp=sharing

My [any Anvil action] is [breaking in any way], what can I do? (This is surprisingly common with mods)
set anvilHandlingEnabled to false in config

Can I change my GUI without restarting the game?
Absolutely!
Press P (by default) to open up the GUI, and then go to Settings -> GUI

How do I modify/add/remove items/biomes/mobs affected by PMMO?
Go to /config/pmmo/, and modify/add/remove values!

Is there a way to take out All the items from a mod into a addData or Json format so that I wouldn’t have to do them all manually?
Yes, do the command /pmmo debug searchRegistry items [search term, such as minecraft:]
and then check your console (or /logs/latest.log) for the output! It comes in 3 formats, text, Json, and Json Builder

Can you port Project MMO to Fabric?
I now offer a Patreon goal to port Project MMO to Fabric. Do not get your hopes up, however, as the goal is intentionally high, due to how Big Project MMO has gotten, and the fact that I do not use Fabric, nor intend to.

I don’t want to loose xp upon death, what can I do?
Go to /config/pmmo-common.toml, change deathXpPenaltyMultiplier, 0 = no xp lost

I want to loose all levels upon death, because I feel confident to not die, or any other reason
Go to /config/pmmo-common.toml (or from inside GUI), wipeAllSkillsUponDeathPermanently

How do I add crops/ores/logs to have an extra chance?
In the json config, you must enter not the seed, not the dropped item, but the block that will drop the items itself, for example: If you want to add a chance for Carrots, minecraft:carrot is incorrect. If you look at the right side of the F3 screen while looking at a carrots plant, it says “minecraft:carrots”, which IS correct, because that is the block that drops them. Same for ores, it must be the ore, not let’s say a diamond.

I'm not gaining xp
Are you in survival mode? If not, does your server have pmmo installed? If both of those are true, please report in #issues-n-bug-reports 



I don't like a certain thing about this mod
Check out the config files, you'd be surprised how many things you can change.
Still don't like something? Let me know in #ideas-n-suggestions!
Visual representation of Config: https://harmonised7.github.io/Config.html

Are you still going to update 1.12?
Nope, only bug fixes, if they're major enough. 

will you do X?
If I like X, which I probably do, I will do it eventually, however, please bare in mind that I am attending University full time, and I will only be less available within the next 3 or 4 years.

However*2, this definately does not mean that I am abandoning this mod by any means, this mod is a great hobby, and something I love dearly.

Edit: yup, Uni + work is quite the time consuming combination that I am currently in!

How do I add Ore/Log/Plant extra chance?
Same place as level requirements, and same idea. `ore`, `log`, `plant`.
Ore, Log, and Plant are dependant on Mining, Woodcutting, and Farming, respectively.

How do I add xp rewards for breaking blocks?
Same place as level requirements and extra chances, but this time it's `xp_value_break`
Any amount of skills are accepted, in same way as level requirements.

Are there any tools to help me out with building a config? (For many entries, or just to prevent screwing up in general)
Yes, type “.m pmmotools” in the Project MMO Discord Server (where you likely found this document)
There are several tools
one lets you build the config (Feel free to contact me, Harmonised, for the up to date version if you want to change all the current vanilla values all in one go)
Highly recommend checking out ".m pmmodata" command also

Are Forge Tags supported?
Only in 1.16 and above, they are marked with a # before the tag, such as #minecraft:ice

How do I level up building faster?
Building xp depends on the block Hardness.
Higher Hardness value means more xp for placing the block.
Obsidian is the highest hardness value Vanilla block.
Enable Advanced Tooltips to see the Hardness value of the block by hovering over it inside an inventory. F3+H enables it. 

How do I up any skill faster in general? 
By default, - Nether provides xp bonuses to Combat and Endurance.
-Certain items give xp bonuses, such as leather, chainmail, gold armor/weapons, ender star, heart of sea.
-The more damage you deal, the faster you train Combat.
-The more damage you take, the faster you train Endurance.
-The more you break the relevant to the skill blocks (example: Stone/Ore for Mining), the more xp you get in that skill.

How do I level up a skill, such as Magic or Fame?
Some skills, like Magic, are unused by default and are included in Project MMO for modpack developers to use in their modpacks. For information on how to gain experience in these skills, you should ask the developer of the modpack you are playing.
Additionally, magic can be gained from any weapon that appears Melee, but causes damage from long distance, and weapons marked as magicWeapon in item_specific.json
