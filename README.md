# Exile Forge Trade

A trade companion tool for **Path of Exile**. It watches the official trade site's Live Search for you, alerts you the moment a matching item is listed, and — if you want — travels to the seller's hideout or completes the purchase automatically.

Exile Forge Trade is built by the same team behind **[Exile Forge](https://github.com/talagio90/GGPK-Modding-Tool)**, a long-running PoE quality-of-life tool.

> This repository hosts **release downloads only**. Source code is not public.

# 📸 Screenshots

![Main Window](https://raw.githubusercontent.com/talagio90/Exile-Forge-Trade-Releases/main/screenshots/Main.png)

![Main Window](https://raw.githubusercontent.com/talagio90/Exile-Forge-Trade-Releases/main/screenshots/Main2.png)

## ⚠️ Before you use this

Exile Forge Trade calls GGG's official trade API using **your own login session** (via a built-in browser login, no password ever touches this app).

- This is a **high-risk feature** with respect to Grinding Gear Games' policy — it can result in **account bans**.
- Exile Forge and its developer take **no responsibility** for any consequences, including bans, from using this tool.
- **You are solely responsible** for your own Path of Exile account while using it. GGG can change their policy at any time.
- Only your machine ID (HWID) is recorded to manage your license — the app **never** collects your password or any GGG account data.

You'll see this same disclaimer inside the app every time it starts, and you must agree to it before continuing.

## What it does

- **Live Search alerts** — track up to several trade search links at once (PoE1, with PoE2 support planned). The moment GGG's Live Search WebSocket reports a new matching listing, you get a desktop toast with the item's name, price, mods, and seller — no need to keep the trade site open.
- **Travel to Hideout** — jump straight to the seller's hideout with one click from the alert, using the same `/whisper` mechanism the official trade site uses.
- **Auto-Buy (opt-in, off by default)** — automatically travels and purchases matching listings for you, with a per-search spend limit and a built-in verification step that checks the item's name and price before clicking, so it doesn't buy the wrong thing. This is the feature the risk warning above is mainly about.
- **Auto-Stash Inventory (opt-in)** — once Auto-Buy has bought a configurable number of items, it automatically opens your stash and sorts everything into the tab(s) you've set up.
- **Browser-based login** — sign in through a built-in browser window, the same one the real trade site uses. No copying cookies or session tokens by hand.
- **Rate-limit aware** — respects GGG's published rate limits and backs off automatically on 429s, with an additional self-imposed connection budget so the tool can't hammer your account's Live Search allowance even if something misbehaves.
- **Auto-reconnect** — if a search's WebSocket connection drops, it reconnects with an increasing backoff, and stops trying (with a clear message) instead of looping forever.
- **Multi-language UI** — English, Vietnamese, Russian, Korean, Simplified & Traditional Chinese, Portuguese, Japanese, Thai, Turkish, and German.

## What it deliberately does *not* do

To keep risk to your account as low as reasonably possible for what is already a high-risk category of tool, Exile Forge Trade never does any of the following: packet-level manipulation, logging into your account with your email/password, reading the game's memory, auto-accepting trades, or force-teleporting your character. Automation is limited to sending the same clicks and keystrokes a human player would, using your own already-authenticated browser session.

## Requirements

- Windows 10/11 (x64)
- [Microsoft Edge WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/) — the app will detect if it's missing and offer to install it for you. Most modern Windows installs already have it.
- A Path of Exile account and an active trade session (you'll log in through the app itself).

No separate .NET installation is needed — the app ships as a single self-contained `.exe`.

## Download

Grab the latest version from the **[Releases](../../releases)** page of this repository.

If GitHub is unreachable from your network, the app also checks for updates directly from our own server and can download the update from there instead.

## Pricing

Exile Forge Trade is currently in a **free beta** — every feature is available at no cost while the tool is being tested by the community. This may change in the future; if it does, existing behavior for already-activated licenses will be communicated in advance through the app's changelog and our Discord.

## Community & Support

Join the Exile Forge Discord for updates, bug reports, and help: **https://discord.gg/77E3ffa547**

## License activation & privacy

The app self-registers a free license tied to your machine's hardware ID on first run — no account creation or email required. It periodically checks in with our license server to keep your session valid; if that check fails (network issues, etc.), a short grace period keeps the app usable until connectivity is restored. See the in-app disclaimer for the full data-handling summary.
