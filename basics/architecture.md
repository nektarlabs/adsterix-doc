---
icon: microchip
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
    - https://app.gitbook.com/s/yE16Xb3IemPxJWydtPOj/basics/editor
---

# Architecture

Adsterix is built as a **Farcaster-native, onchain market for social attention**.

The core idea is simple but powerful:

> **Farcaster lives on Optimism.**\
> **Adsterix lives on Base.**\
> **Adsterix verifies Farcaster state trustlessly across chains.**

No indexers. No offchain assumptions. Just cryptographic proofs.

***

<figure><img src="../.gitbook/assets/Screenshot 2026-01-20 at 10.28.37.png" alt=""><figcaption></figcaption></figure>

### Core chains

* **Base** → Adsterix market, auctions, payouts, permissions
* **Optimism** → Canonical Farcaster contracts and state
* **Ethereum** → Shared trust anchor via the Beacon Chain

***

### High-level flow (cross-chain)

1. Users interact with Adsterix through the **MiniApp**
2. All economic logic executes on **Adsterix contracts (Base)**
3. When Farcaster state is needed (FID, custody address, cast data):
   * Adsterix **proves Optimism storage on Base**
   * Using Ethereum as the **root of trust**

This makes Farcaster data **natively usable inside Base contracts**.

***

### Cross-chain verification: how it works

Adsterix uses **storage proofs** to verify Farcaster contract state from Optimism directly on Base.

#### Step 1 — Ethereum Beacon Root (on Base)

Base exposes the **Ethereum Beacon Root** onchain.

This allows Adsterix contracts to:

* access a trusted Ethereum state root
* without trusting relayers or oracles

***

#### Step 2 — Optimism State Root (via Ethereum)

Optimism periodically commits its **state root** to Ethereum using the\
`AnchorStateRegistry` contract.

From the Ethereum state root, Adsterix can:

* prove the **Optimism state root**
* fully onchain

***

#### Step 3 — Farcaster storage proofs (Optimism → Base)

Once the Optimism state root is known:

* Adsterix verifies **specific storage slots**
* inside **Farcaster contracts on Optimism**
* using Merkle storage proofs

This allows Base contracts to safely read:

* FID → custody address mappings
* registry data
* Farcaster-native identifiers

All **without trusting an indexer**.

***

### Why this matters

This design turns Farcaster into a **verifiable data layer**, not just a social app.

#### Benefits

* 🔐 **Trust-minimized**\
  Farcaster data is _proven_, not fetched
* 🔗 **True cross-chain composability**\
  Base contracts can depend on Optimism state safely
* 🧠 **Protocol-level guarantees**\
  Auctions and permissions can depend on Farcaster identity
* 🚫 **No backend trust assumptions**\
  Offchain services can improve UX, but cannot lie

***

### Example: verifying an FID on Base

To resolve a user’s custody address from an **FID**:

1. Identify the Farcaster `IdRegistry` storage slot on Optimism
2. Generate a **storage proof** against the Optimism state root
3. Verify:
   * Ethereum Beacon Root → Ethereum state root
   * Ethereum proof → Optimism state root
   * Optimism proof → `IdRegistry` storage slot
4. Use the verified value inside Adsterix contracts on Base

Result:\
**Base contracts can reason about Farcaster identity natively.**

***

### Design philosophy

Adsterix treats:

* **Farcaster** as the social identity layer
* **Base** as the economic settlement layer
* **Ethereum** as the cryptographic anchor

Together, they form a **cross-chain attention market** that is:

* onchain
* composable
* censorship-resistant

