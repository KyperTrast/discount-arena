# Discount Arena
A "discounted" version of Rocket Arena 2 for the Quake 2 remaster/rerelease. This mod is barebones and only contains the core gameplay of Rocket Arena 2, where you are given all weapons + ammo for them and you face off against another team in a round-based format. Features that are missing from RA2 are numerous, including:
* No multi-arena support, everyone is on either 1 of 2 teams in one arena, the map itself.
* No round limit, fight until the map timelimit runs out and cycles to the next map
* Score is measured by frags, not damage
* Not much is customizable: you get all base game weapons except the BFG with max ammo (without bandolier/ammo pack), self-damage is always armor only, etc.

Despite the lack of features, I think the core gameplay is fun enough and should last until hopefully OpenRA2 is converted to work with the remaster. This mod works with bots, so you can play strictly off-line or set bot_minClients and start a lobby and have people drop in and out.

## Installing and using
Go to your Quake 2 remaster directory ex.\
Steam: \<steam\>\steamapps\common\Quake 2\rerelease\
GOG: \<GOG\>\Quake II Enhanced\
Create a directory to store the binary ex. "dcarena". Download the release and extract the .dll file to this folder.\
Load up Q2 and in console, type "game dcarena". Now, create a lobby and configure it. Make sure to configure the minimum requirements as listed (a sample dcarena.cfg file is included):
* Select Game Mode: Team Deathmatch
* Set Weapons Stay On (unless you don't mind people restoring ammo)
* Set Frag Limit to 0
* Set Instant Weapon Switch On (optional, but original RA2 had a fast weapon switch)
Once you're finished with settings, start the game and Discount Arena will be loaded.\

## Added variables
* matchstarttime - reused from CTF, pre-round duration in seconds (default: 9)
* arenaroundtime - duration of a round in seconds (default: 60)
* arenaroundcooldown - period between round end and start of pre-round (default: 3)
* g_arena_enabled - enables Discount Arena mod, hasn't been tested with it off... (default: 1)

## Overtime behaviour
I implemented overtime slightly different compared to original RA2. If a round ends by timer, the game will award a point to the team that has more surviving players. If both teams have the same number, then it checks the sum of each team's health (armor is ignored). If that is the same, then no point is awarded.

## Known issues
* Newly added bots (through addbot or bot_minClients) can join a round in progress
* If the last remaining player on a team disconnects and is immediately replaced by a bot, the round can end in a tie

## Other/blog stuff
The core concept of RA2 is pretty simple, so with very little experience I decided to try my hand at seeing if I could replicate the basics of it. I more or less copy-pasted a bunch of things and somehow created this monstrousity...
