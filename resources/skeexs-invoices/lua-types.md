---
description: >-
  Here's all the types I use. Lua is not typesafe at all, but this is a way I
  try to make it more typesafe and help my IDE recognize params etc when coding.
  Just a more comfortable coding environment.
icon: person-digging
---

# Lua Types

## Invoices Class

```lua
--- @class Invoices;
--- @field public new fun(o: table): Invoices
--- @field public id number
--- @field public amount number
--- @field public recipient string
--- @field public dueDate number
```

