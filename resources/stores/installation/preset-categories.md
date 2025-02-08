---
description: >-
  Here we'll learn how to create a preset category. Not the hardest thing in the
  world.
---

# Preset Categories

In the shared/config.lua, we have a table called Config.Categories. This is what I call preset categories, it's simply for quick configuration of new stores that's going to use the same categories.\


Looks like this when you have downloaded it for the first time.

```lua
Config.Categories = {
    ["247"] = {
        {
            label = "General",
            id = "general",
            products = {
                { label = 'Vehicle Repair Kit', itemId = 'repairkit', price = 4, },
                { label = 'Rubber',             itemId = 'rubber',    price = 4, },
                { label = 'Copper',             itemId = 'copper',    price = 4, }
            }
        },
        {
            label = "Food",
            id = "food",
            products = {
                {
                    itemId = 'sandwich',
                    price = 14,
                    label = "Bread",
                    description = "10 Slices of bread",
                }
            }
        }
    },

    ["weaponshop"] = {
        {
            label = "Pistols",
            id = "weapons",
            products = {
                {
                    itemId = 'weapon_pistol',
                    label = 'Glock',
                    description =
                    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
                    price = 2500,
                    image =
                    'https://upload.wikimedia.org/wikipedia/commons/b/b4/Glock_17_MOD_45154998_%28Transparent%29.png'
                }
            }
        },
        {
            label = "Rifles",
            id = "rifles",
            products = {
                {
                    itemId = "weapon_carbinerifle",
                    label = "Carbine Rifle",
                    description = "En karbin rifle",
                    price = 20,
                    image = "https://r2.fivemanage.com/LRlfVgIK7NNsxmVbS4FS5/images/carbine-rifle.png"
                }
            }
        },

        {
            label = "Ammo",
            id = "ammo",
            products = {
                {
                    itemId = "ammo_pistol",
                    label = "Pistol Ammo",
                    description = "10 bullets",
                    price = 20,
                    image = "https://r2.fivemanage.com/LRlfVgIK7NNsxmVbS4FS5/images/ammo-pistol.png"
                }
            }
        }
    }
}
```

Nothing crazy, right?\
Now where going to go over what these do and how it functions etc.\


## Category interface

When creating a new category, it's not just passing in whatever you want.\
You'll need to follow my interface to get it to work.\


```lua
--- Category interface
{
    label = "Category Name", --The name in the ui that everybody will see 
    id = "category_name", -- This one i recommend naming it something unique
    products = {} -- this one i will show in the next example
}
```

It's nothing more than that, but the products need to be there, else it will be hard to buy the items from the shop, right? 😅\


## Product interface

Now where here, the products for the category\


```lua
--- Product interface
products = {
    {
        itemId = "the_spawn_name_of_item", -- The spawn name of the item, like "bread", or such
        label = "label_in_the_ui", -- Label of item in the shop
        description = "not_shown", -- Leave this
        price = 10, -- How much money that will be removed on purchase of item
        image = "", -- If you don't want the inventory image of the item
    }
}
```

Now you're good to go, now you can configure your own preset category for the next shop!\
But, wait?! You're maybe asking how to use this category?\
I'll teach you\


## How do i use it?

As we saw in the beginning, we saw a Config.Categories table, where there were `["247"]`\
This will be the name we'll use for indexing/calling for the categories.\
So when creating new category, you do like this

```lua
["your_category_name"] = {
    --- insert the categories in here
}

--- and when using it in Config.Shops

Config.Shops = {
    { categories = "your_category_name" }
}
```

Thanks for coming to my ted talk, now you're a proffesional at this.&#x20;
