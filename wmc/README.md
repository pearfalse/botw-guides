# Weapon Modifier Corruption

The process of first corrupting meal Cook Data, and then using that to change the modifiers of Weapons, Bows and Shields.

# Transferring Equipment Durability by [crystal_l#6235](https://discord.com/channels/872350971383140422/999115384596742194/999314496965333092)

**Note:** This requires items *left* of "**E**" that you can dupe, as well as the same number of empty/available slots that the dupes will go into.

## Terminology

1. "**E**": Source equipment with the durability you want to transfer ***from***.
1. "**T**": Target equipment you want to transfer durability ***to***.
1. "**X**": Number of slots *between* "**E**" and "**T**", exclusive.
1. "**K**": Total slots to the right of "**E**" that cannot be dropped/sold/removed, including unsellable Armor and Key Items.

### To transfer equipment durability to the right:

1. Start on target save (`save_1`) that contains the source item "**E**" (weapon/bow/arrow/shield) and target slot "**T**" (usually some type of arrow or material) somewhere to its right.
    - If "**T**" is an arrow stack, it should be equipped and have at least 1 arrow.
1. Equip "**E**" but unequip everything else (to avoid additional unwanted corruption), then trigger an autosave (`save_2`).
1. Calculate "**X**" (the number of slots *between* "**E**" and "**T**", exclusive).
    - This only works if there are at least "**X**" items *left* of "**E**" to dupe, as well as available space for all duped "**X**" items.
    - For example: if you have 4 bows, you also need to have 4 empty bow slots to *accept* them so the offset is fully realized.
1. Calculate "**K**" (the number of non-droppable slots *right* of "**E**", excluding "**E**").
    - This includes "**T**" as well as unsellable Armor, Key Items, etc.
1. Generate "**X**+**K**+1" offset slots, then ***drop everything you can*** to the right of "**E**".
    - You will drop "**T**" as well.
    - As a reminder: Nothing except "**E**" should be equipped, as it can help chaining more iterations of Inventory Corruption together by avoiding having multiple equipped items temporarily during step 6.
1. Load the previous autosave (`save_2`). If "**E**" is a type of arrow, then fire a shot (-1 durability to target).
    - As explained on the IST Simulator: *When reloading a save with desynced game data, the equipped weapon/bow/shield are automatically corrupted, but not the arrows. To corrupt the equipped arrow slot, you need to shoot an arrow.*
1. **Without syncing your inventory**, trigger an autosave (`save_3`).
    - Don't close any menu (including the Quick Menu), pick up anything, faint and use a fairy, break a weapon, enter a shrine, etc.
    - Firing an arrow in the step above does *not* cause your inventory to sync.
1. Close and restart game, then load this autosave (`save_3`) and you should notice "**T**" has been increased to **E**'s durability x 100 (truncated at 999 for materials).

Repeat steps 2 through 8 for any other items you'd like corrupted in this way.

### To transfer equipment durability using negative mCount:

1. Equip Hylian Shield ("**E**") in last Shield slot; unequip everything else (unless following a specific plan).
    - If "**E**" is not already in the last slot, just drop and pick it back up (leave it equipped).
1. Count the number of Key Items + Unsellable Armor; call this value "**K**".
1. Have at least 1 target weapon "**T**", and "**K**" other weapons/bows/shields.
1. Generate offset = (inventory size - 1).
1. Drop and pick up **T**.
1. Drop and pick up an additional "**K**" weapons/bows/other shields.
1. Autosave, close the game, and reload.
1. Autosave without syncing inventory, then reload.
1. "**T**" should now have the durability of the Hylian Shield.
