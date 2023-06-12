## PvP

PvP is a work in progress. It lets you use duel rooms under a low latency environment (LAN). The friends list works. There is a custom trading implementation which you can access by going to a players profile.

## Setting it up on a single PC

- Open `Data/Setting.json` and set `MultiplayerEnabled` to `true`
- Open `Data/ClientData/ClientSettings.json` and set `MultiplayerToken` to some random text value
- Copy / paste the entire `YgoMaster` folder so that it creates `YgoMaster - Copy`
- Inside that `YgoMaster - Copy` folder edit `Data/ClientData/ClientSettings.json` and set `MultiplayerToken` to a different random text value to the previous folder
- Run `YgoMaster.exe` in the `YgoMaster` folder
- Run `YgoMasterClient.exe` in both folders

## Setting it up on LAN

- Open `Data/Setting.json` and set `MultiplayerEnabled` to `true`
- Open `Data/ClientData/ClientSettings.json` and set `MultiplayerToken` to some random text value
- Modify `BaseIP` in both `Data/Setting.json` and `Data/ClientData/ClientSettings.json` to point to the IP of the machine which runs `YgoMaster.exe`

## Setting it up on WAN

- Open `Data/Setting.json` and set `MultiplayerEnabled` to `true`
- Open `Data/ClientData/ClientSettings.json` and set `MultiplayerToken` to some random text value
- In `Settings.json` set `BaseIP` to `*` and `SessionServerIP` to `0.0.0.0`
- In `ClientSettings.json` set `BaseIP` to the WAN IP
- Play around with `MultiplayerNoDelay` (`Setting.json` / `ClientSettings.json`) to see which works best for you (it disables nagle's algorithm)

## Starting duels

- Click `DUEL` in the home menu
- Click `Duel Room (PvP)` and create a duel room as you would in the normal game

## Notes

- Every PC (and every seperate YgoMaster folder) must have a different `MultiplayerToken` as otherwise they will share the same session which will break things
- Due to requiring very low latency PvP is unlikely to perform well over WAN / Hamachi / ZeroTier / Tailscale / etc
- Do not modify `YgoMaster/Data/Players/` or any sub folders while `YgoMaster.exe` is running

## Trading

You can trade cards with other players by going to their profile and clicking "Trade"

- Both players need to click "Trade" to enter the trade
- Your cards go to the "main deck" and their cards go to the "extra deck"
- Use the button on the top right where "SAVE" normally is to complete your trade. There's a cooldown of a few seconds on the button when moving cards to avoid accidental trading. You will need to press the trade button again if either player modifies the cards. If the button says "Trade!!!" it means the other player has pressed the trade button
- Use the sub menu of the trade menu to view their cards
- You can add their cards / remove their cards from the trade
- You cannot craft / dismantle while trading