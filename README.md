# TF2_Server_UpTime_Restarter
This plugin will automatically restart your server after a set period of no activity.

If a server runs for long enough, then a detrimental jitter effect can take place. I theorize this is due to floating point errors and is a rather nasty bug. It is really quite bad for server reputation when new players join a low (or empty) population of players in a server, only to encounter this.

I originally wrote this plugin back in 2017, but only now updated it in 2022 and I am making it public. I welcome new features if anyone wishes to do so.
GitHub upload done in 2024, using 15th July 2022 - v1.0.1.

-

Installation:
Just put the .smx file into your "..\tf\addons\sourcemod\plugins" folder and either restart your server, restart the map or just run the command "sm plugins load server_uptime_restarter" via the rcon console.

Default behavior:
Server will run for an hour, then when the server becomes completely empty it will perform a restart. The plugin will wait until the server is completely empty.
There is a grace period of 1 minutes when loading a new map, so that players can join in if they exist, thus preventing an unwarranted restart.

In the case of a server actually having at least 1 player for a whole day, a server restart will be forced anyway.

If set to restart with a minimum number of players instead, then a warning countdown will be shown in chat to warn all players before restarting.

Cvars:
PHP Code:
// Use this if you wish to stop plugin functions temporarily.
// -
// Default: "1"
// Minimum: "0"
SUR_Enable

// Minimum time in seconds before restart attempt.
// -
// Default: "3600"
// Minimum: "60.0"
SUR_UpTime_Min

// Time in seconds before server restart is forced, regardless of player count.
// -
// Default: "86400"
// Minimum: "60.0"
SUR_UpTime_Max

// At least this many players will cause the restart to be delayed. Spectators are not counted.
// -
// Default: "1"
// Minimum: "1.0"
SUR_MinPlayers

// Display restart warning message in chat.
// -
// Default: "1"
// Minimum: "0"
SUR_Warn_ShowChat  

Version v1.0.1 does not use a custom config file, so should any cvar changes be desired, these configuration lines must be placed in your server.cfg file if you wish for them to be permanent.
