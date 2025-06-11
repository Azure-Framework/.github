# Azure Framework

**vMenu-Driven • Lightweight • Modular**

Welcome to **Azure Framework**, a minimalist FiveM server framework built around [vMenu](https://github.com/TomGrobben/vMenu) and Discord integration. Skip the bloat—only include the features you need, instantly.

---

🌟 **Key Highlights**

- **Auto Schema**: Your database tables auto-create on first run—no migrations, no headaches.
- **vMenu Integration**: Seamlessly inject economy, departments, jail, and stats into vMenu’s existing UI.
- **Discord-Powered Permissions**: Sync roles from your Discord guild for in-game permissions and admin access.
- **Modular Architecture**: Enable just the modules you need: Economy, Departments, Jail, Player Stats, and more.
- **High Performance**: Optimized for minimal resource usage.

---

## 🚀 Getting Started

1. **Clone the repo**
   ```bash
   git clone https://github.com/Azure-Framework/Azure-Framework.git
   cd Azure-Framework
   ```
2. **Install dependencies**
   - Ensure you have `mysql-async` or `oxmysql` installed in your FiveM server.
   - Configure `config.lua` with your Discord Bot token, Guild ID, and MySQL details.
3. **Start the resource**
   - Add `ensure mysql-async` (or `ensure oxmysql`) and `ensure Az-Framework` to your `server.cfg`.
   - Launch your server—tables will auto-create on startup!

---

## 📦 Modules

| Module       | Description                                                        |
|--------------|--------------------------------------------------------------------|
| **Economy**  | Cash & bank system, transfers, daily rewards, and Discord logging   |
| **Departments** | Role-based jobs, paychecks, and department management           |
| **Jailer**   | Jail records, permissions, and in-game jailing operations           |
| **Levels**   | Player progression tracking (stamina, strength, driving, RP)        |

To enable or disable modules, simply comment/uncomment in your `server.cfg` and `config.lua`.

---

## 🔧 Configuration

Edit the following in `config.lua`:

```lua
Config = {
  Discord = {
    BotToken = "YOUR_BOT_TOKEN",
    GuildId  = "YOUR_GUILD_ID",
    WebhookURL = "YOUR_LOG_WEBHOOK_URL",
  },
  MySQL = {
    Provider = "mysql-async",     -- or oxmysql
    Host     = "127.0.0.1",
    Database = "fivem_econ",
    Username = "root",
    Password = "password",
  },
  AdminRoleId = "DISCORD_ROLE_ID_FOR_ADMINS",
  Debug      = false,
}
```

---

## 📚 Usage Examples

```lua
-- Add $500 cash to a player
exports['Az-Framework']:addMoney(source, 500)

-- Deposit to bank
exports['Az-Framework']:depositMoney(source, 200)

-- Fetch departments
exports['Az-Framework']:getDepartments(function(rows)
  for _, d in ipairs(rows) do
    print(d.name, d.paycheck)
  end
end)

-- Jail a player for 30 minutes
auth, err = exports['Az-Framework']:requestJail(src, targetId, 30, {'Theft'})
```

---

## 🙌 Contribute

We welcome PRs, issues, and new module ideas! Please follow our [contribution guidelines](https://github.com/Azure-Framework/Azure-Framework/blob/main/CONTRIBUTING.md).

Join the discussion on Discord:

👉 [AzureFramework Community](https://discord.gg/tBg2U6CTHE)

---

<sub>Made with 💙 by the Azure Framework team | v2.4.1 (Last Updated: June 12, 2025)</sub>
