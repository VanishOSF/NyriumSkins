# NyriumSkins

### Your server. Your style.

CS2 cosmetic plugin maintained by **pad7rar**, with in-game skin selection and MySQL-backed player preferences.

**Version:** 0.1.0

[Website](https://nyrium.global) | [Discord](https://discord.gg/FmGBPWTkDP) | [GitHub](https://github.com/VanishOSF)

## Features

- Weapon skins, knives and gloves.
- Agents, music kits, pins and StatTrak controls.
- Sticker and charm data support for compatible external integrations.
- In-game selection menus and cosmetic refresh.
- Player selections stored in MySQL.
- Compatible database structure for WeaponPaints-style websites and custom panels.

Website software and custom panels are not included.

## Commands

| Command | Action |
| --- | --- |
| `!ws` / `!skins` | Open the skin selection menu |
| `!wp` | Reload saved selections and refresh cosmetics |
| `!knife` | Open the knife menu |
| `!gloves` | Open the glove menu |
| `!agents` | Open the agent menu |
| `!music` | Open the music kit menu |
| `!pins` | Open the pin menu |
| `!stattrak` / `!st` | Toggle StatTrak for the active weapon |

Commands are enabled in the included example configuration. Another plugin can still intercept or block them.

## Requirements

- Counter-Strike 2 dedicated server with Metamod:Source.
- CounterStrikeSharp API v375 / .NET 10 runtime.
- Compatible MenuManager, PlayerSettings and their required dependencies.
- A configured MySQL database.

These server frameworks are not bundled. Test compatibility before updating an existing production server.

## Installation

1. Stop the server and back up your existing configuration and database.
2. Upload the contents of `server/` into the server's `game/csgo/` directory.
3. Fill in your MySQL settings in `addons/counterstrikesharp/configs/plugins/NyriumSkins/NyriumSkins.json`.
4. Confirm that `addons/counterstrikesharp/gamedata/nyriumskins.json` is present.
5. Start the server and check `css_plugins list`, then test `!ws` and `!wp` in game.

When migrating, do not run the old WeaponPaints plugin alongside NyriumSkins. Preserve your database and transfer your existing settings instead of overwriting them with empty example values. Keep credentials out of Git.

No Workshop upload is required for this plugin package.

## Integration

Compatible websites and custom panels can save selections to the same `wp_player_*` MySQL tables. The server-console command `wp_refresh <SteamID64> [weaponDefindex]` requests a refresh; the optional weapon definition selects the modified weapon when it is owned by the player.

The `Website` setting is a displayed link, not an automatic website connection.

## Support

For setup questions and bug reports, join [Nyrium Discord](https://discord.gg/FmGBPWTkDP). Include the plugin version, CounterStrikeSharp version, relevant console errors and steps to reproduce. Never post database passwords or tokens.

## License

NyriumSkins is based on [cs2-WeaponPaints](https://github.com/Nereziel/cs2-WeaponPaints) by Nereziel and daffyy, with modifications maintained by pad7rar.

This distribution is licensed under GNU GPLv3. See [LICENSE](LICENSE) and [NOTICE](NOTICE). This repository contains runtime files, not source files; that does not remove the GPL obligations to provide Corresponding Source to recipients. A separate source-delivery mechanism has not yet been established for this distribution.
