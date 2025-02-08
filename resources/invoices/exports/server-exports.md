---
icon: memo
description: >-
  This is where you'll find all the Server Exports, these will only be available
  on the server and can not be called on the client. For security purposes,
  never trust the client as they say ;)
---

# Server Exports

## Get Received Invoices

### QBCore Example

```lua
--- server.lua
--- This is how you'll do it on your QBCore server.
local characterId = QBCore.Functions.GetPlayer(source)?.PlayerData.citizenid
local fetched, invoices = exports["skeexs_invoices"]:GetReceivedInvoices(characterId)

--- This will return true if the player has any invoices to fetch.
if fetched then
    --- this will only print if "fetched"-variable is true, and it has fetched.
    print("Found invoices", invoices)
    
    --// add your code here //
else
    print("Couldn't find any invoices for player " .. characterId)
end
```

### ESX Example

```lua
--- server.lua
local characterId = ESX.GetPlayerFromId(source)?.GetIdentifier()
local fetched, invoices = exports["skeexs_invoices"]:GetReceivedInvoices(characterId)

--- This will return true if the player has any invoices to fetch.
if fetched then
    --- this will only print if "fetched"-variable is true, and it has fetched.
    print("Found invoices", invoices)
    
    --// add your code here //
else
    print("Couldn't find any invoices for player " .. characterId)
end
```

## Get Sent Invoices

### QBCore Example

```lua
---server.lua
local characterId = QBCore.Functions.GetPlayer(source)?.PlayerData.citizenid
local fetched, invoices = exports["skeexs_invoices"]:GetSentInvoices(characterId)

--- This will return true if the player has any invoices to fetch.
if fetched then
    --- this will only print if "fetched"-variable is true, and it has fetched.
    print("Found invoices", invoices)
    
    --// add your code here //
else
    print("The player hasn't sent any invoices " .. characterId)
end
```

### ESX Example

```lua
local characterId = ESX.GetPlayerFromId(source)?.GetIdentifier()
local fetched, invoices = exports["skeexs_invoices"]:GetSentInvoices(characterId)

--- This will return true if the player has any invoices to fetch.
if fetched then
    --- this will only print if "fetched"-variable is true, and it has fetched.
    print("Found invoices", invoices)
    
    --// add your code here //
else
    print("Couldn't find any invoices for player " .. characterId)
end
```

## Create Invoice

### Example

```lua
--- @class Invoices;
--- @field public amount number
--- @field public recipient string
--- @field public dueDate number

---@type Invoices
local invoiceData = {
    amount      = 9999,
    recipient   = "ABC123X",
    dueDate     = "2025-01-15" --- don't use this, use os.time() or os.date() instead
}

---@param invoiceData Invoices;
---@return Invoices;
local invoice = exports["skeexs_invoices"]:CreateInvoice(invoiceData);

local invoiceId = invoice.id;           --- id of the invoice.
local amount = invoice.amount;          --- the price of the invoice
local recipient = invoice.recipient     --- returns the characterId/job that was input in "invoiceData"
```

This will be particularly useful for lets say if you want to make this Invoice script compatible with your Jobpanel/Jobsystem.

## Get Invoice from UUID

### Code example

```lua
--[[ 
    Here the parameter/variable Id needs to be a valid Invoice Id
    Ex. from a newly created Invoice or just fetched from the database;
    Only use if you're familliar with this.
--]]
local found, invoice = exports["skeexs_invoices"]:GetInvoiceFromId(id);
```

## Delete invoice

### Code example

```lua
local removed, message = exports["skeexs_invoices"]:DeleteInvoice(id)
```

### Explanation

Here we need a valid id, a valid invoice that will say. It fetches the invoices from the database to then delete it from database.\
Then return if it has been removed, and returns a message, if you want to use that.\
\
A valid use case for this could be as following:

### Use case

```lua
local found, invoice = exports["skeexs_invoices"]:GetInvoiceFromId(id);

if found then 
    print("I found a valid invoice, i want to remove it")
    
    local invoiceId = id --- here you could use invoice.id also to further validate youre using a valid invoice id
    local hasRemoved, message = exports["skeexs_invoices"]:DeleteInvoices(invoiceId) 

    --- this will print how it went with removing the invoice
    print(message)
end
```

