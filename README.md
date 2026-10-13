# NyriumSkins 0.2.0 BETA

[Discord / Tickets](https://discord.gg/FmGBPWTkDP) | [Website](https://nyrium.global)

## RO
Distributie binara 0.2.0 BETA. Nu contine surse C#, scripturi de build sau surse Panorama editabile.
`server/` contine pluginul, dependintele si exemplul de configurare; `workshop/game/` contine numai resurse compilate.

### Noutati
- Panel !nyrium cu preview, teme, cautare si filtre T/CT/BOTH.
- Salvare DB pentru skinuri, cutite, wear, seed, StatTrak, stickere, charm-uri si pin-uri.
- Optiunea JSON NyriumPanelEnabled pentru activarea/dezactivarea panelului.
- Refresh cu inlocuire verificata, curatarea originalului si protectie temporara la pickup.
- Testele de gameplay si salvare/reconectare DB au fost confirmate de autor. Versiunea ramane BETA.
- Adaugata si remediata alegerea agentilor si manusilor din !nyrium, cu salvare MySQL si aplicare in joc, confirmate prin testare de autor. Agentii respecta echipa selectata.
- Muzica ramane preview-only in noul APPLY; meniurile clasice sunt separate.
- Pentru acest update inlocuiti doar NyriumSkins.dll cu serverul oprit. Nu este necesar Workshop Re-Upload.

### Instalare
1. Opriti serverul si faceti backup configuratiei si DB. Nu rulati WeaponPaints simultan.
2. Instalati Metamod, CounterStrikeSharp compatibil cu API 375 / .NET 10, MenuManager, PlayerSettings si dependintele lor. Configurati MySQL.
3. Urcati gamedata din server/addons/counterstrikesharp/gamedata/ in game/csgo/addons/counterstrikesharp/gamedata/.
4. Urcati plugins/NyriumSkins/ din distributie in game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/.
5. La prima instalare folositi exemplul JSON din configs/plugins/NyriumSkins/. La update pastrati credentialele si setarile existente.
6. Adaugati la radacina configuratiei `"NyriumPanelEnabled": true`. Cu false meniul se dezactiveaza, nu si cosmeticele salvate.
7. Functiile cosmetice necesita FollowCS2ServerGuidelines=false in configuratia CSS. Verificati regulile Valve aplicabile.
8. Configurati Workshop, porniti serverul, verificati css_plugins list si testati !nyrium.
UPDATE PREVIEW nu salveaza. APPLY IN GAME salveaza in DB; pentru refresh imediat tineti arma potrivita in mana.
Nu se acorda iteme in inventarul Steam.

### Workshop propriu
1. Creati/deschideti propriul addon in CS2 Workshop Tools.
2. Copiati continutul workshop/game/ in game/csgo_addons/NUME_ADDON/ din instalarea CS2, pastrand caile panorama/.
3. Includeti resursele compilate in pachetul addonului si publicati/Re-Upload pe propriul Workshop. Nu incarcati DLL-uri sau configuratii.
4. Instalati [MultiAddonManager](https://github.com/Source2ZE/MultiAddonManager) pe server.
5. Adaugati propriul ID in mm_extra_addons din game/csgo/cfg/multiaddonmanager/multiaddonmanager.cfg, pastrand ID-urile existente.
6. Confirmati descarcarea/montarea, schimbati harta si reconectati clientii. Verificati de pe un client fara fisiere loose.
Fiecare client publica pe propriul Workshop; nu exista ID comun. Resursele schimbate necesita Re-Upload; modificarile exclusiv DLL nu.

Raportati bug-uri printr-un **ticket pe Discord** cu versiunea, pasii, logurile si capturile. Nu trimiteti parole/tokenuri.

## EN
Binary distribution 0.2.0 BETA. No C# source, build scripts or editable Panorama source is included.
`server/` contains runtime files and example configuration; `workshop/game/` contains compiled resources only.

### Changes
- !nyrium panel with preview, themes, search and T/CT/BOTH filters.
- DB persistence for skins, knives, wear, seed, StatTrak, stickers, charms and pins.
- NyriumPanelEnabled JSON toggle.
- Checked replacement, original cleanup and temporary pickup protection during refresh.
- Gameplay and DB save/reconnect tests confirmed by the author. This remains a BETA.
- Added and fixed agent and glove selection through !nyrium, with MySQL persistence and in-game application confirmed by the author's tests. Agents respect the selected team.
- Music remains preview-only in the new APPLY flow; classic menus are separate.
- For this update, replace only NyriumSkins.dll while the server is stopped. No Workshop re-upload is required.

### Installation
1. Stop the server and back up configuration/DB. Do not run WeaponPaints alongside this plugin.
2. Install Metamod, CounterStrikeSharp compatible with API 375 / .NET 10, MenuManager, PlayerSettings and their dependencies. Configure MySQL.
3. Upload gamedata to game/csgo/addons/counterstrikesharp/gamedata/.
4. Upload the distributed plugins/NyriumSkins/ folder to game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/.
5. Use the example config only for first installation. Preserve existing credentials/settings when upgrading.
6. Add root-level `"NyriumPanelEnabled": true`. False disables the panel, not saved cosmetics.
7. Cosmetic changes require FollowCS2ServerGuidelines=false in CSS configuration. Review applicable Valve rules.
8. Configure Workshop, start the server, check css_plugins list and test !nyrium.
UPDATE PREVIEW does not save. APPLY IN GAME saves to DB; hold the matching weapon for immediate refresh.
This does not grant Steam inventory items.

### Your own Workshop
1. Create/open your own addon in CS2 Workshop Tools.
2. Copy the contents of workshop/game/ into game/csgo_addons/ADDON_NAME/ in your CS2 installation, preserving panorama/ paths.
3. Include compiled resources in the addon package and publish/Re-Upload to your own Workshop. Do not upload DLLs or configurations.
4. Install [MultiAddonManager](https://github.com/Source2ZE/MultiAddonManager) on the server.
5. Add your actual ID to mm_extra_addons in game/csgo/cfg/multiaddonmanager/multiaddonmanager.cfg, retaining existing IDs.
6. Verify downloads/mounting, reload the map and reconnect clients. Test without loose client overrides.
Each operator publishes their own addon; no shared ID is required. Resource changes require Re-Upload; DLL-only changes do not.

Report bugs by opening a **Discord ticket** with version, steps, logs and screenshots. Never share passwords/tokens.

## License / Licenta
Based on cs2-WeaponPaints by Nereziel and daffyy. GPL-3.0; see LICENSE and NOTICE.
Removing source from this repository does not remove the applicable source-distribution obligations.
Eliminarea sursei din repository nu elimina obligatiile de distribuire a sursei prevazute de licenta.
