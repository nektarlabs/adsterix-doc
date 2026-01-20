---
icon: bolt
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
metaLinks:
  alternates:
    - https://app.gitbook.com/s/yE16Xb3IemPxJWydtPOj/getting-started/quickstart
---

# Quickstart

**Adsterix** works for **everyone** in the **Farcaster** ecosystem. Choose the path that fits you and get started in minutes.

***

### 🌟 You’re an influencer

**Monetize your influence automatically**

Turn your social reach into passive income.

1. Open the **Adsterix** miniapp:\
   [https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix](https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix)
2. Enable **Autopilot** 🚀
   * Autopilot allows Adsterix to cast **on your behalf** when a user or brand wins an auction
   * Each promotional cast stays live for **30 minutes**, then is automatically deleted
3. Go to the **Sell** page.
4. Set a **starting price**.
5. Forget about it — and **earn** 💰

Your attention is now an onchain asset.

***

### 🧑‍💻 You’re a developer

**Monetize your miniapp, wallet, or interface**

Display **Farcaster-native, onchain ads** anywhere with a single cast hash.

#### Steps

1. Create an ad using the **Adsterix miniapp**:\
   [https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix](https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix)
2. Open the ad’s cast on **Farcaster**.
3. Click the **three dots (⋮)** in the top-right corner.
4. Select **“Copy cast hash.”**
5. Use the copied value as the `castHash` prop in your app 🧩
6. `npm install @nektarlabs/adsterix-widget`

```typescript
import { AdsterixWidget } from "@nektarlabs/adsterix-widget"

function App() {
  return <AdsterixWidget castHash="0xbf59074b94c5fd1c6b3ee1a7201708da3f60998f" />
}
```

That’s it — if you can render a cast, you can render an ad.

***

### 📣 You’re a user or brand

**Promote your content**

Boost visibility where attention already lives.

1. Open the **Adsterix** miniapp: [https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix](https://farcaster.xyz/miniapps/nOlHtdHWXJ6H/adsterix).
2. Select an available ad slot.
3. Place a **bid** 💸
4. If you win, your content is **promoted automatically** via a Farcaster-native cast.

No banners. No middlemen. Just attention.
