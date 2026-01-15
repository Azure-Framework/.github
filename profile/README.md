<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:007BFF,100:FFFFFF&height=190&section=header&text=AZURE%20FRAMEWORK&fontSize=62&fontColor=FFFFFF&fontAlignY=35&animation=fadeIn&desc=THE%20MODULAR%20FIVEM%20ECOSYSTEM&descAlignY=60&descSize=18&descColor=EAF3FF" />
</p>

<p align="center">
  <img src="https://imgimp.xyz/images/Stoic-2025-06-28_06-06-19-685f865b90047.png" width="140" height="140" />
</p>

<h1 align="center">Azure Framework</h1>

<p align="center"><b>Lightweight • Modular • Discord-Powered • vMenu Optional</b></p>

<p align="center">
  <a href="https://github.com/Azure-Framework"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-OPEN-FFFFFF?style=for-the-badge&labelColor=007BFF" /></a>
  <a href="https://azurewebsites.xyz/framework/"><img alt="Website" src="https://img.shields.io/badge/Website-OPEN-FFFFFF?style=for-the-badge&labelColor=007BFF" /></a>
  <a href="https://azurewebsites.xyz/docs/guides/framework/guide.html"><img alt="Docs" src="https://img.shields.io/badge/Docs-OPEN-FFFFFF?style=for-the-badge&labelColor=007BFF" /></a>
  <a href="https://discord.com/invite/tBg2U6CTHE"><img alt="Discord" src="https://img.shields.io/badge/Discord-JOIN-FFFFFF?style=for-the-badge&labelColor=007BFF" /></a>
</p>

<p align="center">
  <img alt="version" src="https://img.shields.io/badge/VERSION-v2.0.0-007BFF?style=for-the-badge&labelColor=FFFFFF" />
  <img alt="fivem" src="https://img.shields.io/badge/FIVEM-READY-007BFF?style=for-the-badge&labelColor=FFFFFF" />
</p>

> **Yes — these sections can be auto-collapsed.**  
> Remove the `open` attribute from `<details>` to have them collapsed by default.

---

## :rocket: AZURE FRAMEWORK
> :sparkles: *One ecosystem. Three ways to run your server.*

<details>
<summary><b>🧭 Modes (click to expand)</b></summary>

### :white_check_mark: FULL FRAMEWORK (No vMenu)
- :school_satchel: **Inventory** — usable items + clean UI  
- :shopping_cart: **Shops** — configurable buy/sell  
- :red_car: **Player Vehicles** — ownership + garages/parking  
- :moneybag: **Economy + Banking** — accounts, money flow  
- :bust_in_silhouette: **Character Systems** — modern experience + UI  

### :white_check_mark: HYBRID (Framework + vMenu)
- :zap: Keep vMenu for what you want  
- :jigsaw: Add Azure modules as you grow  
- :school_satchel: Inventory • :shopping_cart: Shops • :red_car: Owned Vehicles • :moneybag: Banking  

### :white_check_mark: vMenu MODE (Lightweight)
- :joystick: vMenu-driven with Azure features layered in  
- :shield: **Discord role integration** — perms + departments  
- :technologist: **Admin tools/UI** — staff controls + reports  
- :police_car: **MDT** • :chains: **Jailing** • :clapper: **Loading UI** + more  

</details>

---

## ✅ What This Repo Provides (Az-Framework)
- :moneybag: **Economy helpers** (cash/bank operations + client updates)  
- :busts_in_silhouette: **Discord identity + permissions hooks**  
- :briefcase: **Job helpers** (job reads + role logic)  
- :car: **Vehicle parking helpers** (parked vehicle tracking exports)  
- :sparkles: **Client helpers** (HUD refresh hooks)  

---

<details>
<summary><b>📦 Dependencies (click to expand)</b></summary>

### Required
- **oxmysql**
- **ox_lib**
- **ox_target**

### Optional (only if you use the feature)
- **screenshot-basic**
- **fivem-appearance**
- **MugShotBase64**
- **glitch-minigames**

</details>

---

<details>
<summary><b>🚀 Resource Start Order (click to expand)</b></summary>

```cfg
ensure oxmysql            # (NEEDED)
ensure ox_lib             # (NEEDED)
ensure ox_target          # (NEEDED)

ensure screenshot-basic   # (IF YOU ARE USING)
ensure fivem-appearance   # (IF YOU ARE USING)
ensure MugShotBase64      # (IF YOU ARE USING)
ensure glitch-minigames   # (IF YOU ARE USING)

ensure Az-Framework       # (NEEDED)
ensure Az-CharacterUI     # (IF YOU ARE USING)

ensure [Framework]        # (ALL OTHER Az-* RESOURCES GO HERE)
```

### Recommended Folder Layout
```text
resources/
  Az-Framework/
  Az-CharacterUI/
  [Framework]/
    Az-Banking/
    Az-Admin/
    Az-Jailing/
    Az-MDT/
    Az-Loading/
    Az-DMV/
    ...etc
```

</details>

---

<details>
<summary><b>🧰 Exports (click to expand)</b></summary>

### :moneybag: Economy / Money
```lua
exports['Az-Framework']:addMoney(src, amount)
exports['Az-Framework']:addMoney(amount)

exports['Az-Framework']:deductMoney(src, amount)
exports['Az-Framework']:depositMoney(src, amount)
exports['Az-Framework']:withdrawMoney(src, amount)
exports['Az-Framework']:transferMoney(src, targetSrc, amount)

exports['Az-Framework']:GetMoney(discordID, charID, function(cash, bank) end)
exports['Az-Framework']:UpdateMoney(discordID, charID, newCash, function(ok) end)

local money = exports['Az-Framework']:GetPlayerMoney(src)
exports['Az-Framework']:sendMoneyToClient(src)
exports['Az-Framework']:claimDailyReward(src)
```

### :busts_in_silhouette: Identity / Admin / Character
```lua
local job = exports['Az-Framework']:getPlayerJob(src)
local discordId = exports['Az-Framework']:getDiscordID(src)

exports['Az-Framework']:isAdmin(src)
exports['Az-Framework']:logAdminCommand(src, commandName, extraInfo)

local char = exports['Az-Framework']:GetPlayerCharacter(src)
local name = exports['Az-Framework']:GetPlayerCharacterName(src)
```

### :car: Parking / Vehicle Helpers
```lua
exports['Az-Framework']:RegisterParkedWorldVehicle(discordID, netId, plate)
exports['Az-Framework']:UnregisterParkedWorldVehicle(netId)
exports['Az-Framework']:GetParkingDiscordId(src)

exports['Az-Framework']:GetPlayerParkedVehicles(discordID, function(rows) end)
exports['Az-Framework']:GetParkedVehicleByPlate(discordID, plate, function(row) end)
exports['Az-Framework']:IsVehicleParked(discordID, plate, function(isParked) end)
```

### :sparkles: Client Helpers
```lua
exports['Az-Framework']:refreshHUD()
exports['Az-Framework']:updateHUD()
```

### :speech_balloon: Discord Presence (Optional)
```lua
exports['Az-Framework']:RefreshDiscordPresence()
exports['Az-Framework']:SetDiscordPresenceOverride(text)
exports['Az-Framework']:SetDiscordJob(jobLabel)
```

</details>

---

## 🙌 Contributing
- GitHub Org: https://github.com/Azure-Framework  
- Discord: https://discord.com/invite/tBg2U6CTHE  

<sub>Last Updated: Jan 14, 2026</sub>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:FFFFFF,100:007BFF&height=120&section=footer&animation=fadeIn" />
</p>
