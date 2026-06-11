# TierTagger Mod

Minecraft 1.21.1 (Fabric) mod that fetches PvP tier data from the TierTagger API and displays it above player heads.

**Made by Mirzecatafa**

---

## Setup

### 1. Configure API URL

After first launch, a config file is created at:
```
.minecraft/config/tiertagger.json
```
Edit it and set your deployed API URL:
```json
{
  "apiBaseUrl": "https://your-app.replit.app"
}
```

### 2. In-game commands

| Command | Description |
|---|---|
| `/kit <kitname>` | Select active kit (shows that tier above all players) |
| `/kit` | Show currently selected kit |
| `/tiertagger refresh` | Manually re-fetch tier data from API |
| `/tiertagger clear` | Hide all tier tags |

**Valid kit names:** `sword`, `axe`, `uhc`, `nethpot`, `crystal`, `mace`, `potion`, `smp`

### 3. Display format

When a kit is selected, every player's name tag changes to:
```
{icon}{tier} | {username}
```
Example: `⚔ HT2 | zlelouch`

---

## Build from source

Requirements: JDK 21+, internet connection (first build downloads Gradle & Minecraft)

```bash
# Clone repo
git clone https://github.com/YOUR/tiertagger-mod
cd tiertagger-mod

# Download Gradle wrapper (first time only)
gradle wrapper --gradle-version=8.8

# Build mod JAR
./gradlew build
```

Output: `build/libs/tiertagger-1.0.0.jar`

Put the JAR in your `.minecraft/mods/` folder alongside Fabric Loader + Fabric API.

---

## Icons

Icons are defined in `TierDataManager.java` using Unicode emoji as placeholders.
To use custom PNG icons, replace the unicode characters with texture-based rendering.

---

## Requirements

- Minecraft 1.21.1
- Fabric Loader ≥ 0.16.5
- Fabric API
