# NyriumSkins 0.2.0 BETA

## Update 2026-10-16 / RO
- Scroll in listele de filtre Model, Rarity si Sort, fara Next/Previous. Catalogul principal ramane paginat.
- Optiune JSON `RequireMatchingWeaponForApply`: implicit `true`; setati `false` pentru salvare fara arma potrivita in mana si refresh automat al armei/cutitului deja detinut.
- Arma selectata este echipata scurt pentru refresh; alte tipuri de arme nu sunt oferite. Daca arma lipseste, selectia se aplica la cumparare/pickup. Manusile pastreaza aplicarea automata.
- Mesajele tehnice de refresh nu mai apar in chat. Testele de gameplay au fost confirmate de autor; versiunea ramane BETA, fara garantie pentru toate mediile.

### Instalare update / RO
1. Opriti serverul si pastrati un backup al DLL-ului, configuratiei si resurselor Workshop.
2. Copiati fisierele din `workshop/game/panorama/` in `game/csgo_addons/ADDON_NAME/panorama/` din instalarea proprie CS2. Faceti Workshop Re-Upload pe addonul propriu, pastrand ID-ul existent.
3. Inlocuiti `game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/NyriumSkins.dll` cu DLL-ul actualizat.
4. In configuratia existenta `game/csgo/addons/counterstrikesharp/configs/plugins/NyriumSkins/NyriumSkins.json`, adaugati `"RequireMatchingWeaponForApply": false` daca doriti comportamentul nou. Nu suprascrieti credentialele DB cu exemplul din Git.
5. Porniti serverul, verificati descarcarea noii versiuni Workshop si testati filtrele si aplicarea. DLL-ul si resursele trebuie actualizate impreuna. Nu este necesara migrare DB sau schimbarea dependentelor.

## Update 2026-10-16 / EN
- Scrollable Model, Rarity and Sort filter lists without Next/Previous. The main catalog remains paginated.
- New JSON option `RequireMatchingWeaponForApply`: defaults to `true`; set to `false` to save without holding the matching weapon and automatically refresh an already-owned weapon/knife.
- The selected weapon is briefly equipped for refresh. No different weapon is granted; missing weapons receive the saved selection on purchase/pickup. Gloves retain automatic application.
- Removed technical refresh messages from player chat. Gameplay tests were confirmed by the author; this remains BETA, not a guarantee for every environment.

### Update installation / EN
1. Stop the server and back up the current DLL, configuration and Workshop resources.
2. Copy `workshop/game/panorama/` into your own CS2 `game/csgo_addons/ADDON_NAME/panorama/`. Re-upload your own Workshop addon, keeping its existing ID.
3. Replace `game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/NyriumSkins.dll` with the updated DLL.
4. Add `"RequireMatchingWeaponForApply": false` to your existing `game/csgo/addons/counterstrikesharp/configs/plugins/NyriumSkins/NyriumSkins.json` to enable the new behavior. Do not overwrite database credentials with the Git example.
5. Start the server, verify the updated Workshop download and test filters and application. Update DLL and resources together. No database migration or dependency changes required.

RO: Raportati bug-uri prin ticket pe https://discord.gg/FmGBPWTkDP.
EN: Report bugs through a ticket at https://discord.gg/FmGBPWTkDP.

---


Tag: v0.2.0. GitHub release type: Pre-release.

## RO
Versiune BETA pentru testare, nu o garantie de stabilitate.
- Panelul !nyrium: preview, teme, categorii, cautare, filtre T/CT/BOTH.
- Salvare MySQL pentru arme/cutite, wear/seed, StatTrak, stickere, charm-uri si pin-uri.
- NyriumPanelEnabled in JSON pentru activarea/dezactivarea panelului.
- Refresh cu inlocuire verificata, curatarea originalului si protectie temporara la pickup.
- Fisierele binare si instructiunile de instalare/Workshop sunt incluse in repository. Sursele nu sunt incluse.

Cititi README inainte de instalare. Pastrati configuratia si faceti backup DB.
Adaugata si remediata alegerea agentilor si manusilor din !nyrium, cu salvare MySQL si aplicare in joc, confirmate prin testare de autor. Agentii respecta echipa selectata. Muzica ramane preview-only in noul APPLY.
Pentru acest update opriti serverul, inlocuiti doar addons/counterstrikesharp/plugins/NyriumSkins/NyriumSkins.dll si reporniti serverul. Pastrati configuratia si dependentele. Nu este necesar Workshop Re-Upload.
Salvarea si reincarcarea DB dupa reconectare au fost confirmate de autor pe serverul de teste. Fisierele Workshop sunt incluse; fiecare administrator le publica pe propriul Workshop si configureaza propriul ID.
Raportati bug-uri printr-un ticket pe https://discord.gg/FmGBPWTkDP, cu versiunea, pasii, loguri si capturi. Fara parole/tokenuri.

## EN
BETA for testing, not a stability guarantee.
- !nyrium panel: preview, themes, categories, search, T/CT/BOTH filters.
- MySQL persistence for weapons/knives, wear/seed, StatTrak, stickers, charms and pins.
- NyriumPanelEnabled JSON toggle for the panel.
- Validated replacement flow, original cleanup and temporary pickup protection.
- Runtime files and installation/Workshop instructions included in the repository. Source is not included.

Read README before installing. Preserve configuration and back up the database.
Added and fixed agent and glove selection through !nyrium, with MySQL persistence and in-game application confirmed by the author's tests. Agents respect the selected team. Music remains preview-only in the new APPLY flow.
For this update, stop the server, replace only addons/counterstrikesharp/plugins/NyriumSkins/NyriumSkins.dll and restart the server. Preserve configuration and dependencies. No Workshop re-upload is required.
The author confirmed database saving and reloading after reconnecting on the test server. Workshop files are included; each operator publishes them to their own Workshop and configures their own ID.
Report bugs by opening a ticket at https://discord.gg/FmGBPWTkDP with version, steps, logs and screenshots. No passwords/tokens.
