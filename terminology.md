# Terminology

## Fundamentals

<dl>
<dt>IST</dt>
<dd><strong>Inventory Slot Transfer</strong>. Lets you keep item slots through file reloads and mode changes.</dd>

<dt>mCount</dt>
<dd>How many slots wide the game thinks your inventory currently is. IST works by pushing <em>mCount</em> to be some amount lower than it's supposed to be.</dd>

<dt>Offset</dt>
<dd>The number of slots by which <em>mCount</em> is too low. Cannot be partially reduced, but can be removed entirely by fully closing the game.</dd>

<dt>Nuke</dt>
<dd>Any save file made when mCount is at or below 0. The saved inventory will be completely empty.</dd>

<dt>Simulator</dt>
<dd>Piston's excellent <a href="https://ist.itntpiston.app/">IST simulator</a>, which is vital for making and understanding IST setups.</dd>

<dt>mCount 0</dt>
<dd>When your offset and real inventory slot count are exactly the same. In this state, the game will refuse to show you any of your item slots, and any saves will <em>nuke</em>.</dd>

<dt>Negative mCount</dt>
<dd>You have more offset than actual item slots. The inventory will act slightly odd, and any saves will <em>nuke</em>.</dd>

<dt>Stackable</dt>
<dd>An item with a visible quantity (e.g. arrows, materials, korok seeds).</dd>

<dt>Duping</dt>
<dd>When an item slot is transferred through offset, and another slot of the same item loads in from a file, giving you two.</dd>

<dt>Blocking</dt>
<dd>When items transferred with IST prevent other slots from loading in during a file load.</dd>

<dt>GameData</dt>
<dd>A shadow copy of your inventory kept in memory at all times. This copy is what gets written to save files.</dd>

<dt>Syncing</dt>
<dd>Remaking the <em>GameData</em> inventory to match the visible one. The game does this automatically after a lot of common actions.</dd>

<dt>K+<code>n</code> (<code>n</code> is some whole number above 0)</dt>
<dd>Making enough offset to cover all slots in your <em>Key Items</em> tab, plus <code>n</code> more.</dd>

<dt>TOTS</dt>
<dd><strong>Trial Of The Sword</strong>. A DLC-exclusive quest that gives you a temporary inventory with all non-key items removed. Like the shrine quest on Eventide Island, this provides a quick way to get weapons into offset slots.</dd>

## Making offset

<dt>Menu overloading</dt>
<dd>A glitch that blocks most inventory changes being reflected in the overworld. A key part of one way to make <em>offset</em>. This is the quickest way to make a lot of offset, but it requires shock arrows, and multiple multi-shot bows.</dd>

<dt>Arrowless</dt>
<dd>A way of making offset with equipment smuggling glitches. So called because unlike <em>menu overloading</em>, you don't need any arrows to do it. One of the quickest ways to make modest amounts of offset, but has some difficult input timing.</dd>

<dt>Check item</dt>
<dd>An additional item held during one of the steps of making offset with Arrowless. It doesn't affect the glitch itself, but helps verify a difficult input timing.</dd>

<dt>Fairy Offset</dt>
<dd>a way of making offset with fairies and fire. One of the easiest setups, but by far the slowest.</dd>

<dt>PE Offset</dt>
<dd>a way of making offset with <em>prompt entanglement</em>. Can be done anywhere, but requires PE, and is quite slow.</dd>

## Inventory Corruption

<dt>IC</dt>
<dd><strong>Inventory Corruption</strong>. Changes equipment durability and item quantities by making the game write active equipment durability to the wrong slot during a save. Requires a <em>desynced</em> inventory. This term usually refers to an older, non-IST setup of the glitch.

<dt>DIC</dt>
<dd><strong>Direct Inventory Corruption</strong>. Inventory Corruption by transferring items with IST to <em>desync</em> the inventories. Most setups can only copy durability to an item that sorts after the source item.</dd>

<dt>Desync</dt>
<dd>The visible inventory and GameData don't agree on contents, and you deliberately keep it that way during the next save.</dd>

<dt>NGC</dt>
<dd><strong>New Game Corruption</strong>. A strategy of starting a new game, which is never manually saved, to get a much smaller inventory that's easier to use when doing DIC.</dd>

<dt>Reverse Corruption</dt>
<dd>A variant of DIC that copies equipment durability to an item slot that sorts before the source item. It gets its own special name because it's harder to set up.</dd>

## Weapon Modifier Corruption

<dt>WMC</dt>
<dd><em>Weapon Modifier Corruption</em>. Changes modifiers on equipment by making the game write cooking data of a food item to an equipment slot.</dd>

<dt>K+1</dt>
<dd>A method of WMC that only needs <code>K+1</code> offset by using a stackable food. This is by far the recommended method.</dd>

<dt>K+60</dt>
<dd>The first-known method of WMC. It requires over 60 offset, and despite all the YouTube videos on it, there's no reason to do it anymore.</dd>

<dt>Piercing</dt>
<dd><em>Blocking</em> slots that would normally interfere with WMC lets the glitch "ignore" them. The most common case is piercing through arrows when trying to target a weapon or bow.</dd>

<dt>Ultimate 1</dt>
<dd>One of the most useful recipes for WMC, giving all beneficial modifiers. It consists of 1× Endura Carrot, 3× Roasted Endura Carrot, 1× Frozen Hearty Salmon.</dd>

<dt>Ultimate 2</dt>
<dd>An alternative to <em>Ultimate 1</em> that keep bows spread-shot, but requires a critical cook for maximum effect. It consists of 1× Hearty Blueshell Snail, 3× Roasted Endura Carrot, 1× Icy Prime Meat.</dd>

<dt>Ultimate 3</dt>
<dd>A lesser-known alternative to <em>Ultimate 2</em> that doesn't require a critical cook. It consists of 1× Raw Gourmet Meat, 1× Roasted Endura Carrot, 1× Roasted Big Radish, 2× Frozen Bird Thigh.</dd>

## Prompt Entanglement

<dt>PE</dt>
<dd><strong>Prompt Entanglement</strong>. Carries an action submenu from one inventory item and applies it to another.</dd>

<dt>Invalid Slot</dt>
<dd>An on-screen position for the cursor that isn't supposed to occur. Bypasses some of the inventory UI's consistency checks and allows for <em>prompt entanglement</em>.</dd>

<dt>Phantom Tab</dt>
<dd>An inventory tab that isn't empty, but is still locked in the UI.</dd>

<dt>SIIS</dt>
<dd><strong>Star Icon Invalid Slot</strong>. A method of performing </em>prompt entanglement</em>, and often just called <strong>Star</strong>. Obtained from a <em>phantom tab</em>.</dd>

<dt>Arrow PE</dt>
<dd>A way of unlocking <em>Prompt Entanglement</em> by having a lot of arrow slots.</dd>

<dt>System Tab</dt>
<dd>The actual invalid slot obtained with <em>Arrow PE</em>.</dd>

<dt>Phantom Smuggle</dt>
<dd>A glitch that stops the game putting 3D models of held items in Link's hands. It lets you use PE to hold more food and key items without crashing the game.</dd>

<dt>HPE</dt>
<dd>A wrong name for <em>Prompt Entanglement</em>.</dd>

<dt>X-hauling</dt>
<dd>A quick way to reduce arrows by entangling a <em>Hold</em> prompt from a material, and pressing <kbd>X</kbd> to enter the hold state.</dd>

## Save File Nonsense

<dt>Protected autosave</dt>
<dd>An autosave that the game won't choose to overwrite. Any autosave in the future, where there's a manual save even further in the future, is protected.</dd>

<dt>SPS</dt>
<dd><strong>Save Prompt Storage</strong>. A glitch to carry the manual save confirmation prompt over the top of a running game. Requires arrow PE, and the DLC-exclusive Travel Medallion.</dd>

<dt>Blue Hyrule</dt>
<dd>The glitched post-Ganon state of a file saved during the final pre-credits cutscene, so named because the pillars around Hyrule Castle glow blue. You set it up with <em>Save Prompt Storage</em>.</dd>