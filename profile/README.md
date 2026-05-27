<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0A84FF,100:EAF4FF&height=190&section=header&text=AZURE%20FRAMEWORK&fontSize=62&fontColor=FFFFFF&fontAlignY=35&animation=fadeIn&desc=AZ-FRAMEWORK%202.0%20FOR%20FIVEM&descAlignY=60&descSize=18&descColor=EAF3FF" alt="Azure Framework" />
</p>

<h1 align="center">Az-Framework</h1>

<p align="center">
  <b>Modular FiveM framework, compatibility bridges, resource packs, and txAdmin deployment for production roleplay servers.</b>
</p>

<p align="center">
  <a href="https://madebyazure.com/framework/"><img alt="Docs" src="https://img.shields.io/badge/Docs-madebyazure.com-0A84FF?style=for-the-badge" /></a>
  <a href="https://github.com/Azure-Framework/txRecipe"><img alt="txAdmin" src="https://img.shields.io/badge/txAdmin-Recipe-111827?style=for-the-badge" /></a>
  <a href="https://discord.gg/tBg2U6CTHE"><img alt="Discord" src="https://img.shields.io/badge/Discord-Support-5865F2?style=for-the-badge" /></a>
  <a href="https://github.com/Azure-Framework/Az-Framework"><img alt="Framework" src="https://img.shields.io/badge/Az--Framework-2.0-0A84FF?style=for-the-badge" /></a>
</p>

---

## What Is Az-Framework?

Az-Framework is a FiveM framework ecosystem built around a central `Az-Framework` core, modular gameplay resources, compatibility bridges, and a public txAdmin recipe.

It is designed for servers that want Az-native systems without throwing away every resource written for QBCore, qb-inventory, qb-target, ESX, ND_Core, ox, or vMenu-style stacks.

## Why Use It?

- Central player, character, money, job, metadata, department, admin, HUD, and bridge export layer.
- Modular resources that can be installed as a full stack or added one at a time.
- Bridge repos for legacy resource compatibility.
- Summer 2.0 resource pack with legal and illegal seasonal activities.
- txAdmin recipe for faster clean installs.
- Public docs and Discord support.

---

<details open>
<summary><b>Quick Install</b></summary>

Use the txAdmin recipe when starting fresh:

```text
https://github.com/Azure-Framework/txRecipe
```

Core start order:

```cfg
ensure oxmysql
ensure ox_lib
ensure ox_target
ensure Az-Framework
```

Start inventory, target, bridge, MDT, job, and gameplay resources after `Az-Framework`.

</details>

<details>
<summary><b>Important Bridge Rename Instructions</b></summary>

The bridge repositories are published with Az-branded repo names, but the runtime folders must be renamed to the framework names that legacy resources expect.

If you download or clone a bridge manually, rename the folder before starting it:

| GitHub repository | Required runtime folder name | Use when a resource expects |
| --- | --- | --- |
| `Az-QBCore-Bridge` | `qb-core` | `exports['qb-core']:GetCoreObject()` |
| `Az-QBInventory-Bridge` | `qb-inventory` | qb-inventory events/exports |
| `Az-QBTarget-Bridge` | `qb-target` | qb-target exports |
| `Az-ESX-Bridge` | `es_extended` | ESX Legacy APIs |
| `Az-NDCore-Bridge` | `ND_Core` | ND_Core APIs |

Correct start order:

```cfg
ensure Az-Framework
ensure qb-core
ensure qb-inventory
ensure qb-target
ensure es_extended
ensure ND_Core
```

Do not start the folders as `Az-QBCore-Bridge`, `Az-QBInventory-Bridge`, `Az-QBTarget-Bridge`, `Az-ESX-Bridge`, or `Az-NDCore-Bridge`; most compatibility resources check the original framework resource name.

</details>

<details>
<summary><b>2.0 Resource Groups</b></summary>

Core framework:

- `Az-Framework`
- `txRecipe`

Compatibility bridges:

- `Az-QBCore-Bridge`
- `Az-QBInventory-Bridge`
- `Az-QBTarget-Bridge`
- `Az-ESX-Bridge`
- `Az-NDCore-Bridge`

Summer 2.0 pack:

- `Az-Summer2Core`
- `Az-Lifeguard`
- `Az-Marina`
- `Az-IceCream`
- `Az-Camping`
- `Az-ParkEvents`
- `Az-ResortStaff`
- `Az-FoodFestival`
- `Az-Fishing2`
- `Az-SmugglingRun`
- `Az-Boosting2`
- `Az-Burglary2`
- `Az-DrugLabs2`
- `Az-IllegalFishing`
- `Az-Poaching`
- `Az-ScrapTheft`
- `Az-FraudOps`
- `Az-StreetRacing2`
- `Az-BlackMarketBeach`

Public safety and server systems:

- `Az-MDT`
- `Az-5PD`
- `Az-Jailing`
- `Az-Ambulance`
- `Az-Fire`
- `Az-ParkRangers`
- `Az-Admin`
- `Az-ConfigManager`
- `Az-Loading`
- `Az-WeatherSystem`

Jobs, economy, and gameplay:

- `Az-Jobs`
- `Az-JobCenter`
- `Az-JobGarages`
- `Az-Marketplace`
- `Az-Hunting`
- `Az-Fishing`
- `Az-FishFinder`
- `Az-Inventory`
- `Az-Levels`
- `Az-Dealerships`
- `Az-VehicleSystems`

</details>

<details>
<summary><b>Framework Exports</b></summary>

Use Az exports when building or converting resources:

```lua
local Az = exports['Az-Framework']:GetObject()
local player = exports['Az-Framework']:GetPlayer(source)
local snapshot = exports['Az-Framework']:GetBridgePlayerSnapshot(source)
```

Common server exports include:

```lua
exports['Az-Framework']:GetPlayer(source)
exports['Az-Framework']:GetPlayers()
exports['Az-Framework']:GetPlayerCharacter(source)
exports['Az-Framework']:GetActiveCharacter(source)
exports['Az-Framework']:GetBridgePlayerSnapshot(source)
exports['Az-Framework']:GetBridgePlayers()
exports['Az-Framework']:AddBridgeMoney(source, account, amount, reason)
exports['Az-Framework']:RemoveBridgeMoney(source, account, amount, reason)
exports['Az-Framework']:AddBridgeItem(source, item, count, metadata)
exports['Az-Framework']:RemoveBridgeItem(source, item, count, metadata)
exports['Az-Framework']:BridgeNotify(source, message, type, duration)
```

</details>

---

## Links

- Docs: https://madebyazure.com/framework/
- Discord: https://discord.gg/tBg2U6CTHE
- Core repo: https://github.com/Azure-Framework/Az-Framework
- txAdmin recipe: https://github.com/Azure-Framework/txRecipe

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:EAF4FF,100:0A84FF&height=120&section=footer&animation=fadeIn" alt="" />
</p>
