# Terminology

## Fundamentals

<dl>
<dt>**IST**</dt>
<dd>_Inventory Slot Transfer_. Lets you keep item slots through file reloads and mode changes.</dd>

<dt>**mCount**</dt>
<dd>How many slots wide the game thinks your inventory currently is. IST works by pushing _mCount_ to be some amount lower than it's supposed to be.</dd>
<dt>**Offset**</dt>
<dd>The number of slots by which _mCount_ is too low. Cannot be partially reduced, but can be removed entirely by fully closing the game.</dd>
<dt>**Nuke**</dt>
<dd>Any save file made when mCount is at or below 0. The saved inventory will be completely empty.</dd>
<dt>**Simulator**</dt>
<dd>Piston's excellent IST simulator at [https://ist.itntpiston.app/]</dd>
<dt>**mCount 0**</dt>
<dd>When your offset and real inventory slot count are exactly the same. In this state, the game will refuse to show you any of your item slots, and any saves will _nuke_.</dd>
<dt>**Negative mCount**</dt>
<dd>You have more offset than actual item slots. The inventory will act slightly odd, and any saves will _nuke_.</dd>
<dt>**Stackable**</dt>
<dd>An item with a visible quantity (e.g. arrows, materials, korok seeds).</dd>
<dt>**Duping**</dt>
<dd>When an item slot is transferred through offset, and another slot of the same item loads in from a file, giving you two.</dd>
<dt>**Blocking**</dt>
<dd>When items transferred with IST prevent other slots from loading in during a file load.</dd>
<dt>**GameData**</dt>
<dd>A shadow copy of your inventory kept in memory at all times. This copy is what gets written to save files.</dd>
<dt>**Syncing**</dt>
<dd>Remaking the _GameData_ inventory to match the visible one. The game does this automatically after a lot of common actions.</dd>
<dt>**`K+n`** (`n` is some whole number above 0)</dt>
<dd>Making enough offset to cover all slots in your _Key Items_ tab, plus `n` more.</dd>
<dt>**TOTS**</dt>
<dd>_Trial Of The Sword_. A DLC-exclusive quest that gives you a temporary inventory with all non-key items removed. Like the shrine quest on Eventide Island, this provides a quick way to get weapons into offset slots.</dd>

## Making offset

**Menu overloading**: A glitch that blocks most inventory changes being reflected in the overworld. A key part of one way to make _offset_. This is the quickest way to make a lot of offset, but it requires shock arrows, and multiple multi-shot bows.
**Arrowless**: A way of making offset with equipment smuggling glitches. So called because unlike _menu overloading_, you don't need any arrows to do it. One of the quickest ways to make modest amounts of offset, but has some difficult input timing.
**Check item**: An additional item held during one of the steps of making offset with Arrowless. It doesn't affect the glitch itself, but helps verify a difficult input timing.
**Fairy Offset**: a way of making offset with fairies and fire. One of the easiest setups, but by far the slowest.
**PE Offset**: a way of making offset with _prompt entanglement_. Can be done anywhere, but requires PE, and is quite slow.

## Inventory Corruption

**IC**: _Inventory Corruption_. Changes equipment durability and item quantities by making the game write active equipment durability to the wrong slot during a save. Requires a _desynced_ inventory. This term usually refers to an older, non-IST setup of the glitch.
**DIC**: _Direct Inventory Corruption_. Inventory Corruption by transferring items with IST to _desync_ the inventories. Most setups can only copy durability to an item that sorts after the source item.
**Desync**: The visible inventory and GameData don't agree on contents, and you deliberately keep it that way during the next save.
**NGC**: _New Game Corruption_. A strategy of starting a new game, which is never manually saved, to get a much smaller inventory that's easier to use when doing DIC.
**Reverse Corruption**: A variant of DIC that copies equipment durability to an item slot that sorts before the source item. It gets its own special name because it's harder to set up.

## Weapon Modifier Corruption

**WMC**: _Weapon Modifier Corruption_. Changes modifiers on equipment by making the game write cooking data of a food item to an equipment slot.
**K+1**: A method of WMC that only needs `K+1` offset by using a stackable food. This is by far the recommended method.
**K+60**: The first-known method of WMC. It requires over 60 offset, and despite all the YouTube videos on it, there's no reason to do it anymore.
**Piercing**: _Blocking_ slots that would normally interfere with WMC lets the glitch "ignore" them. The most common case is piercing through arrows when trying to target a weapon or bow.
**Ultimate 1**: One of the most useful recipes for WMC, giving all beneficial modifiers. https://discord.com/channels/872350971383140422/1003549748902514728/1086779983151779871
**Ultimate 2**, **Ultimate 3**: Alternate WMC mega-recipes that keep bows spread-shot. Ultimate 2 requires a critical cook for maximum effect, but Ultimate 3 does not.

## Prompt Entanglement

**PE**: _Prompt Entanglement_. Carries an action submenu from one inventory item and applies it to another.
**Invalid Slot**: An on-screen position for the cursor that isn't supposed to occur. Bypasses some of the inventory UI's consistency checks and allows for _prompt entanglement_.
**Phantom Tab**: An inventory tab that isn't empty, but is still locked in the UI.
**SIIS**: _Star Icon Invalid Slot_. A method of performing _prompt entanglement_, and often just called _Star_. Obtained from a _phantom tab_.
**Arrow PE**: A way of unlocking _Prompt Entanglement_ by having a lot of arrow slots.
**System Tab**: The actual invalid slot obtained with _Arrow PE_.
**Phantom Smuggle**: A glitch that stops the game putting 3D models of held items in Link's hands. It lets you use PE to hold more food and key items without crashing the game.
**HPE**: A wrong name for _Prompt Entanglement_.
**X-hauling**: A quick way to reduce arrows by entangling a _Hold_ prompt from a material, and pressing `X` to enter the hold state.

## Save File Nonsense

**Protected autosave**: An autosave that the game won't choose to overwrite. Any autosave in the future, where there's a manual save even further in the future, is protected.
**SPS**: _Save Prompt Storage_. A glitch to carry the manual save confirmation prompt over the top of a running game. Requires arrow PE, and the DLC-exclusive Travel Medallion.
**Blue Hyrule**: The glitched post-Ganon state of a file saved during the final pre-credits cutscene, so named because the pillars around Hyrule Castle glow blue. You set it up with _Save Prompt Storage_.