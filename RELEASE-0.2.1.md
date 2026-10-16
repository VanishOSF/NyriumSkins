# NyriumSkins 0.2.1 BETA

## Update 2026-10-16 / RO
- Scroll in filtrele Model, Rarity si Sort, fara Next/Previous. Catalogul principal ramane paginat.
- Refresh automat dupa APPLY IN GAME pentru arma/cutitul deja detinut, fara comanda manuala !wp, cand `RequireMatchingWeaponForApply=false`. Arma este echipata scurt; nu se ofera alte arme. Daca lipseste, selectia ramane salvata pentru cumparare/pickup. Manusile pastreaza aplicarea automata.
- Overview retine ultima selectie salvata pentru fiecare echipa/categorie, inclusiv dupa reconectare. Alegerile vechi necesita o noua salvare pentru stabilirea preferintei.
- Comenzile meniurilor clasice (!ws, !skins, !knife, !gloves, !agents, !music, !pin si aliasurile lor) deschid implicit !nyrium. Aceasta evita calea meniurilor raportata ca instabila, nu confirma remedierea cauzei crash-ului. Comenzile administrative si !wp raman separate.
- Eliminate mesajele tehnice de refresh din chat. !nyriumstatus afiseaza overview-r2 si optiunea efectiva pentru arma tinuta.
- Exemplul JSON include optiunile corecte. Daca `RequireMatchingWeaponForApply` lipseste din configuratia existenta, fallback-ul DLL ramane true pentru compatibilitate. Simpla inlocuire a DLL-ului nu modifica configuratia.
- Versiune BETA. Testele raportate de autor/client au trecut; nu este o garantie pentru orice server sau combinatie de pluginuri.

### Instalare update / RO
1. Opriti serverul si pastrati backup pentru DLL, configuratie, DB si resurse Workshop.
2. Copiati `workshop/game/panorama/` din branch-ul main in `game/csgo_addons/ADDON_NAME/panorama/`. Faceti Workshop Re-Upload pe addonul propriu, pastrand ID-ul. Nu mai este necesar daca versiunea de scroll este deja publicata si descarcata.
3. Inlocuiti `NyriumSkins.dll` si `NyriumSkins.deps.json` din `game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/` cu fisierele 0.2.1 din release sau main. Nu inlocuiti DLL-urile dependente ori gamedata pentru acest update.
4. Editati configuratia existenta `game/csgo/addons/counterstrikesharp/configs/plugins/NyriumSkins/NyriumSkins.json`. Adaugati optiunile de mai jos o singura data, in interiorul obiectului principal, nu in Additional. Nu copiati exemplul peste credentialele DB.
5. Porniti serverul. Pluginul creeaza automat tabelul aditiv `wp_nyrium_overview`; utilizatorul DB necesita drepturi CREATE, SELECT, INSERT si UPDATE. Nu se sterg skin-uri existente.
6. Verificati !nyriumstatus: `RequireMatchingWeaponForApply=False`. Verificati descarcarea addonului Workshop, apoi testati APPLY cu alta arma in mana si Overview dupa reconectare.

```json
{
  "NyriumPanelEnabled": true,
  "RequireMatchingWeaponForApply": false,
  "RedirectLegacyMenusToPanel": true
}
```
Fragmentul de mai sus arata doar optiunile, nu o configuratie completa. Cu `RedirectLegacyMenusToPanel=false` revin meniurile clasice, dar stabilitatea lor trebuie validata separat. Nu activati aceasta valoare doar pentru a ocoli un crash.

## Update 2026-10-16 / EN
- Scrollable Model, Rarity and Sort filters without Next/Previous. The main catalog remains paginated.
- Automatic refresh after APPLY IN GAME for an already-owned weapon/knife, without manually typing !wp, when `RequireMatchingWeaponForApply=false`. The weapon is briefly equipped; no other weapons are granted. If absent, the selection is saved for purchase/pickup. Gloves retain automatic application.
- Overview remembers the last saved selection per team/category across reconnects. Older selections require a new save to establish the preference.
- Classic menu commands (!ws, !skins, !knife, !gloves, !agents, !music, !pin and their aliases) redirect to !nyrium by default. This avoids the reported unstable menu path; it does not establish that the underlying crash is fixed. Admin commands and !wp remain separate.
- Removed technical refresh chat messages. !nyriumstatus shows overview-r2 and the effective held-weapon setting.
- Correct options are included in the example JSON. If `RequireMatchingWeaponForApply` is absent from an existing config, the DLL fallback remains true for compatibility. Replacing the DLL alone does not change configuration.
- BETA. Author/client-reported tests passed; this is not a guarantee for every server or plugin combination.

### Update installation / EN
1. Stop the server and back up the DLL, config, database and Workshop resources.
2. Copy `workshop/game/panorama/` from main into your own `game/csgo_addons/ADDON_NAME/panorama/`. Re-upload your Workshop addon, keeping its ID. Skip this if the scroll resources are already published and downloaded.
3. Replace `NyriumSkins.dll` and `NyriumSkins.deps.json` in `game/csgo/addons/counterstrikesharp/plugins/NyriumSkins/` with the 0.2.1 files from the release or main. No dependency DLL or gamedata replacement is required for this update.
4. Edit your existing `game/csgo/addons/counterstrikesharp/configs/plugins/NyriumSkins/NyriumSkins.json`. Add the options shown above once, inside the root object, not Additional. Preserve database credentials and all unrelated settings.
5. Start the server. The plugin automatically creates the additive `wp_nyrium_overview` table; the database account needs CREATE, SELECT, INSERT and UPDATE permissions. Existing skins are not deleted.
6. Check !nyriumstatus for `RequireMatchingWeaponForApply=False`. Verify Workshop download, then test APPLY while holding another weapon and Overview after reconnecting.

The JSON fragment above contains options only, not a full configuration. `RedirectLegacyMenusToPanel=false` restores classic menus, whose stability still requires separate validation.

RO: Raportati bug-uri prin ticket pe https://discord.gg/FmGBPWTkDP, fara parole sau tokenuri.
EN: Report bugs through a ticket at https://discord.gg/FmGBPWTkDP. Never share credentials.

---


Tag: v0.2.1. GitHub release type: Pre-release.

## RO
Versiune BETA pentru testare, nu o garantie de stabilitate.
- Panelul !nyrium: preview, teme, categorii, cautare, filtre T/CT/BOTH.
- Salvare MySQL pentru arme/cutite, wear/seed, StatTrak, stickere, charm-uri si pin-uri.
- NyriumPanelEnabled in JSON pentru activarea/dezactivarea panelului.
- Refresh cu inlocuire verificata, curatarea originalului si protectie temporara la pickup.
- Fisierele binare si instructiunile de instalare/Workshop sunt incluse in repository. Sursele nu sunt incluse.

Cititi README inainte de instalare. Pastrati configuratia si faceti backup DB.
Adaugata si remediata alegerea agentilor si manusilor din !nyrium, cu salvare MySQL si aplicare in joc, confirmate prin testare de autor. Agentii respecta echipa selectata. Muzica ramane preview-only in noul APPLY.
Pentru instalarea update-ului curent urmati pasii RO/EN de mai sus.
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
Follow the RO/EN instructions above to install the current update.
The author confirmed database saving and reloading after reconnecting on the test server. Workshop files are included; each operator publishes them to their own Workshop and configures their own ID.
Report bugs by opening a ticket at https://discord.gg/FmGBPWTkDP with version, steps, logs and screenshots. No passwords/tokens.
