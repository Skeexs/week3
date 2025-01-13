---
description: >-
  Here's all the events for the client, ex. what'll trigger on a players client
  when he gets an invoice etc.
---

# Client Events

## onInvoiceReceived

<pre class="language-lua"><code class="lang-lua"><strong>---@param invoiceData Invoices;
</strong><strong>RegisterNetEvent("invoices:client:onInvoiceReceived", function(invoiceData)
</strong>    local invoiceAmount = invoiceData.amount;
    local description = invoiceData.description;
    local dueDate = invoiceData.dueDate
    local sender = invoiceData.sender
        
<strong>    -- this will trigger on the receivers client when receiving a invoice
</strong>    print(string.format("You got sent a invoice for %s with description %s", invoiceAmount, invoiceDescription))
    -- Here I would trigger a notification or something instead of printing. 
end)
</code></pre>

{% hint style="info" %}
**Note**\
These events will not ever contain any exclusive data that could be used to exploit the script.\
These are just for the sake of listening when a player receives or sends.
{% endhint %}

## onInvoiceSent

```lua
---@param invoiceData Invoices;
RegisterNetEvent("invoices:client:onInvoiceSent", function(invoiceData)
    local invoiceAmount = invoiceData.amount;
    local description = invoiceData.description;
    local dueDate = invoiceData.dueDate
    local reciever = invoiceData.reciever
    
   print(string.format("You sent a invoice for %s to %s", invoiceAmount, reciever))
    -- Here I would trigger a notification or something instead of printing. 
end)
```

