---
description: >-
  Now when you're here, I guess you want to create a new theme for another shop.
  Here I will guide you on how it works, don't worry.
---

# Creating Themes

## Creating your first theme

* Navigate to `shared/themes`
* Create a new file, preferrably named something that makes sense, i'll call this `blackmarket.json`
* Now that we've created our `blackmarket.json` file inside of `shared/themes` Open the file
* Copy and paste this code

<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "primary": "",
    "secondary": "",
    "button_color": "",
    "border": "",
    "gradient": ""
}
</code></pre>

You're probably wondering, "but Skeexs, how do I know what to put in here", and I fully understand you\
In this file I use rgba() formatting, and these are r, g, b, a. I.e `255, 0, 0, 1` this will display a fully red, not transparent at all.\
\
If you have a hex color you want to use, use [THIS ](https://rgbacolorpicker.com/hex-to-rgba)website to convert it and paste the numbers WITHOUT the "rgba()", only the numbers

* Now you're done with the theme configuration
* When wanting to use this on a shop, add `theme = "filename"` to the shop and it will apply by it self

If you still don't understand you could always joing my discord and open a ticket and ask :)
