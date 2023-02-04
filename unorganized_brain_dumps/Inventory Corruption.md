# Breath of the Wild: Weapon, Bow, Shield Corruption

# Terminology
1. Inventory Prompt: When the Inventory menu is open, this is the rectangular square on the left side of the screen that the player moves around in order to inspect some item in Link's inventory.
1. Inventory Details: When the Inventory menu is open, this pane on the right half of the screen shows information about whichever item the Inventory Prompt is highlighting.
1. PE: *Prompt Entanglement*. Tricking the Inventory menu into thinking that the Inventory Prompt is actually somewhere else than what the Inventory Details is displaying.
1. IST: *Invalid Slot Transfer*. Generating (or "*breaking*") invalid slots allows some items in Link's inventory to remain in the underlying linked list when reloading any save (Manual or Autosave) file.
1. Visible Inventory: The state of each of the items in Link's inventory, when viewed by opening the Menu. This is what the player may interact with in order to Equip, Drop, Hold, or use items.
    - Each item's state may include stats not visible to the player but that affect the item (such as durability, cook data).
    - The physical layout of the underlying linked list may differ from what the Player sees due to IST: Weapons (regardless of actual order) are typically sorted first, but may actually occur later in the list.
    - When either Trial of the Sword (ToS/TotS) or the Eventide Isle quests are active, opening and closing menus will ***not*** sync the Visible Inventory ("memory") with GameData.
    - Breaking slots for IST affect **this** state, not the GameData state.
1. GameData: The state of the items in Link's inventory, as is correlates to data to be saved or loaded.
    - This is usually synced with Visible Inventory, where syncing can occur after entering/leaving a shrine, closing (but not opening) the Game/Inventory menu, using the Quick Menu, talking with some NPCs, etc.
    - When either Trial of the Sword (ToS/TotS) or the Eventide Isle quests are active, syncing with Visible Inventory is disabled. This protects the player's original inventory so items picked up or lost there do not reflect back onto the player's inventory after the trial has ended.
1. mCount: Number of items within Visible Inventory which are cleared as a save file is loaded.
    - A negative mCount will prevent duplicate items, but items are left unsorted as they load in from the save.
    - A zero mCount will **not** prevent duplicate items, and items are not sorted as they load in from the save.
    - An mCount of 1 will prevent duplicate items, but items are not sorted.
    - A positive mCount above 1 will prevent duplicate items

# Protected Autosaves

These are autosaves that are generated while the Switch's system clock is set to some date in "the future" (relative, at least, to the system clock while you play the game in "the present"). Note that "the present" can be any date or time you wish to set the system clock to.

Master Mode provides two save slots; one of them 

## Safeties

The game ***will not overwrite*** your Manual Save with an autosave.

## Limitations

The game's autosave system *will* reuse the oldest save slot

You cannot create Protected Autosaves on Master Mode.

- **NOTE 2:** 
- **NOTE 3:** You may create more than one Protected Autosave in Normal Mode.
- **NOTE 4:** The game's autosave system *will* overwrite the oldest autosave slot, even if you attempt to protect them all.
- **NOTE 3:** The game's autosave system *will* overwrite the oldest autosave slot, even if you attempt to protect them all.
    - This means that 

## Theory

The game may reuse any save slot for a new autosave except:
1. A slot containing the player's Manual Save (your manually-saved file will not be overwritten by an autosave).
1. Any slot containing an autosave with a timestamp set ***between*** the Manual Save's "future" timestamp and "the present" (so older than your manual save, but newer than your system clock right now).
    - This means that autosaves with a timestamp *further in the future* than the Manual Save **can be overwritten**, as well as all autosaves with a timestamp *before* "the present" (starting with the oldest).

> I have manually saved by accident while corrupting my inventory -- several times -- after a point where I have no autosaves close to where I had progressed to in my main file.
> I now create an emergency Protected Autosave with roughly the same progression as my main save to have on hand for just this reason.

You may have more than one Protected Autosave at a time, so long as you remember that the timestamp for your Manual Save must be later than the autosaves you wish to protect.

## Steps

1. Change the Switch's system clock (1st time) to some date in the future (like tomorrow, next week, next month).
1. Load your main save, then generate an autosave; this is `Protected_Autosave` and should have this "future" date in its timestamp. It should show up at the top of the Load Game list (due to its date).
1. Change the Switch's system clock (2nd time) to a date further in the future than `Protected_Autosave` (like one day later).
1. Manually save; this should now appear at the top of the Load Game list (it should have the "most" future date), followed by `Protected_Autosave` (that should have the "next most" future date), followed by all the remaining autosaves.
1. Change the Switch's system clock (3nd time) back to the present; any autosaves generated after this point should always be listed after/below both the Manual Save and `Protected_Autosave`.
1. ***If you manually save*** during any of the corruption steps below, stop what you're doing immediately (especially anything that can generate a new autosave) and:
    1. (Optional) Restart the game to clear the IST offsets and avoid transferring un-corrupted seeds/orbs into `Protected_Autosave`.
    1. Load `Protected_Autosave`, then repeat Steps 3-5 above to re-save the manual save with the correct date.

## Arrow Stack Corruption: An Explanation
- Basically, there are multiple copies of the inventory; two of them would be memory (aka the Visible Inventory) and GameData.
- When you **save**, the game copies the durability of the equipped items *from* memory *to* GameData.
- When you **reload**, it copies the durability of the equipped items *from* GameData *to* memory.
- Normally, memory and GameData are always synced.
- But when you transfer items with IST into a file, they will land in memory and update it, but they won't update GameData (aka syncing GameData) until you do an action that interacts with the inventory (use the QuickMenu, or pick up an item, aka syncing GameData).
- If you save in this state, it will copy the durability *from* memory *to* GameData, but because the inventories are desynced, the durability gets copied to the wrong items.
- Those items will be corrupted, but they are not in memory *yet*.
- If you then reload, it will load in the items *from* GameData *to* memory and you can see the corrupted items.
- Because the durability of weapons, bows and shields is actually 100 times higher than you might think, you will get 100 more materials/meals/arrows/champions than you would expect.
- This 100 times rule does NOT apply for arrows.
- You can also copy the "durability" from arrows to other items, but it requires shooting an arrow before saving or it won't write the durability to GameData.

## Durability Transfer from Shield


## Inventory Setup and IST-offsets

There are two states that you will want to have:
1. The "Manual Save" state, where all obtained items, progress, and Key Items may be resumed after corruption is complete.
1. Various "Autosave" states, which will have a minimal amount of Weapons, Bows and/or Arrows\* *(see Note 1)*, Shields, Materials\* *(see Note 2)*, Meals\* *(see Note 3)*, and Key Items\* *(see Note 4)*.
    1. ***Note 1:*** Some of the steps further down require generating (or "breaking") a lot of IST slots, and it may be more convenient to use multiple Multi-Shot Bows combined with a Shock Arrow to overload the menu, than to break slots using the "Arrowless Offsets" method.

        This will require that you keep enough materials/meals so you can "eat" the Shock Arrows (and its empty arrow stack) in some of the later parts of this guide.
    1. ***Note 2:*** Materials are used for two purposes: in generating IST slots, and when using Prompt Entanglement ("***PE***") Sell **all but 2** of each Materials *per stack*.
    For most of the steps below, you will want to have at least 3 tabs' worth of Materials, although 4-6 Material tabs make things easier.

        Materials that can be eaten/drunk are preferable, since they can be both consumed *and* dropped, depending on your needs at the time.

         You can duplicate stacks of Materials (same item, but taking up more than one Material slot) to generate multiple tabs' worth 
        
    1. ***Note 4:*** Due to the special case of the **Champion+ Ability** slots duplicating on reload (see bullet point 1.2 below), it may be necessary to start a new game and progress until you've unlocked Link's house in Hateno Village. Information on that is provided further down.

An ideal setup will have minimal unnecessary items (*not* including Materials and Meals... yet).

1. **Key Items:** Corrupt stackable KIs like Korok Seeds to 999 (steps to do that are provided further down), but remove everything else possible. Get rid of all Spirit Orbs.
    1. "**Champion**" Abilities do not duplicate, but "**Champion+**" Abilities *can*:
        1. If the save file contains a "*Link has defeated this Divine Beast a second time and earned the **Champion+** Ability*" flag, the Champion+ Ability slots **will dupe** on reload.
        1. If a Champion+ Ability has been transferred into a (new) save file, the Champion+ Ability slots **will not dupe** on reload. ***This is the ideal save file!***
    1. You
1. **Materials:** Sell all but last (1-2) of each item.
1. **Arrows:** Get rid of them all (eat the empty stacks, too).
1. Generate *K+60* offsets.
1. Cook some non-stackable food, like an apple in a Cooking Pot.
1. Generate `Autosave_1`.
1. Reload `Autosave_1` enough times to duplicate up to 60 food

## Link's House: Mounts

### Note: You do not want the Bow of Light ("**BoL**") to be in Link's inventory; you want it on the Bow Mount until the very end of these steps.
1. Put the Bow of Light ("BoL") on the mount.
1. Remove the BoL from Link's inventory.
    1. If you can use Prompt Entanglement:
        1. Stand close to a steep cliff/ledge, with Link's back toward it (when you drop it, the BoL drops behind Link).
        1. Entangle the prompt with the BoL (its name and description should be displayed on the right).
        1. Switch tabs (in groups of 3) to the right until the prompt highlights one of the Materials.
        1. Bring up the action prompt (usually the "**A**" button) and select ***Equip*** (the name and description should change to whatever Material you have selected).
        1. Switch tabs (in groups of 3) back to the Bows tab, so the BoL is highlighted.
        1. Bring up the action prompt (again, with the "**A**" button) and select ***Hold***.

            Link should go into the open-handed "holding an item" stance, but his hands should be empty.
        1. Close the menu (with the "**`+`**" button) and ***immediately run away*** from the cliff/ledge and the BoL.

            - The Bow of Light will appear behind Link's back (hopefully over the cliff/ledge), hovering in the air, and slowly fall till it reaches the ground.
            - The BoL will "magnet" toward Link if you don't get away fast enough.
    1. If you can't use Prompt Entanglement:
        1. Use IST to "shift" the BoL 
        1. You can shift the BoL to the end of the Bows tab by having no empty bow slots (fill rest of Bow inventory with regular bows), putting the BoL onto a wall mount (which duplicates it into the mount, as well as shifts it to the end), trigger `Autosave_2`, sort the BoL back to the beginning of the bow inventory, drop all shields and materials and eat 1 meal, so IST offset includes the last bow, and reload `Autosave_2` so BoL is shifted off the bows list. Trigger `Autosave_3`.
    1. Or, using Prompt Entanglement, drop the BoL off a ledge, and trigger `Autosave_3`.

# Corrupting Stackable Key Items

Most of the steps are similar for corrupting 999x Korok Seeds as for corrupting 999x Spirit Orbs.

This should be done in Normal Mode, as 3 separate autosaves are required.

**Before you begin:** You may need to restart your game if you had generated any IST offsets before starting **Step 1** of either of the subsections; you don't want to accidentally transfer in items from your main save that can get saved into any of your autosaves.

**Once you begin:** Don't manually save (till the very end) in case something unexpected occurs. This way, you can restart your main save if you have any problems.

## Theory

You start with a new game and **only** a Sheikah Slate, gather the Woodcutter's Axe (this weapon specifically because of its durability value), generate `Autosave_1` *before* collecting the desired stackable Key Item, generate `Autosave_2` *after* collecting the desired stackable Key Item, and generate a specially-desynced `Autosave_3` after performing some very specific series of events but ***without syncing GameData*** first. A lot of autosave reloading is required.
- A tree branch has 4 durability (this would only corrupt 400x seeds/orbs).
- A torch has 8 durability (this would corrupt 800x seeds/orbs, which may allow some duplication to still occur).
- The Woodcutter's Axe has 47 durability (4700 gets capped at 999 seeds/orbs).

Some of the steps below may include bullet points that detail the ***what*** and/or ***why*** of the process. (I would rather include boring information that you're free to skip, than have you not understand the reasons behind something.)



Before you start: you don't want to accidentally transfer in any items with IST offsets; restart the game if necessary to clear them.

## 999x Korok Seeds

1. Start a new game
    - Don't manually save, or it will overwrite your main save
    - Don't collect armor or arrows
    - Don't collect Korok Seeds
1. Collect the WoodCutter's Axe; leave it **equipped**
    - It's okay if you pick up other materials and weapons (not arrows/armor) along the way
    - Don't collect Korok Seeds
1. Enter any shrine
1. Drop everything except the Woodcutter's Axe
1. Get the rune
    - You will get an autosave after collecting the rune; this is `Autosave_1`
1. Beat the shrine
    - You should receive the Spirit Orb
    - You will get another autosave; this is `Autosave_2`
1. Load your main file
1. Create two offset slots
1. Load `Autosave_1` (the one before collecting the spirit orb)
1. Unequip the Woodcutter's Axe
    - Repeat these last 2 steps until you have two unequipped Woodcutter's Axes **and** they are behind your Key Items
    - The first few times, the Weapons tab containing the axe(s) is left of the Key Items tab; then, the Weapons tab with the axe(s) will appear *after* the KIs tab
1. Load `Autosave_2` (the one after collecting the spirit orb)
    - Do not sync GameData here: don't pick up items, open the menu, use the QuickMenu, etc.
1. Walk around until you get another autosave; this is `Autosave_3`.
1. Load `Autosave_1` (be sure that you don't close the menu when doing this, or it syncs GameData)
    - Repeat this step until you have no Spirit Orbs left in your Key Items (again: don't close the menu when doing this, or it syncs GameData)
1. Load `Autosave_3` (the one after walking around and NOT syncing the GameData)
    - The Spirit Orbs should be corrupted to 999 and be in one of the slots covered by your 2 offsets
1. Load your main save
1. Sync GameData (opening and closing the Inventory is usually enough)
1. Open your Inventory (again) to check that everything looks good
    - You may manually save if you're satisfied and didn't accidentally duplicate something

### 999x Spirit Orbs

1. Start a new game
    - Don't manually save, or it will overwrite your main save
    - Don't collect armor or arrows
    - Don't collect Korok Seeds
1. Collect the WoodCutter's Axe; leave it **equipped**
    - It's okay if you pick up other materials and weapons (not arrows/armor) along the way
    - Don't collect Korok Seeds
1. Enter any shrine
1. Drop everything except the Woodcutter's Axe
1. Get the rune
    - You will get an autosave after collecting the rune; this is `Autosave_1`
1. Beat the shrine
    - You should receive the Spirit Orb
    - You will get another autosave; this is `Autosave_2`
1. Load your main file
1. Create two offset slots
1. Load `Autosave_1` (the one before collecting the spirit orb)
1. Unequip the Woodcutter's Axe
    - Repeat these last 2 steps until you have two unequipped Woodcutter's Axes **and** they are behind your Key Items
    - The first few times, the Weapons tab containing the axe(s) is left of the Key Items tab; then, the Weapons tab with the axe(s) will appear *after* the KIs tab
1. Load `Autosave_2` (the one after collecting the spirit orb)
    - Do not sync GameData here: don't pick up items, open the menu, use the QuickMenu, etc.
1. Walk around until you get another autosave; this is `Autosave_3`.
1. Load `Autosave_1` (be sure that you don't close the menu when doing this, or it syncs GameData)
    - Repeat this step until you have no Spirit Orbs left in your Key Items (again: don't close the menu when doing this, or it syncs GameData)
1. Load `Autosave_3` (the one after walking around and NOT syncing the GameData)
    - The Spirit Orbs should be corrupted to 999 and be in one of the slots covered by your 2 offsets
1. Load your main save
1. Sync GameData (opening and closing the Inventory is usually enough)
1. Open your Inventory (again) to check that everything looks good
    - You may manually save if you're satisfied and didn't accidentally duplicate something

## 999x Stamina And Speed Foods
1. Infinite Endura Food: Stamina
    1. 5x Endura Carrot into 1 Endura Food (2 yellow stamina wheels)
1. Infinite Speed Food: Speed
    1. 1x Farosh Horn, 4x Fleet Lotus Seeds into 1 Speed Food (3x speed up @ 30:00)
1. Should have 57 "other" meals, then 1x stackable, then Endura Food, then Speed Food.
1. https://youtu.be/9SEUChxcT2A?t=4543

Run, glide infinitely.


# Additional Notes

1. Unlock row 3 with [[R]-Left, [D]-Up, [R]-Right, [D]-Left](https://discord.com/channels/872350971383140422/997616079977316352/1007061460632993814):
    1. Unlock row 3
        1. Row 4, Column 5
        2. [R]-Left, [D]-Up, [R]-Right, [D]-Left
        3. This should leave you on the current page, column 0
    2. [D]-Left
    3. Move cursor to row 4 col 1
    4. [D]-Left, [D]-Right, 2x [RS]-Right, [D]-Right


## Current Autosave:

1. `Save as SoR`
1. `Has 19 weapon slots`
1. `Has 13 bow slots`
1. `Has 20 shield`
1. `Initialize 1 MasterSword[modifier=AttackUp,hp=120,equip] 1 SpringLoadedHammer 1 RoyalBroadsword[modifier=AttackUp,hp=24] 1 Flameblade 1 Frostblade[modifier=LongThrow] 1 Thunderblade 1 LizalTriBoomerang[modifier=AttackUp,hp=19] 1 SavageLynelSword[modifier=AttackUp,hp=22] 1 MeteorRod[modifier=AttackUp,hp=7] 1 BlizzardRod[modifier=DurabilityUp] 1 ThunderstormRod[modifier=AttackUp,hp=15] 1 IronSledgehammer[modifier=AttackUp,hp=120] 1 EdgeOfDuality[modifier=DurabilityUp] 1 AncientBladesaw 1 RoyalGuardsClaymore[modifier=LongThrow] 1 GreatThunderblade 1 SavageLynelCrusher[modifier=AttackUp,hp=27] 1 WoodenMop 4 SavageLynelBow[modifier=AttackUp,hp=120] 1 GreatEagleBow 1 ForestDwellersBow[modifier=AttackUp,hp=9] 1 RoyalBow[modifier=AttackUp,hp=12] 1 AncientBow 1 GoldenBow[modifier=QuickShot] 1 BowOfLight[modifier=GuardUp,hp=120,equip] 1 BowOfLight[modifier=AttackUp,hp=120] 643 NormalArrow 306 FireArrow 309 IceArrow 728 ShockArrow 197 BombArrow 380 AncientArrow 2 HylianShield[modifier=AttackUp,hp=120] 1 AncientShield[modifier=AttackUp,hp=120,equip] 1 AncientShield[modifier=AttackUp,hp=120] 1 TravelersShield[modifier=AttackUp,hp=120] 2 SavageLynelShield[modifier=GuardUp,hp=16] 1 RoyalShield[modifier=GuardUp,hp=15] 2 RoyalGuardsShield[modifier=DurabilityUp] 1 SavageLynelShield[modifier=DurabilityUp] 1 RadiantShield[modifier=GuardUp,hp=13] 1 RadiantShield[modifier=DurabilityUp] 1 KiteShield[modifier=GuardUp,hp=14] 1 SoldiersShield 1 RustyShield[modifier=GuardUp,hp=9] 90 OldShirt 3 HeartyDurian 3 PalmFruit 3 Apple 3 Wildberry 3 Hydromelon 3 SpicyPepper 3 Voltfruit 3 FleetLotusSeeds 3 MightyBananas 3 BigHeartyTruffle 3 HeartyTruffle 3 EnduraShroom 3 HylianShroom 3 StamellaShroom 3 Chillshroom 3 Sunshroom 3 Zapshroom 3 Rushroom 3 Razorshroom 3 Ironshroom 3 SilentShroom 3 BigHeartyRadish 3 HeartyRadish 3 EnduraCarrot 3 HyruleHerb 3 SwiftCarrot 3 FortifiedPumpkin 3 CoolSafflina 3 WarmSafflina 3 ElectricSafflina 3 SwiftViolet 3 MightyThistle 3 Armoranth 3 BlueNightshade 3 SilentPrincess 3 RawGourmetMeat 3 RawWholeBird 3 RawPrimeMeat 3 RawBirdThigh 3 RawMeat 3 RawBirdDrumstick 3 CourserBeeHoney 3 HylianRice 3 BirdEgg 3 TabanthaWheat 3 FreshMilk 3 Acorn 3 ChickalooTreeNut 3 CaneSugar 3 GoatButter 3 GoronSpice 3 RockSalt 3 MonsterExtract 3 StarFragment 3 DinraalsScale 3 DinraalsClaw 3 ShardOfDinraalsFang 3 ShardOfDinraalsHorn 3 NaydrasScale 3 NaydrasClaw 3 ShardOfNaydrasFang 3 ShardOfNaydrasHorn 3 FaroshsScale 3 FaroshsClaw 3 ShardOfFaroshsFang 3 ShardOfFaroshsHorn 3 HeartySalmon 3 HeartyBlueshellSnail 3 HeartyBass 3 HyruleBass 3 StaminokaBass 3 ChillfinTrout 3 SizzlefinTrout 3 VoltfinTrout 3 StealthfinTrout 3 MightyCarp 3 ArmoredCarp 3 SankeCarp 3 MightyPorgy 3 ArmoredPorgy 3 SneakyRiverSnail 3 RazorclawCrab 3 IronshellCrab 3 BrightEyedCrab 157 Fairy 1 Fairy 3 WinterwingButterfly 3 SummerwingButterfly 3 ThunderwingButterfly 3 SmotherwingButterfly 3 ColdDarner 3 WarmDarner 3 ElectricDarner 3 RestlessCricket 3 BladedRhinoBeetle 3 RuggedRhinoBeetle 3 EnergeticRhinoBeetle 3 SunsetFirefly 3 HotFootedFrog 3 TirelessFrog 3 HightailLizard 3 HeartyLizard 3 FireproofLizard 3 Flint 3 Amber 3 Opal 3 LuminousStone 3 Topaz 3 Ruby 3 Sapphire 3 Diamond 3 BokoblinHorn 3 BokoblinFang 3 BokoblinGuts 3 MoblinHorn 3 MoblinFang 3 MoblinGuts 3 LizalfosHorn 3 LizalfosTalon 3 LizalfosTail 3 IcyLizalfosTail 3 RedLizalfosTail 3 YellowLizalfosTail 3 LynelHorn 3 LynelHoof 3 LynelGuts 3 ChuchuJelly 3 WhiteChuchuJelly 3 RedChuchuJelly 3 YellowChuchuJelly 3 KeeseWing 3 IceKeeseWing 3 FireKeeseWing 3 ElectricKeeseWing 3 KeeseEyeball 3 OctorokTentacle 3 OctorokEyeball 3 OctoBalloon 3 MoldugaFin 3 MoldugaGuts 3 HinoxToenail 3 HinoxTooth 3 HinoxGuts 3 AncientScrew 3 AncientSpring 3 AncientGear 3 AncientShaft 3 AncientCore 3 GiantAncientCore 3 Wood 999 BakedApple[modifier=AttackUp,hp=120] 1 SheikahSlate 1 MiphasGracePlus 1 RevalisGalePlus 1 DaruksProtectionPlus 1 UrbosasFuryPlus 1 Paraglider 999 KorokSeed 1 ClassifiedEnvelope 1 MedalOfHonorMolduga 1 RoyalBridle 1 MonsterBridle 1 AncientBridle 1 RoyalSaddle 1 MonsterSaddle 1 AncientSaddle 1 TravelMedallion`
1. `Save`
1. `Initialize 1 MasterSword[modifier=AttackUp,hp=120,equip] 1 WoodenMop 1 SavageLynelBow[modifier=AttackUp,hp=120] 1 BowOfLight[modifier=GuardUp,hp=120,equip] 1 BowOfLight[modifier=AttackUp,hp=120] 643 NormalArrow 306 FireArrow 309 IceArrow 728 ShockArrow 197 BombArrow 380 AncientArrow 1 HylianShield[modifier=AttackUp,hp=120] 1 RustyShield[modifier=GuardUp,hp=9] 3 HeartyDurian 3 PalmFruit 3 Apple 3 Wildberry 3 Hydromelon 3 SpicyPepper 3 Voltfruit 3 FleetLotusSeeds 3 MightyBananas 3 BigHeartyTruffle 3 HeartyTruffle 3 EnduraShroom 3 HylianShroom 3 StamellaShroom 3 Chillshroom 3 Sunshroom 3 Zapshroom 3 Rushroom 3 Razorshroom 3 Ironshroom 3 SilentShroom 3 BigHeartyRadish 3 HeartyRadish 3 EnduraCarrot 3 HyruleHerb 3 SwiftCarrot 3 FortifiedPumpkin 3 RawGourmetMeat 3 RawWholeBird 3 RawPrimeMeat 3 RawBirdThigh 3 RawMeat 3 RawBirdDrumstick 3 CourserBeeHoney 3 HylianRice 3 BirdEgg 3 TabanthaWheat 3 FreshMilk 3 Acorn 3 ChickalooTreeNut 3 HeartySalmon 3 HeartyBlueshellSnail 3 HeartyBass 3 HyruleBass 3 StaminokaBass 3 ChillfinTrout 3 SizzlefinTrout 3 VoltfinTrout 3 StealthfinTrout 3 MightyCarp 3 ArmoredCarp 3 SankeCarp 3 MightyPorgy 3 ArmoredPorgy 3 SneakyRiverSnail 3 RazorclawCrab 3 IronshellCrab 3 BrightEyedCrab 157 Fairy 1 Fairy 3 Wood 999 BakedApple[modifier=AttackUp,hp=120] 1 MiphasGracePlus 1 RevalisGalePlus 1 DaruksProtectionPlus 1 UrbosasFuryPlus 999 KorokSeed 1 TravelMedallion`
1. `Save as autosave1`
1. `Break 17 slots`
1. `Reload SoR`
1. `# Activate SIS for Prompt Entanglement`
1. `Reload autosave1`
1. `Eat MiphasGracePlus from slot 1`
1. `Eat RevalisGalePlus from slot 1`
1. `Eat DaruksProtectionPlus from slot 1`
1. `Eat UrbosasFuryPlus from slot 1`
1. `Sync GameData`
1. `Save as autosave1`


```
Weapons:
	MasterSword, TreeBranch, Torch, SoupLadle, Boomerang, SpringLoadedHammer, TravelersSword, SoldiersBroadsword, KnightsBroadsword, RoyalBroadsword, ForestDwellersSword, ZoraSword, FeatheredEdge, GerudoScimitar, MoonlightScimitar, ScimitarOfTheSeven, EightfoldBlade, AncientShortSword, RustyBroadsword, RoyalGuardsSword, Flameblade, Frostblade, Thunderblade, GoddessSword, Sword, SeaBreezeBoomerang, BokoClub, SpikedBokoClub, DragonboneBokoClub, LizalBoomerang, LizalForkedBoomerang, LizalTriBoomerang, GuardianSword, GuardianSwordPlus, GuardianSwordPlusPlus, LynelSword, MightyLynelSword, SavageLynelSword, FireRod, MeteorRod, IceRod, BlizzardRod, LightningRod, ThunderstormRod, ViciousSickle, DemonCarver, OneHitObliterator, BokoblinArm, LizalfosArm, KorokLeaf, FarmingHoe, BoatOar, WoodcuttersAxe, DoubleAxe, IronSledgehammer, GiantBoomerang, TravelersClaymore, SoldiersClaymore, KnightsClaymore, RoyalClaymore, SilverLongsword, CobbleCrusher, StoneSmasher, BoulderBreaker, GoldenClaymore, EightfoldLongblade, EdgeOfDuality, AncientBladesaw, RustyClaymore, RoyalGuardsClaymore, GreatFlameblade, GreatFrostblade, GreatThunderblade, SwordOfTheSixSages, BiggoronsSword, FierceDeitySword, BokoBat, SpikedBokoBat, DragonboneBokoBat, MoblinClub, SpikedMoblinClub, DragonboneMoblinClub, AncientBattleAxe, AncientBattleAxePlus, AncientBattleAxePlusPlus, LynelCrusher, MightyLynelCrusher, SavageLynelCrusher, Windcleaver, MoblinArm, WoodenMop, FarmersPitchfork, FishingHarpoon, ThrowingSpear, TravelersSpear, SoldiersSpear, KnightsHalberd, RoyalHalberd, ForestDwellersSpear, ZoraSpear, SilverscaleSpear, CeremonialTrident, LightscaleTrident, Drillshaft, FeatheredSpear, GerudoSpear, SerpentineSpear, AncientSpear, RustyHalberd, RoyalGuardsSpear, Flamespear, Frostspear, Thunderspear, BokoSpear, SpikedBokoSpear, DragonboneBokoSpear, MoblinSpear, SpikedMoblinSpear, DragonboneMoblinSpear, LizalSpear, EnhancedLizalSpear, ForkedLizalSpear, GuardianSpear, GuardianSpearPlus, GuardianSpearPlusPlus, LynelSpear, MightyLynelSpear, SavageLynelSpear, Weapon

Bows:
	BowOfLight, WoodenBow, TravelersBow, SoldiersBow, KnightsBow, RoyalBow, ForestDwellersBow, SilverBow, SwallowBow, FalconBow, GreatEagleBow, GoldenBow, PhrenicBow, AncientBow, RoyalGuardsBow, TwilightBow, BokoBow, SpikedBokoBow, DragonBoneBokoBow, LizalBow, StrengthenedLizalBow, SteelLizalBow, LynelBow, MightyLynelBow, SavageLynelBow, DuplexBow, Bow

Arrows:
	NormalArrow, FireArrow, IceArrow, ShockArrow, BombArrow, AncientArrow

Shields:
	HylianShield, PotLid, WoodenShield, EmblazonedShield, HuntersShield, FishermansShield, TravelersShield, SoldiersShield, KnightsShield, RoyalShield, ForestDwellersShield, SilverShield, KiteShield, GerudoShield, RadiantShield, Daybreaker, ShieldOfTheMindsEye, AncientShield, RustyShield, RoyalGuardsShield, HerosShield, BokoShield, SpikedBokoShield, DragonboneBokoShield, LizalShield, ReinforcedLizalShield, SteelLizalShield, GuardianShield, GuardianShieldPlus, GuardianShieldPlusPlus, LynelShield, MightyLynelShield, SavageLynelShield, Shield

Armor:
	OldShirt, WellWornTrousers, ChampionsTunic, HylianHood, HylianTunic, HylianTrousers, SoldiersHelm, SoldiersArmor, SoldiersGreaves, AmberEarrings, WarmDoublet, RubyCirclet, SnowquillHeaddress, SnowquillTunic, SnowquillTrousers, SapphireCirclet, DesertVoeHeadband, DesertVoeSpaulder, DesertVoeTrousers, GerudoVeil, GerudoTop, GerudoSirwal, TopazEarrings, RubberHelm, RubberArmor, RubberTights, FlamebreakerHelm, FlamebreakerArmor, FlamebreakerBoots, OpalEarrings, ZoraHelm, ZoraArmor, ZoraGreaves, StealthMask, StealthChestGuard, StealthTights, SheiksMask, ThunderHelm, ClimbersBandanna, ClimbingGear, ClimbingBoots, BarbarianHelm, BarbarianArmor, BarbarianLegWraps, FierceDeityMask, FierceDeityArmor, FierceDeityBoots, RadiantMask, RadiantShirt, RadiantTights, DiamondCirclet, AncientHelm, AncientCuirass, AncientGreaves, SandBoots, SnowBoots, BokoblinMask, MoblinMask, LizalfosMask, LynelMask, DarkHood, DarkTunic, DarkTrousers, CapOfTime, TunicOfTime, TrousersOfTime, CapOfTheWind, TunicOfTheWind, TrousersOfTheWind, CapOfTwilight, TunicOfTwilight, TrousersOfTwilight, CapOfTheSky, TunicOfTheSky, TrousersOfTheSky, CapOfTheHero, TunicOfTheHero, TrousersOfTheHero, CapOfTheWild, TunicOfTheWild, TrousersOfTheWild, NintendoSwitchShirt, KorokMask, MajorasMask, TinglesHood, TinglesShirt, TinglesTights, MidnasHelmet, PhantomHelmet, PhantomArmor, PhantomGreaves, IslandLobsterShirt, RaviosHood, ZantsHelmet, RoyalGuardCap, RoyalGuardUniform, RoyalGuardBoots, PhantomGanonSkull, PhantomGanonArmor, PhantomGanonGreaves, VahRutaDivineHelm, VahMedohDivineHelm, VahRudaniaDivineHelm, VahNaborisDivineHelm, SalvagerHeadwear, SalvagerVest, SalvagerTrousers

Materials:
	HeartyDurian, PalmFruit, Apple, Wildberry, Hydromelon, SpicyPepper, Voltfruit, FleetLotusSeeds, MightyBananas, BigHeartyTruffle, HeartyTruffle, EnduraShroom, HylianShroom, StamellaShroom, Chillshroom, Sunshroom, Zapshroom, Rushroom, Razorshroom, Ironshroom, SilentShroom, BigHeartyRadish, HeartyRadish, EnduraCarrot, HyruleHerb, SwiftCarrot, FortifiedPumpkin, CoolSafflina, WarmSafflina, ElectricSafflina, SwiftViolet, MightyThistle, Armoranth, BlueNightshade, SilentPrincess, RawGourmetMeat, RawWholeBird, RawPrimeMeat, RawBirdThigh, RawMeat, RawBirdDrumstick, CourserBeeHoney, HylianRice, BirdEgg, TabanthaWheat, FreshMilk, Acorn, ChickalooTreeNut, CaneSugar, GoatButter, GoronSpice, RockSalt, MonsterExtract, StarFragment, DinraalsScale, DinraalsClaw, ShardOfDinraalsFang, ShardOfDinraalsHorn, NaydrasScale, NaydrasClaw, ShardOfNaydrasFang, ShardOfNaydrasHorn, FaroshsScale, FaroshsClaw, ShardOfFaroshsFang, ShardOfFaroshsHorn, HeartySalmon, HeartyBlueshellSnail, HeartyBass, HyruleBass, StaminokaBass, ChillfinTrout, SizzlefinTrout, VoltfinTrout, StealthfinTrout, MightyCarp, ArmoredCarp, SankeCarp, MightyPorgy, ArmoredPorgy, SneakyRiverSnail, RazorclawCrab, IronshellCrab, BrightEyedCrab, Fairy, WinterwingButterfly, SummerwingButterfly, ThunderwingButterfly, SmotherwingButterfly, ColdDarner, WarmDarner, ElectricDarner, RestlessCricket, BladedRhinoBeetle, RuggedRhinoBeetle, EnergeticRhinoBeetle, SunsetFirefly, HotFootedFrog, TirelessFrog, HightailLizard, HeartyLizard, FireproofLizard, Flint, Amber, Opal, LuminousStone, Topaz, Ruby, Sapphire, Diamond, BokoblinHorn, BokoblinFang, BokoblinGuts, MoblinHorn, MoblinFang, MoblinGuts, LizalfosHorn, LizalfosTalon, LizalfosTail, IcyLizalfosTail, RedLizalfosTail, YellowLizalfosTail, LynelHorn, LynelHoof, LynelGuts, ChuchuJelly, WhiteChuchuJelly, RedChuchuJelly, YellowChuchuJelly, KeeseWing, IceKeeseWing, FireKeeseWing, ElectricKeeseWing, KeeseEyeball, OctorokTentacle, OctorokEyeball, OctoBalloon, MoldugaFin, MoldugaGuts, HinoxToenail, HinoxTooth, HinoxGuts, AncientScrew, AncientSpring, AncientGear, AncientShaft, AncientCore, GiantAncientCore, Wood

Food:
	SimmeredFruit, CopiousSimmeredFruit, MushroomSkewer, CopiousMushroomSkewers, FriedWildGreens, CopiousFriedWildGreens, FishSkewer, SeafoodSkewer, CopiousSeafoodSkewers, MeatSkewer, CopiousMeatSkewers, FruitAndMushroomMix, FishAndMushroomSkewer, MeatAndMushroomSkewer, SteamedFruit, SteamedMushrooms, SteamedFish, SteamedMeat, SaltGrilledMushrooms, SaltGrilledGreens, SaltGrilledFish, SaltGrilledCrab, SaltGrilledMeat, SaltGrilledPrimeMeat, SaltGrilledGourmetMeat, CrabStirFry, PepperSeafood, PepperSteak, MeatAndSeafoodFry, PrimeMeatAndSeafoodFry, GourmetMeatAndSeafoodFry, SpicedMeatSkewer, PrimeSpicedMeatSkewer, GourmetSpicedMeatSkewer, FragrantMushroomSaute, HerbSaute, MeatStuffedPumpkin, SauteedNuts, SauteedPeppers, Omelet, GlazedMushrooms, GlazedVeggies, GlazedSeafood, GlazedMeat, SeafoodMeuniere, PorgyMeuniere, SalmonMeuniere, SeafoodFriedRice, CrabOmeletWithRice, SeafoodPaella, PoultryPilaf, PrimePoultryPilaf, GourmetPoultryPilaf, CurryPilaf, FriedEggAndRice, MushroomRisotto, VegetableRisotto, SalmonRisotto, CrabRisotto, CreamOfVegetableSoup, CreamOfMushroomSoup, VeggieCreamSoup, CreamyHeartSoup, CreamySeafoodSoup, CreamyMeatSoup, MonsterSoup, CarrotStew, PumpkinStew, ClamChowder, MeatStew, PrimeMeatStew, GourmetMeatStew, MonsterStew, CurryRice, VegetableCurry, SeafoodCurry, PoultryCurry, PrimePoultryCurry, GourmetPoultryCurry, MeatCurry, PrimeMeatCurry, GourmetMeatCurry, MonsterCurry, MushroomOmelet, VegetableOmelet, MushroomRiceBalls, VeggieRiceBalls, SeafoodRiceBalls, MeatyRiceBalls, MonsterRiceBalls, MeatAndRiceBowl, PrimeMeatAndRiceBowl, GourmetMeatAndRiceBowl, WheatBread, Nutcake, Fruitcake, CarrotCake, PumpkinPie, MonsterCake, PlainCrepe, WildberryCrepe, HoneyCrepe, FruitPie, ApplePie, FishPie, MeatPie, EggTart, HoneyCandy, HoneyedFruits, HoneyedApple, HotButteredApple, FriedBananas, EggPudding, WarmMilk, Elixir, HeartyElixir, EnergizingElixir, EnduringElixir, HastyElixir, FireproofElixir, SpicyElixir, ChillyElixir, ElectroElixir, MightyElixir, ToughElixir, SneakyElixir, FairyTonic, DubiousFood, RockHardFood, BakedApple, BakedPalmFruit, RoastedWildberry, RoastedAcorn, RoastedTreeNut, RoastedHeartyDurian, RoastedHydromelon, CharredPepper, RoastedVoltfruit, RoastedLotusSeeds, RoastedMightyBananas, ToastyHylianShroom, ToastyStamellaShroom, ToastyEnduraShroom, ToastedHeartyTruffle, ToastedBigHeartyTruffle, ToastyChillshroom, ToastySunshroom, ToastyZapshroom, ToastyRushroom, ToastyRazorshroom, ToastyIronshroom, ToastySilentShroom, RoastedRadish, RoastedBigRadish, RoastedSwiftCarrot, RoastedEnduraCarrot, BakedFortifiedPumpkin, RoastedMightyThistle, RoastedArmoranth, CampfireEgg, HardBoiledEgg, SearedSteak, SearedPrimeSteak, SearedGourmetSteak, RoastedBirdDrumstick, RoastedBirdThigh, RoastedWholeBird, RoastedBass, RoastedHeartyBass, RoastedHeartySalmon, RoastedTrout, RoastedCarp, RoastedPorgy, SneakyRiverEscargot, BlueshellEscargot, BlackenedCrab, IcyMeat, IcyPrimeMeat, IcyGourmetMeat, FrozenBirdDrumstick, FrozenBirdThigh, FrozenWholeBird, FrozenBass, FrozenHeartyBass, FrozenHeartySalmon, FrozenTrout, FrozenCarp, FrozenPorgy, FrozenCrab, FrozenRiverSnail, IcyHeartyBlueshellSnail

KeyItems:
	SheikahSlate, MiphasGrace, RevalisGale, DaruksProtection, UrbosasFury, MiphasGracePlus, RevalisGalePlus, DaruksProtectionPlus, UrbosasFuryPlus, Paraglider, RutasEmblem, MedohsEmblem, RudaniasEmblem, NaborissEmblem, SpiritOrb, KorokSeed, HestusMaracas, ThunderHelmKey, ClassifiedEnvelope, HestusGift, PictureOfTheChampions, MedalOfHonorTalus, MedalOfHonorHinox, MedalOfHonorMolduga, TravelersBridle, KnightsBridle, RoyalBridle, ExtravagantBridle, MonsterBridle, AncientBridle, TravelersSaddle, KnightsSaddle, RoyalSaddle, ExtravagantSaddle, MonsterSaddle, AncientSaddle, TravelMedallion
```
