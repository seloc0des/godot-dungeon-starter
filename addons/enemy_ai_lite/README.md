# SELODEV Dungeon Starter

A small, finished dungeon crawl you can press Play on, plus every free SELODEV
Lite system already sitting in the project. No coding required.

Walk into the crypt, fight the goblins and skeletons that come for you, gather
the flasks they drop, clear the room, save your run. Movement is the Controller
system, the monsters think with the Enemy AI system, the hits go through the
Combat system, your sword damage comes from a Stats attack value, what a monster
drops is a Loot table, and the kill count is a Quest. That is seven Lite systems
working together in one small game. All fourteen are in `addons/`, wired through
one event bus.

## Play it (Godot 4.5 or newer)

Open this folder in Godot and press **Play (F5)**.

- **Move:** arrow keys or WASD
- **Attack:** **Space**. The swing hits whatever is in front of you, for as much
  as your Attack stat (top right) says.
- **Grab the drops.** Slain monsters sometimes leave a healing flask. Walk over
  it to drink it. Not every kill drops, and that is the loot table doing its job.
- **Watch your hearts.** Monsters hurt on touch. If you fall, you wake at the
  door with full health.
- **Save and Load:** buttons at the top right.

## Make it yours

- `content/quests.json` is the kill quest. Change the counts, retitle it, or
  add a second quest. No scripts.
- `game/dungeon/crypt_loot.tres` is the drop table. Change the weights to make
  flasks rarer, or point an entry at a new item. A weight-0 or `null` entry is
  the "nothing drops" chance.
- `game/dungeon/attack_stat.tres` is your Attack. Raise the base and every
  swing hits harder. The full Stats system adds skill points and modifiers.
- `game/art/` is the pixel art, CC0 from 0x72's DungeonTileset II (credits in
  `CREDITS.md`). Overwrite a PNG with your own and the game picks it up.
- The room is one rect on the `Ground` node. Resize it in the Inspector and
  the walls and camera follow.
- The monsters are plain scenes. Copy one, change its `enemy_id`, sprite
  frames, health and `loot_table`, and you have a new creature. Add it to the
  quest by its id and the counter tracks it.
- Eleven more systems ship switched off. Turn one on in Project Settings then
  Plugins when your game wants it. Switching one off deletes nothing.

## Run the checks yourself

```bash
godot --headless --path . tools/dungeon/verify.tscn
```

Every other system carries its own suite under `tools/` as well.

## Growing out of the Lite tier

Each Lite system is the free cut of a paid one. The full versions of everything
in this project, plus the Game Kit that wires them together, ship in one
package: **SELODEV Complete** on https://selodev.com/go/complete. One purchase, every
system, drop-in upgrades. Your content and scenes keep working.

## License

MIT for the kit. The art is CC0, credited in `CREDITS.md`. Make it, rename it,
ship it, sell it. That's the point.


## Part of a family

This is one free tier from the selodev catalog of no-code Godot 4 systems. They share an item contract and a save contract, so they plug into each other, and each one also works fully on its own.

Free systems:

- [Inventory Lite](https://github.com/seloc0des/godot-inventory-lite)
- [Equipment Lite](https://github.com/seloc0des/godot-equipment-lite)
- [Loot Lite](https://github.com/seloc0des/godot-loot-lite)
- [Crafting Lite](https://github.com/seloc0des/godot-crafting-lite)
- [Vendor Lite](https://github.com/seloc0des/godot-vendor-lite)
- [Quests Lite](https://github.com/seloc0des/godot-quests-lite)
- [Stats / Skills Lite](https://github.com/seloc0des/godot-stats-skills-lite)
- [Save / Load Lite](https://github.com/seloc0des/godot-save-load-lite)
- [Dialogue Lite](https://github.com/seloc0des/godot-dialogue-lite)
- [Combat Lite](https://github.com/seloc0des/godot-combat-lite)
- [Controller Lite](https://github.com/seloc0des/godot-controller-lite)
- [Enemy AI Lite](https://github.com/seloc0des/godot-enemy-ai-lite)
- [Scene Flow Lite](https://github.com/seloc0des/godot-scene-flow-lite)
- [Audio Lite](https://github.com/seloc0des/godot-audio-lite)
- [Level Builder Lite](https://github.com/seloc0des/godot-level-builder-lite)
- [Weather System Lite](https://github.com/seloc0des/godot-weather-lite)
- [Settings + Menus](https://github.com/seloc0des/godot-settings-menus) (complete and free, no paid tier)

Free VFX: [Magic Cast](https://github.com/seloc0des/godot-magic-cast-vfx-lite), [Elemental Impact](https://github.com/seloc0des/godot-elemental-impact-vfx-lite), [Explosion](https://github.com/seloc0des/godot-explosion-vfx-lite), [Pickup, Buff & Heal](https://github.com/seloc0des/godot-pickup-buff-vfx-lite).

Free starter projects: [Free Starter](https://github.com/seloc0des/free-starter-godot), [Dungeon](https://github.com/seloc0des/godot-dungeon-starter), [Survival](https://github.com/seloc0des/godot-survival-starter), [RPG](https://github.com/seloc0des/godot-rpg-starter).

The full versions add drop-in UI, editor docks and the cross-system wiring. They're on itch.io: **https://selodev.itch.io**
