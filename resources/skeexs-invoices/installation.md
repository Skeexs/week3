---
description: >-
  Learn how to install skeexs_invoices. This will help you if you have any
  questions or just don't know what to do.
icon: arrow-down-to-square
---

# Installation

{% hint style="danger" %}
### HEADS UP

To get this script to work properly, I need you to install [ox\_lib](https://github.com/overextended/ox_lib/releases/tag/v3.27.0)\
Start this script before the resource, like this:\


```
// In your server.cfg
ensure ox_lib
ensure skeexs_invoices

// DO NOT DO THIS
ensure skeexs_invoices
ensure ox_lib
```
{% endhint %}

### Install the asset

> First and foremost, when buying a script from Skeexs Scripts you'll have to download the asset from either [https://keymaster.fivem.net](https://keymaster.fivem.net) or [https://portal.cfx.re](https://portal.cfx.re), from there you will get a asset named skeexs\_invoices.

### Setting it up

> Now you need to set it up for your own server, this will not take long. \
> You get a `invoices.sql` file, to get this script to work you need to run this. After running this we're almost done.

### Configuring to work with your server

> Now I suppose you have extracted the file into your resources folder, started ox\_lib and skeexs\_invoices\
> \
> Now its time to configure it to your liking.\
> \
> In `src/config/main.lua` you will find the main config options\
> Here you can set the language for the script, currently only supporting **Swedish and English**\
> \
> **Change these to how you want them.**\
> **I would recommend to have** `Config.Debug = false` **if you dont want any un-needy prints in your console.**
>
> ```lua
> -- src/config/main.lua
> Config = {};
>
> --- This is the framework you're using, either 'esx' or 'qb'
> --- @type string
> --- @default 'esx'
> Config.Framework = 'esx'
>
> -- Use this only when getting support from me or if you know what you're doing
> -- This will print unneedy information to the console, which can be useful for debugging but not for normal use
> --- @type boolean
> Config.Debug = false;
>
> -- Change this to your language
> -- If theres a language you want me to add, please feel free to DM me on Discord with said language and translations
> -- https://discord.gg/JRMnUJaS
> --- @alias Lang 'en' | 'sv'
> --- @type Lang
> Config.Lang = 'en';
>
> ```

