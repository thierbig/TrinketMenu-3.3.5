# TrinketMenu (Wrath 3.3.5a)

Lightweight trinket management addon by Gello, updated for Wrath of the Lich King 3.3.5a (Interface 30300). This fork adds a few quality-of-life safeguards while keeping original behavior and layout.

## Features
- **Equipped trinkets bar**: Shows both trinket slots; left-click to use.
- **Expandable trinkets menu**: Docked grid of bagged trinkets with cooldown sweep.
- **Auto Queue (optional)**: Prioritize and cycle trinkets (see `TrinketMenuQueue.*`).
- **Cooldown numbers (optional)**: Toggle large/small numeric timers on icons.
- **Minimap button**: Moveable around round or square minimap.
- **Tooltips**: Full or compact tooltips; follow cursor option.
- **Frame docking & orientation**: Horizontal/vertical, menu docking anchors.
- **Keybindings**: Bind use for Top/Bottom trinket and toggle.
- **WotLK self-heal (new)**: Optional protection if another addon hides the frame.

## Game version
- Tested on **3.3.5a (build 12340)**.
- `TrinketMenu.toc` has `## Interface: 30300`, so "Load out of date AddOns" is not required.

## Installation
1. Download/clone this repo.
2. Place the folder as `Interface/AddOns/TrinketMenu/` so that the `.toc` and Lua/XML files are directly inside that folder.
3. Launch the game and enable the addon on the character selection screen.
4. Type `/reload` in-game if you updated in place.

## Usage
- Open/close the main frame: `/trinket` or `/trinketmenu`
- Right-click behavior and other options are configured in the Options window.
- Drag the window(s) to reposition. Use the lower-right corner to scale.

### Slash commands
- **/trinket, /trinketmenu** — Toggle the main TrinketMenu window.
- **/trinket opt** or **/trinket config** — Open options.
- **/trinket lock | unlock** — Toggle moving/scaling.
- **/trinket alpha <0.1–1.0>** — Set global alpha for frames.
- **/trinket scale main <num>** — Set exact scale for main frame.
- **/trinket scale menu <num>** — Set exact scale for menu frame.
- **/trinket load top|bottom <ProfileName>** — Load an Auto Queue profile.
- (New) **/trinket show | hide** — Explicitly show or hide the main frame.
- (New) **/trinket fix** — Repair visibility/alpha/scale/strata/position and show.
- (New) **/trinket alwayson on|off** — Keep the main frame visible even if another addon tries to hide it.

### Keybindings
- **Use Top Trinket** — `CLICK TrinketMenu_Trinket0:LeftButton`
- **Use Bottom Trinket** — `CLICK TrinketMenu_Trinket1:LeftButton`
- **Toggle TrinketMenu** — Toggles Main or Options depending on settings

You can bind these in the in-game Key Bindings interface (`Esc` → `Key Bindings`).

## Configuration highlights
- **Cooldown numbers**: Options → Cooldown Numbers (and Large Numbers).
- **Menu behavior**: Keep Menu Open, Keep Menu Docked, Wrap columns.
- **Tooltips**: Show Tooltips, At Mouse, Tiny Tooltips.
- **Menu on Right-Click**: Prevents menu from opening on hover until explicitly right-clicked.

## Compatibility
- Built and tested for **WotLK 3.3.5a**.
- Includes a safeguard to re-show the frame if another addon hides it (`ForceShow`, default ON). Toggle with `/trinket alwayson off` if you prefer complete manual control.

## Files
- `TrinketMenu.toc` — AddOn manifest (30300).
- `TrinketMenu.lua` — Core logic and frame scripts.
- `TrinketMenu.xml` — Main/menu frames and templates.
- `TrinketMenuOpt.lua` + `TrinketMenuOpt.xml` — Options UI and minimap button.
- `TrinketMenuQueue.lua` + `TrinketMenuQueue.xml` — Auto Queue features (optional, included).
- `Bindings.xml` — Keybinding definitions.

## SavedVariables
- Global: `TrinketMenuOptions`
- Per-character: `TrinketMenuPerOptions`, `TrinketMenuQueue`

## Credits
- Original AddOn by **Gello**.
- This fork: minor maintenance for 3.3.5a compatibility and stability improvements (anti-hide, extra slash commands).

## License
- This repository preserves original authorship and intent. If you are a rights holder for TrinketMenu and would like this fork changed or taken down, please open an issue.

## Changelog (fork)
- 3.81-wotlk-3.3.5
  - Bumped `## Interface: 30300`.
  - Added optional self-heal to keep frame visible when hidden by other addons.
  - Added `/trinket show`, `/trinket hide`, `/trinket fix`, `/trinket alwayson on|off`.
  - Included `Bindings.xml` in `.toc`.
