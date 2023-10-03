# Discount Arena
A "discounted" version of Rocket Arena 2 for the Quake 2 remaster/rerelease. This mod is barebones and only contains the core gameplay of Rocket Arena 2, where you are given all weapons + ammo for them and you face off against another team in a round-based format. Features that are missing from RA2 are numerous, including:
* No multi-arena support, everyone is on either 1 of 2 teams in one arena, the map itself.
* Not much is customizable: you get all base game weapons except the BFG with max ammo (without bandolier/ammo pack), self-damage is always armor only, etc.

Despite the lack of features, I think the core gameplay is fun enough and should last until hopefully OpenRA2 is converted to work with the remaster. This mod works with bots, so you can play strictly off-line or set bot_minClients and start a lobby and have people drop in and out.

## Installing and using the mod
From the Github page, in the Releases -> Latest section on the right-hand side, download `discount-arena.zip`.
Go to your Quake 2 remaster directory ex.\
Steam: \<steam\>\steamapps\common\Quake 2\rerelease\
GOG: \<GOG\>\Quake II Enhanced\
Create a directory to store the binary and name it `dcarena`. Extract `discount-arena.zip` here and you will see a .DLL file. Then, use one of the two methods listed below to load the mod.
### Load the mod manually
Load up Quake 2 and then press the tilde key (~) to open the console. Here, type `game dcarena` (no quotes) then hit Enter. Now, create a lobby and select `Team Deathmatch` as the game mode and turn on `Instant Weapon Switch` (optional, but original RA2 had a fast weapon switch). Configure the rest of the settings as desired, Discount Arena will be loaded once you start the game.
### Run the config file
Get a copy of the "dcarena_bots.cfg" file from the source code above, and place it into your rerelease\baseq2 folder. Load up Quake 2 and then press the tilde key (~) to open the console. In here, type `exec dcarena_bots.cfg` (no quotes) then hit Enter. This will create a local game with the below:
* set `game dcarena`
* set `g_instant_weapon_switch 1`
* immediately load q2dm1 with `map q2dm1`
* load 5 bots with `bot_minClients 6`

If you see "Discount Arena" in the bottom left then the mod has loaded. You can immediately quit the map and create your own lobby, and modify the config file for future use.

## Added variables
* matchstarttime - reused from CTF, pre-round duration in seconds (default: 9)
* dca_roundtime - duration of a round in seconds (default: 60)
* dca_roundcooldown - period between round end and start of pre-round (default: 3)
* dca_warmuptime: duration of intermission/warmup time in seconds (default: 20)
* dca_roundscorelimimt: number of rounds a team needs to win (default: 10)
* dca_useready: require players to ready up before starting (default: 0, OFF)
* g_arena_start_health: Starting health (default: 100)
* g_arena_start_armor: Starting armor (default: 100)
* g_arena_enabled - enables Discount Arena mod, hasn't been tested with it off... (default: 1)

## Overtime behaviour
I implemented overtime slightly different compared to original RA2. If a round ends by timer, the game will award a point to the team that has more surviving players. If both teams have the same number, then it checks the sum of each team's health (armor is ignored). If that is the same, then no point is awarded.

## Known issues
* Scoreboard is sorted by frags instead of damage done

## Other/blog stuff
The core concept of RA2 is pretty simple, so with very little experience I decided to try my hand at seeing if I could replicate the basics of it. I more or less copy-pasted a bunch of things and somehow created this monstrousity...
