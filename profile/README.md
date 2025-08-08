# Azure Framework – Lightweight Modular System for vMenu Servers

<div align="center">

<img src="https://imgimp.xyz/images/Stoic-2025-06-28_06-06-19-685f865b90047.png" width="200" height="200" />

**vMenu‑Driven • MySQL‑Automatic • Discord‑Powered**

> A fast, modular FiveM framework built around Discord integration and vMenu compatibility.  
> Skip the bloat. Only what your server actually needs.

</div>

---

## 📚 Docs & Resources

- **Homepage** → https://azurewebsites.xyz/framework  
- **Setup Wizard** → https://azurewebsites.xyz/docs/guides/framework/guide.html  
- **Full Documentation** → https://azurewebsites.xyz/docs/economy.html  
- **Community Discord** → https://discord.gg/tBg2U6CTHE

---

## 🔥 Recent Announcements

<details>
<summary>📢 Patch Notes (June 2025)</summary>

- 🔒 **Secure Token Config**  
  All sensitive info like Discord bot tokens and webhooks are now configured in `server.cfg`.

- 💠 **Character Menu (ox_lib)**  
  Now using ox_lib’s sleek menu system to manage character switching.

- 🪙 **MySQL Full Automation**  
  No more import.sql! All framework tables are generated on first run.

- ⚙️ **Upcoming Exports**  
  Two powerful new exports coming soon for even easier script integration.

- 🧼 **Code Refinement & Bug Fixes**  
  Lots of cleanup under the hood—expect smoother performance and fewer warnings.

</details>

---

## 🚀 Quick Start

<details>
<summary>🛠️ How to Install</summary>

1. **Prepare a MySQL database**  
   Note host, port, name, user, and password.

2. **Install Dependencies**  
   - Drop `oxmysql` and `ox_lib` into `resources/`
   - Add `start oxmysql` and `start ox_lib` to your `server.cfg`

3. **Add Azure Framework**  
   - Place `Az-Framework` into `resources/`  
   - Place `Az-Banking`, `Az-Admin`, etc., into `resources/[framework]/`

4. **Update `server.cfg`**

   Add the following in this order:
```
start oxmysql
start ox_lib
start Az-Framework
start [framework]
```

Then, securely set your Discord credentials:

```
set DISCORD_BOT_TOKEN "your_bot_token"
set DISCORD_WEBHOOK_URL "your_webhook_url"
set DISCORD_GUILD_ID "your_guild_id"
```




5. **Launch your server**  
All tables will auto-generate. Your HUD, economy, and admin system should be ready to go.

</details>

---

## 🧩 Core Modules

| Module         | Features                                                                 |
|----------------|--------------------------------------------------------------------------|
| Departments    | Jobs, paychecks, role-based logic, live HUD updates                      |
| Banking        | Cash, bank, transfers, Discord webhook logs                              |
| Admin Tools    | In-game admin menu powered by Discord roles                              |
| Jail System    | Jailing support, timers, reasons, and Discord logging                    |
| Player Stats   | Stamina, strength, driving, RP—persisted between sessions                |
| Characters     | ox_lib character switcher + multi-character support                      |
| Inventory (WIP)| Simple inventory base + ox_inventory support (early development)         |

---

## 🧪 Usage Examples

- Add money: `exports['Az-Framework']:addMoney(source, 500)`
- Transfer to bank: `exports['Az-Framework']:depositMoney(source, 200)`
- Jail a player: `exports['Az-Framework']:requestJail(src, targetId, 30, {'Theft'})`
- Get departments: `exports['Az-Framework']:getDepartments(function(rows) ... end)`

---

## 🧰 Configuration

All sensitive data is handled securely via `server.cfg`.

You should:
- Add `DISCORD_BOT_TOKEN`, `DISCORD_WEBHOOK_URL`, and `DISCORD_GUILD_ID` into `server.cfg`
- Never hardcode Discord tokens or webhooks into your Lua files

Other configuration (like module toggles or default values) is done within each module’s `config.lua` where applicable.

---

## 🧠 Philosophy

Azure Framework was built for simplicity and transparency:

- ✅ No bloat: you choose which modules to use
- 🔐 Discord handles all permissions
- 🛠️ Designed to work seamlessly with vMenu, ox_lib, and community scripts
- 💾 MySQL auto-setup—no manual imports

---

## 📎 Screenshots

<details>
<summary>📸 Preview Gallery</summary>

![Dashboard Preview](upload://jGWM0S2UuMMTpRoLHxDwegzliCg.png)  
![In‑Game HUD](upload://1rOzX7uVhRubXuHdyKpTYGopBv0.png)  
![Departments List](upload://7P3qNuMSPJy6Gn4u9Q5k6VrXC7j.jpeg)  
![Admin Panel](upload://dJz2W9OngIxImSL5bh91ZcVnOa2.jpeg)  
![HUD Example](upload://yANYSsBWlTkIx4wVZKluxpgLtfBZ.jpeg)

</details>

---

## 🙌 Contributing

We welcome PRs and feedback! Submit improvements, report bugs, or suggest new modules.

- GitHub: https://github.com/Azure-Framework  
- Community: https://discord.gg/tBg2U6CTHE

---

<sub>Made with 💙 by Azure Framework | v2.4.2 – Last Updated: June 28, 2025</sub>
