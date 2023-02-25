# General Terminology

Definition and meaning for terms which aren't specific to any single topic, and which may be referenced from any number of other guides and pages.

## Terminology

Not really glitch-specific, but just so everyone's on the *same page* (pun intended):

1. **Inventory Tab**: These are the tabs at the top of the Inventory menu which group items into logical categories: Weapons, Bows and Arrows, Shields, Armor, Materials, Food, and Key Items.
1. **Inventory Prompt**: When the Inventory menu is open, this is the rectangular square on the left side of the screen that the player moves around in order to inspect or interact with one or more items.
1. **Inventory Details**: When the Inventory menu is open, this pane on the right half of the screen shows information about an item the Inventory Prompt is highlighting.

Terms (sorted alphabetically) usually associated with various glitches:

1. **GameData**: The state of the items in Link's inventory, as it relates to data that is, or may be, saved or loaded.
    - This is *usually* synced with Visible Inventory, where syncing can occur after closing the Game/Inventory menu (*opening* the menu does **not** cause syncing to occur), using the Quick Menu, talking with some NPCs, entering/leaving a shrine, etc.
    - When either **TotS** or **Eventide** are active, syncing with Visible Inventory is disabled. This protects the player's original inventory so items picked up or lost there do not reflect back onto the player's inventory after the trial has ended.
1. **mCount**: The number of items within Visible Inventory which will be removed before a save file is loaded back in.
    - When mCount is negative, items remain unsorted as they load in from the save. Duplication checks **are enabled** so items that already exist in the Inventory due to IST **are ignored** as they are read in from the save file.
    - When mCount is exactly 0 (zero), items remain unsorted as they load in from the save. Duplication checks **are disabled**.
    - When mCount is exactly 1 (one), sorting and duplication checks are the same as when *mCount is negative*: Duplication checks **are enabled** but items remain unsorted.
    - When mCount is 2 (two) or higher, **all items are sorted** (including those unsorted items added earlier) and duplication checks **are enabled**.
1. [Invalid Slot Transfer](/ist/README.md) or "**IST**": Generating invalid slots (also known as "*breaking* slots") allows some items in Link's inventory to remain in the Visible Inventory when reloading a save file (Manual or Autosave).
1. [Prompt Entanglement](/pe/README.md) or "**PE**": Tricking the Inventory menu into thinking that the Inventory Prompt is actually somewhere else than what the Inventory Details is displaying.
1. **Visible Inventory**: The state of each of the items in Link's inventory, when viewed by opening the Menu. This is what the player may interact with in order to Equip, Drop, Hold, or use items.
    - Each item's state may include stats not visible to the player but that still affect the item (such as durability, cook data, etc.).
    - When either Trial of the Sword ("**TotS**") or the Eventide Isle ("**Eventide**") quests are active, no syncing occurs between the Visible Inventory and GameData.
    - Breaking IST slots will only affect **this** state, not the GameData state.

## Switch Controllers

<details>
    <summary>Controller Terminology</summary>

To be consistent in describing inputs throughout the various guides, the inputs for the JoyCon and similar controllers are listed below.

## Left Controller

- **Left Bumper** abbreviated `[L]`.
- **Left Z Bumper** abbreviated `[ZL]`.
- **Minus Button** abbreviated `[-]`.
- **Left Stick** abbreviated `[LS]` with square brackets or `(L)` (it looks like the round top of the stick). It is both an **analog input** as well as a **button**. The notation to indicate that it should be depressed like a button is `(L)-click`, while directional variations may look like `(L)-left`, `(L)-right`, `(L)-up`, or `(L)-down`.
- **D-Pad Buttons** abbreviated `[D]-` followed by a direction: `[D]-left`, `[D]-right`, `[D]-up`, or `[D]-down`. These may be 4 separate buttons marked with arrows, or a single `+`-shaped directional pad.
- **Snapshot Button** which the game is unable to use for inputs.
- **SL Button** and **SR Button** are additional buttons, usually found within the attachment bar of detachable controllers, but are not typically used in the game.

## Right Controller

- **Right Bumper** abbreviated `[R]`.
- **Right Z Bumper** abbreviated `[ZR]`.
- **Plus Button** abbreviated `[+]`.
- **Named Buttons** are `A` (on the right), `B` (on the bottom), `X` (on the top), and `Y` (on the left).
- **Right Stick** abbreviated `[RS]` with square brackets or `(R)` (it looks like the round top of the stick). It is both an **analog input** as well as a **button**. The notation to indicate that it should be depressed like a button is `(R)-click`, while directional variations may look like `(R)-left`, `(R)-right`, `(R)-up`, or `(R)-down`.
- **System Button** which the game is unable to use for inputs.
- **SL Button** and **SR Button** are additional buttons, usually found within the attachment bar of detachable controllers, but are not typically used in the game.
</details>
