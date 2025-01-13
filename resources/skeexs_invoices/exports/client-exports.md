---
icon: memo
description: >-
  Not trusting the client as much, thats why only a handful of exports is
  compatible here.
---

# Client Exports

If you're interested in more client sided exports, I suggest you join my [Discord ](https://discord.gg/fruaAkwNfA)and open a ticket, there we can see if your suggestion is worth adding..

<pre class="language-lua"><code class="lang-lua"><strong>--- Use this to open the UI from another script.
</strong>--- Only on the client;
--- @return any
<strong>exports["skeexs_invoices"]:Open()
</strong></code></pre>

## Close Interface

```lua
--- Use this to close the UI from another script.
--- @return any
exports["skeexs_invoices"]:Close()
```
