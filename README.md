# Zelda: Breath of the Wild - Glitch Guides

A compilation of guides, glitch terminology, and links to other Breath of the Wild resources.

Unless otherwise noted, the information here assumes an unmodified version of the game.

## Purpose

The methods to find and exploit glitches in BotW are constantly being discovered and refined, with static guides and videos quickly becoming outdated.

This repo is organized into sections to help you locate the most up-to-date resources as possible.

# Organization

- [Apparatus Storage](./apparatus/README.md)
- [Collaboration Resources](./collab/README.md)
- [Invalid Slot Transfer](./ist/README.md)
- [Prompt Entanglement](./pe/README.md)
- [Online Tools](./tools/README.md)
- [Weapon Modifier Corruption](./wmc/README.md)

## Terminology

1. **Inventory Prompt**: When the Inventory menu is open, this is the rectangular square on the left side of the screen that the player moves around in order to inspect or interact with one or more items.
1. **Inventory Details**: When the Inventory menu is open, this pane on the right half of the screen shows information about an item the Inventory Prompt is highlighting.
1. [Prompt Entanglement](./pe/README.md) or "**PE**": Tricking the Inventory menu into thinking that the Inventory Prompt is actually somewhere else than what the Inventory Details is displaying.
1. [Invalid Slot Transfer](./ist/README.md) or "**IST**": Generating invalid slots (also known as "*breaking* slots") allows some items in Link's inventory to remain in the Visible Inventory when reloading a save file (Manual or Autosave).
1. **Visible Inventory**: The state of each of the items in Link's inventory, when viewed by opening the Menu. This is what the player may interact with in order to Equip, Drop, Hold, or use items.
    - Each item's state may include stats not visible to the player but that still affect the item (such as durability, cook data, etc.).
    - When either Trial of the Sword ("**TotS**") or the Eventide Isle ("**Eventide**") quests are active, no syncing occurs between the Visible Inventory and GameData.
    - Breaking IST slots will only affect **this** state, not the GameData state.
1. **GameData**: The state of the items in Link's inventory, as it relates to data that is, or may be, saved or loaded.
    - This is *usually* synced with Visible Inventory, where syncing can occur after closing the Game/Inventory menu (opening the menu does **not** sync them), using the Quick Menu, talking with some NPCs, entering/leaving a shrine, etc.
    - When either **TotS** or **Eventide** are active, syncing with Visible Inventory is disabled. This protects the player's original inventory so items picked up or lost there do not reflect back onto the player's inventory after the trial has ended.
1. **mCount**: The number of items within Visible Inventory which will be removed before a save file is loaded back in.
    - When mCount is negative, items remain unsorted as they load in from the save. Duplication checks **are enabled** so items that already exist in the Inventory due to IST **are ignored** as they are read in from the save file.
    - When mCount is exactly 0 (zero), items remain unsorted as they load in from the save. Duplication checks **are disabled**.
    - When mCount is exactly 1 (one), sorting and duplication checks are the same as when *mCount is negative*: Duplication checks **are enabled** but items remain unsorted.
    - When mCount is 2 (two) or higher, **all items are sorted** (including those unsorted items added earlier) and duplication checks **are enabled**.
