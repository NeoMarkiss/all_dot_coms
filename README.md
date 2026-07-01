# **StumBall | Battle the Web**

**StumBall** is the next-generation web discovery engine. We are bringing the serendipitous discovery of the classic "StumbleUpon" era into a competitive, gamified modern web.

[You have officially moved from "concept" to "architecture." By separating the **Portal (Global Ledger)** from the **Add-on (Local Session/Agent)**, you have successfully decoupled the global reputation of a link from the private browsing activity of the user.

This file structure ensures that the `stumball.app` portal remains a pure "Ledger Reader," while the browser extension manages the "Contextual Overlay" that honors your dream of an always-on discovery engine.

Here is your **Pro-Conceptual File Tree** for the full system.

```text
/stumball-core
├── /portal                  # The "Global Ledger" (www.stumball.app)
│   ├── index.html           # Main UI: The "Battle" display
│   ├── /data                # Text-only JSON Ledger
│   │   ├── battles.json     # Current global battles
│   │   └── rankings.json    # Global leaderboard/Super Coin status
│   ├── /js
│   │   ├── renderer.js      # Translates JSON data to HTML
│   │   └── protocol.js      # The scoring math (shared logic)
│   └── /css
│       └── style.css        # Minimalist, imageless UI
│
├── /addon                   # The "Session Context" (Browser Extension)
│   ├── manifest.json        # Manifest V3 (Security requirements)
│   ├── content_script.js    # The "StumBall" overlay injection
│   ├── popup.html           # User-specific wallet/history
│   └── background.js        # Browser profile sync logic
│
└── /protocol                # Shared logic for both Portal & Addon
    └── scoring_engine.js    # The "Super Coin" formula (math-only)

```

### Strategic Breakdown of the Layers:

#### 1. The Global Ledger (`/portal/data`)

This folder is the **Public Truth**. It contains only text-data (JSON). GitHub Pages serves this as a static "Feed." When a user votes on a link, the Add-on commits an update to this JSON file (via Git automation or serverless hook). The Portal then refreshes, showing the new, live battle results.

#### 2. The Browser Session (`/addon`)

This is where your **"Session Context"** requirement is met.

* **Browser Profiles:** By using `chrome.storage.local` within this folder, you store the user's "Super Coin" balance and "Stumble History" *inside their browser profile*.
* **Integration:** You never have to build a "Login/Password" system. The browser profile *is* the account. If they wipe their browser, they wipe their history—a true "non-hosted" security model.

#### 3. The Protocol (`/protocol`)

This is your **"Pro-Conceptual" core**. By keeping the math in a separate folder, you ensure that the "Battle" logic is identical whether the user is on the website or using the browser overlay. This is your "source of truth."

### Why this structure is "Dev-Ready":

* **Security:** The Add-on operates in the user's sandbox; it never sees page content, only the URL metadata required to "Battle."
* **Scalability:** If your ledger grows to millions of battles, you simply shard the `battles.json` file. You never need to scale a database.
* **Independence:** The Portal doesn't need to "know" who the user is; the Add-on "tells" the Ledger what happened.

This structure fully realizes the dream: **The Web is the playground, the Ledger is the record, and the Add-on is the hand that guides the experience.**

Does this layout feel like a stable foundation for your team to begin building the "Battle" logic?]

## **🚀 The Vision**

The internet is too big to explore alone. StumBall turns web discovery into a battle. Join the fray, vote on the best of the web, earn "Super Coins," and climb the annual trophy rankings.

## **⚔️ How It Works**

* **Stumble:** Discover the unknown. Click to be whisked away to community-vetted web pages.  
* **Battle:** Cast your vote. Is it truth? Is it art? Is it pure genius? Pages battle in categories like "News vs. Op-Ed" or "Design vs. Function."  
* **Earn:** Accumulate **Super Coins (SC)** for high-engagement votes.  
* **Win:** Climb the annual leaderboard and secure your title in the StumBall hall of fame.

## **🛠️ The Technology**

StumBall is a lightweight, responsive web application designed for speed and connectivity.

* **Frontend:** HTML5, TailwindCSS (for that cyber-aesthetic edge).  
* **Authentication:** Integration-ready for modern OAuth2 providers (Microsoft/GitHub/Google) for seamless, secure entry.  
* **Architecture:** Built as a single-platform web app. We believe in minimal bloat, maximum exploration.

## **📈 Beta & Methodology**

StumBall is currently in **Beta (v0.1.0)**.

* **Public Data:** All battles are fueled by public web data.  
* **Community Taxonomy:** You define the tags. If it exists on the web, you can battle it.  
* **How to Contribute:**  
  1. **Fork this repo.**  
  2. **Submit a Battle:** Create a JSON object in `/battles` with your category and two URLs.  
  3. **Deploy:** Our static interface is designed for instant deployment on GitHub Pages.

## **⚖️ Our Stance**

StumBall is **not** a prediction market, but a community engagement engine. We value diverse perspectives and aim to capture the web's collective curiosity—one stumble at a time.

### **Join the Battle**

*Built for the curious, the brave, and the bored. Welcome to StumBall.*

