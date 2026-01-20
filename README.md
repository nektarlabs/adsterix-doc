---
description: Welcome to your team’s developer platform
layout:
  width: wide
  title:
    visible: false
  description:
    visible: false
  tableOfContents:
    visible: false
  outline:
    visible: false
  pagination:
    visible: false
  metadata:
    visible: true
metaLinks:
  alternates:
    - https://app.gitbook.com/s/2AwfWOGBWBxQmyvHedqW/
---

# Developer Platform

<h2 align="center">Adsterix</h2>

<p align="center"><em>A market for social attention</em></p>

<p align="center"></p>

<p align="center"></p>

{% columns %}
{% column %}
#### Embed **Farcaster-native, onchain** ads anywhere in seconds

Monetize **any miniapp, wallet, or interface** with **native, onchain Farcaster ads**—live in under **5 seconds**. To render an ad, all you need is the **cast hash** of a Farcaster cast.

**How it works**

1. **Create an ad** using the **Adsterix** miniapp:\
   [https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix](https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix)
2. **Open the ad’s cast** on **Farcaster**.
3. Click the **three dots (⋮)** in the top-right corner.
4. Select **“Copy cast hash.”**

That’s it—embed the cast hash anywhere to display a **Farcaster-native, onchain ad** and start monetizing instantly.



<a href="https://app.gitbook.com/o/ezBFtKnWRx7ww8t6YBho/s/FkyK3sCcyFjm2ras2DOD/" class="button primary" data-icon="rocket-launch">Get started</a>&#x20;
{% endcolumn %}

{% column %}
{% code title="index.js" overflow="wrap" %}
```javascript
import { AdsterixWidget } from "@nektarlabs/adsterix-widget"

function App() {
  return <AdsterixWidget castHash="0xbf59074b94c5fd1c6b3ee1a7201708da3f60998f" />
}

```
{% endcode %}
{% endcolumn %}
{% endcolumns %}
