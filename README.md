> # NitroSniperGo

[![GitHub release](https://img.shields.io/github/release/Vedzaa/NitroSniperGo.svg?style=flat)](https://github.com/Vedzaa/NitroSniperGo/releases)
[![GitHub All Releases](https://img.shields.io/github/downloads/vedza/NitroSniperGo/total?style=flat)](https://github.com/vedza/NitroSniperGo/releases)
[![Views](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://github.com/Vedza/NitroSniperGo&title=Views)](https://github.com/Vedza/NitroSniperGo)     
[![Build Status](https://travis-ci.com/Vedza/NitroSniperGo.svg?branch=master)](https://travis-ci.com/Vedza/NitroSniperGo)

<a href="https://www.buymeacoffee.com/Vedza" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="32" width="140"></a>
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/Vedza/NitroSniperGo/tree/heroku)

Discord Nitro sniper and Giveaway joiner in Go.

![Screenshot](screenshot.png)

#### Features 
* Multiple accounts support to claim on one main account
* Optional Counter for max Nitro activations
* Optional main account sniper to only claim code from alts
* Cooldown for # hour(s) after redeeming # nitro code(s)
* Duplicate code detection
* Optional Giveaway joiner and only Nitro Giveaway joiner
* DM host with custom message if giveaway won
* Optional Privnote sniper
* Optional custom status
* Optional Invite link sniper
* Optional Counter for max server joined
* Cooldown for # hour(s) after joining # server(s)
* Webhook support with good only mode that report only codes applied and giveaways won.
* Blacklist servers to not join any giveaways on these servers
* Custom delay to join giveaways, servers and DM giveaways host

#### Usage

Edit `settings.json`
``` json5
{
  "tokens": {
    "main": "Nz...", // Main token
    "alts": [ // Alts token
      "Nz..."
    ]
  },
  "status": {
    "main": "", // online, offline, idle, dnd, invisible
    "alts": "invisible" // online, offline, idle, dnd, invisible
  },
  "nitro": {
    "max": 2,   // Max Nitro before cooldown
    "cooldown": 24,  // in Hour
    "main_sniper": true // Enable or not Nitro sniper on main account (It will only claim code from alts)
  },
  "giveaway": {
    "enable": true, // Enable or not giveaway joiner
    "delay": 5, // Delay in second before joining giveaway
    "dm": "Hey, I won a giveaway !", // DM sent to giveaway host, leave empty to not send any dm
    "dm_delay": 10, // Delay in second before sending DM
    "blacklist_words": [ // Don't join giveaways with these words
      "black",
      "test",
      "ban"
    ],
    "whitelist_words": [ // Only join giveaways with these words
      "white",
      "nitro"
    ],
    "blacklist_servers": [ // IDs of servers you don't want the giveaway joiner to work on
      ""  
    ]
  },
  "invite": {
    "enable": true,
    "delay": {
      "min": 10, // Minimum delay in minute before joining server
      "max": 20  // Maximum delay in minute before joining server
    },
    "max": 10,    // Max Servers joined before cooldown
    "cooldown": 6 // in Hour
  },
  "privnote": {
    "enable": false // Enable or not Privnote sniper
  },
  "webhook": {
    "url": "",
    "good_only": false // Will trigger webhook only when you applied a Nitro code or won a giveaway
  }
}
```

You have multiple choices to run the sniper : 

- [Deploy on Heroku](https://heroku.com/deploy?template=https://github.com/Vedza/NitroSniperGo/tree/heroku) (Free 24/7)
   * Deploy
   * Resources -> enable worker
   * See logs in More -> View logs

- Download the latest [release](https://github.com/Vedza/NitroSniperGo/releases)

- Compile it yourself
  ``` sh
  go mod download
  go build
  ./NitroSniperGo
  ```
 
#### How to obtain your token
https://github.com/Tyrrrz/DiscordChatExporter/wiki/Obtaining-Token-and-Channel-IDs#how-to-get-a-user-token

#### Known issues
* `error unmarshalling READY event` is not a problem, it just happens because you're doing a self bot
* It looks like Discord added a security feature where your token change every time but also expire, that might be the reason why the sniper doesn't work after some time or if you get an unauthorized error when sniping Nitro
* Some welcome bots mention giveaways that might cause a false positive
* Privnote sniper makes the program crash sometimes, disable it in settings if that happens to you until I find a solution

#### Disclaimer
This is against TOS and can get your account banned, especially if you run multiple instance at the same time and/or claim too many Nitros in a too short amount of time. Use it at your own risks.

> *If you like my sniper consider putting a star on this repo !*
