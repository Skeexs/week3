---
description: >-
  Congratulations. You've just bought Skeexs Stores, what now? Thats what we're
  going to talk about in here.
---

# Setup

{% hint style="info" %}
First and foremost, we need to install [ox\_lib](https://github.com/overextended/ox_lib/releases/tag/v3.29.0).\
When you've installed that, you'll have to start it before the store script. \
If you don't do that, It won't work because it depends on some ox\_lib functions
{% endhint %}

> If you haven't already downloaded the asset, you can do that [here](https://portal.cfx.re/assets/granted-assets)

## Configuring

Now we have the script installed on our server, but now we need to configure it to our liking.\
How do we do that?\


### Setting up for the framework and inventory

To get all the item and money functions to work we'll need to configure this.

Note that all the framworks and inventories are listed in the Config file\
Frameworks: line 5 in `shared/config.lua`\
Inventories:  Line 6 in `shared/config.lua`

```lua
--- shared/config.lua
Config.Framework = "qb" -- You have, qb, esx and qbox to pick in here
Config.Inventory = "qb_inventory" -- here you select the inventory youre using.
```

