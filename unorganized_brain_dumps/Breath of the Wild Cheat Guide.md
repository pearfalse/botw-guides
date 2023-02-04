# Item Transfer + Hold Prompt Entanglement

Star Icon Invalid Slot (***SIIS***) allows you to do unusual things to items via Hold Prompt Entanglement (***HPE***).

This can be used to:

- Duplicate items.
- Delete one or more items within a stack, and fully remove item stacks once empty.
- Transfer durability for Weapons, Shields, and Bows (to their respective types only).
- Hold items that don't usually allow it (such as cooked foods: required to make Corruption meals).

# Corruption Meals

These are meals designed to be used to change attributes of Weapons, Shields, and Bows. They *usually* require the use of HPE, as well as cooking during a Blood Moon (or around 11:50pm on any normal night at a cooking pot inside Hyrule Castle) to get a special "full-heart recovery" **Critical Success for Recovery Hearts** cooking bonus.

## Ultimate Recipe 1

- Can be used on Weapons, Bows, *and* Shields:

    | Tool Affected | Effect 1 | Effect 2 | Effect 3 |
    | --- | --- | --- | --- |
    | **Weapon** | Attack Up: `+120` | Critical Attack | "Long" Throw |
    | **Bow** | Attack Up: `+120` | `10x` Clustered Multishot | Zoom |
    | **Shield** | Attack Up: `+120` | Guard Up: `+120`<br>(*displayed: Guard `+240`*) | Surf Up: `0.12` |

    | Quantity | Ingredient |
    | --- | --- |
    | `3x` | Roasted Endura Carrot |
    | `1x` | Frozen Hearty Salmon |
    | `1x` | Endura Carrot |

## Ultimate Recipe 2

- Can be used on Weapons, Bows, *and* Shields:

    | Tool Affected | Effect 1 | Effect 2 | Effect 3 |
    | --- | --- | --- | --- |
    | **Weapon** | Attack Up: `+120` | Critical Attack | "Normal" Throw |
    | **Bow** | Attack Up: `+120` | `10x` Spread Multishot |  |
    | **Shield** | Attack Up: `+120` | Guard Up: `+120`<br>(*displayed: Guard `+240`*) | Surf Up: `0.12` |

    | Quantity | Ingredient |
    | --- | --- |
    | `3x` | Roasted Endura Carrot |
    | `1x` | Icy Prime Meat |
    | `1x` | Hearty Blueshell Snail |
    | **NOTE:** | Must have `Critical Success for Recovery Hearts` (full recovery) |

## Material Locations

1. **Endura Carrot**: behind Great Fairy Fountains; on Satori Mountain.
1. **Hearty Salmon**: `Tama Pond` (west of `Hebra Tower`) and `Hubra Plunge` (north of `Tama Pond`, below waterfall), pond on 2nd bridge-connected island east of `Rito Village`.
1. **Hearty Blueshell Snail**: `Lanayru Sea` coast (far east) and `Necluda Sea` coasts (far south-east: west of `Eventide Island`).

You can set this up in either Normal Mode or Master Mode; the steps below are the same.

## Preparation

You need enough progression in your file to have unlocked at least 1 Recovered Memory.

- This requires the Camera Rune on your Sheikah Slate

- A progressed file with:
    - the Camera Rune available
    - at least one Key Item (KI)
    - at least 1 Memory unlocked
- A Manual Save *inside* the **Myahm Agana** shrine (Hateno Village).

## Note

While SIIS does not transfer between Normal Mode and Master Mode, the single Invalid Slot that you break for these steps *do transfer*, so be aware that at least one item (usually a Key Item) can be transferred back and forth.

# Activate SIIS (Master Mode)

1a. Load into Manual Save inside the Myahm Agana shrine
1b. Exit to the main menu and on the same mode you have the Manual Save on
1. Start a new game.
2. Get an autosave in the new game (don't pick up the Shiekah Slate!).
3. Load the file in Myahm Agana. Make sure you have at least two hearts.
3a. Walk up to the apparatus pedestal and make sure it says "Examine".
3b. Have the camera rune and a shield equipped.
3c. Press L and Rstick at the same time. The camera rune should be activated and you should still see the Examine prompt.
3d. Press A.
3e. Delete the photo and press + to enter the inventory.
3f. Hold any item.
3g. Quickly press + twice.
3h. Go to the adventure log and view a memory (nothing should happen). You now have apparatus storage activated.
4. Jump into the void, wait for a second, and reload the file you made in the new game(do NOT go to the title screen). This is called Void Out Storage (VOS).
5. When you load in, you will void out twice and respawn on a cliff. Climb down the cliff and make sure you stay in the very center so as to not get the Shiekah Slate cutscene. If anything goes wrong, restart from step 1.
6. At the bottom of the cliff, wait 45 seconds and then get an autosave. Make sure to avoid the cliff while trying.
7. Once you get an autosave, reload the file in Myahm Agana.
8. Exit the shrine and get 1 offset at the store using any method of IST.
9. Load the autosave you got down the cliff in the new game.
10. Pick up one material. If you are able to access 3 inventory tabs (some may be invisible), then consider yourself lucky and go to step 12. If not, then continue from step 11. 
11a. Pick up the second material of a different type.
11b. Drop both materials.
11c. Pick up one of the materials.
11d. You should now be able to access 3 inventory tabs.
12. In the inventory, move to the middle inventory tab (it should be invisible).
13. Press R to move to the system tab.
14. In the system tab, you should be able to use d-pad left and d-pad right to make the cursor disappear and reappear. 
15. Reload the file in Myahm Agana.
16. You should now have SIIS. Congrats! To check, go to the system tab and then back to the inventory. You should see a cursor appear over the star icon for a split second. If you don't, then reboot the game and restart from step 1.




#!Steps for corrupting 999 Korok Seeds.
# This is just whatever you may already have in your Manual Save file:
Initialize 1 Weapon 1 Bow 1 NormalArrow 1 Shield 1 Apple 2 LizalfosTalon 1 LizalfosHorn 1 Fairy 3 KorokSeed 1 SheikahSlate 1 Paraglider
Save
# If you DON'T have any broken slots/IST offsets, you can skip this step.
Close game
# Start a new game and get ONLY the Sheikah Slate and the Woodcutter's Axe. Leave it equipped.
Initialize 1 SheikahSlate
Get 1 WoodcuttersAxe[equip=true]
Save as autosave1
# Wait 45 seconds, else autosave2 overwrites autosave1.
Get 1 KorokSeed
Save as autosave2
# NOTE: Only break slots AFTER the first 2 autosaves are made, so they contain the correct # of KIs.
Reload
Break 2 slots
# Reload the first autosave, and unequip the axe, multiple times:
Reload autosave1
# GameData: [1]Axe(equipped), [2]Slate
# Visible(Count=1): [1]Slate, [2]Paraglider, [3]Axe(equipped)
Unequip WoodcuttersAxe
# GameData: [1]Slate, [2]Paraglider, [3]Axe
# Visible(Count=1): [1]Slate, [2]Paraglider, [3]Axe
Reload autosave1
# GameData: [1]Axe(equipped), [2]Slate
# Visible(Count=2): [1]Axe, [2]Axe(equipped), [3]Paraglider, [4]Slate
Unequip WoodcuttersAxe
# GameData: [1]Axe, [2]Axe, [3]Paraglider, [4]Slate
# Visible(Count=2): [1]Axe, [2]Axe, [3]Paraglider, [4]Slate
#Reload autosave1
#Unequip WoodcuttersAxe
#Reload autosave1
# You should now have 3 axes in your inventory, 2 of which which should be "behind" the first 2 axes:
Unequip WoodcuttersAxe
# DO NOT sync your gamedata after this next reload:
Reload autosave2
# Make a new save WITHOUT opening the inventory, using the quickmenu, picking up items, etc.
Save as autosave3
# It's now safe to open your inventory.
# You should have 3 axes (3rd should be equipped), and 2nd Key Item should be a Korok Seed.
# Repeat this step until you have no more Korok Seeds in your inventory:
Reload autosave1
# Once you have no more Korok Seeds:
Reload autosave3
# Check that you have 999 Korok Seeds, and load your Manual Save.
Reload
# Open and close the inventory
Sync GameData
# Check if everything looks fine, and if you are happy, save the game.
Save
# Close and reopen the game.



---

Video: Offsets = KI + 60 (meals): video shows 23 KIs, so 83 offset slots
With all weapons, bows (NO arrows!), and shields that you want to corrupt in inventory.
Drop all but 1-2 of each material: video shows 3 full tabs (20*3=60) + 1
    - Keep 30 wood
[Set system clock in future]
Trigger an autosave
[Reset system clock]

Ideal save will have:
    - undiscovered armor tab
    - undamaged Hylian shield
    - all materials in inventory, but only 1-2 each (except wood)
    - undamaged weapons

Most efficient to corrupt weapons, then bows, then shields.
Must temporarily store the BoL on the wall mount.
    1. Fill all remaining bow inventory with regular bows.
    2. Attempt to place BoL on mount to move it to the END of the bow inventory (and clone it onto the mount).
    3. Run across bridge and back (bow still on mount).
    4. Trigger Autosave_1
    5. Sort BoL back to front of the bow inventory.
    6. Drop shields and materials, and eat [1] meal so offset includes the LAST regular bow.
    7. Reload previous Autosave_1
        - Transfers regular bow to font of inventory
        - Shifts the BoL off the list
        - Sync inventory (open+close menu)
    8. Trigger Autosave_2
        - BoL on mount, and no longer in inventory

# Corrupt Weapon Setup
1. Trigger Autosave_3
2. Eat [1] meal
3. Cook desired recipe
4. Make sure food tab:
    - is completely filled
    - has no stackable food
    - has Target Food in last (60th) slot
5. Drop all materials, and everything RIGHT of the tab you're targeting EXCEPT food

# Corrupt Target Weapon
1. Drop & Pick up target weapon (so it's last in list)
2. Trigger + reload autosave
3. Repeat 1-3 for all weapons in Weapon tab
4. After corrupting all weapons besides Master Sword:
    - Use IST shift to move to end of inventory:
    - Eat enough meals to cover all weapons RIGHT of the Master Sword
    - Reload a previous autosave
        - Other weapons should be transferred in, left of Master Sword
    - Resort FOOD tab so target recipe is at the end again
5. Trigger + reload autosave
    - Master Sword should now be corrupted





(k refers to your number of key items) 
- have 60 meals ending with a stackable, then the wmc meal
- save
- generate k+1 offset
- load
(account for duped key items to maintain k+1 offset after each load if needed)
- eat all meals except stackable
- get rid of all armour and materials
- have at least one shield of durability 5+ and at least one empty shield slot
- drop, pick up and equip this shield
- save
- unequip shield
- eat stackable
- load (no need to account for key items here) 
- save without syncing gamedata
- eat stackable
- load
- have target weapon immediately to the left of the stackable
- save
(if you have arrows and do not wish to corrupt a shield, generate 1 extra offset for each stack, must have 500+ of each)
- load

boom
corruption

for anyone curious, the theory is as follows:
- transfer wmc cookdata to stackable item
- corrupt count of stackable item
- force stackable to fail to load in via item limit as opposed to inventory size
thus corrupting with minimal offset

piercing through arrows works by transferring in 500+ of each stack you have
this makes the arrows in your save file fail to load in
causing your most recently added item to still be your target weapon 





you can use a material prompt, press X, then spam A
that will get rid of them all at once
then you can eat the remaining 0 stack


@Kai, Chef of the Wild 's recipe for left slot hold prompt:
Key: Dx =dpad Rx = Right stick
L = left, R = Right

Go to edge of shield tab, ><>< Y < R(4x)
===


The important inputs for undiscovered tab invalid slots:
^ = dpad-up
> = dpad-right
< = dpad-left
v = dpad-down
R = Right stick right
L = Right stick left

><>         : Cursor on rightmost slot of tab to the left of undiscovered tab

><>< Y <    : Cursor on rightmost slot 2 tabs to the left (caution sorts inventory)

From the tab 2 to the left of the undiscovered tab: RRRR : Bottom right of the tab 2 to the right of the undiscovered tab (I think)

From the tab 1 to the left of a invalid slot on the row the invalid slot is on: R>\L>: Moves the cursor to the slot 1 to the right of the slot the cursor was originally on from the left tab onto the right tab

From the tab 1 to the left of an invalid slot, in the same relative column but below: R^LR<> (if on 5th column) R^LR> (If on any other column): Moves the cursor to the slot 1 above the slot cursor was originally on from the left tab onto the right tab

From the tab 1 to the left of an invalid slot, in the same relative column but above: RvLR<> (if on 5th column) RvLR> (If on any other column): Moves the cursor to the slot 1 below the slot cursor was originally on from the left tab onto the right tab 




# What is Inventory Slot Transfer (IST)?

IST Writeup by `zxrobin` (translated by `LetMeThinkOfAUsername`):
- https://pastebin.com/raw/FBhc9GqX
- https://www.bilibili.com/read/cv17141856/ (original post by `zxrobin`)

New Item Dupe & Master Mode Bow of Light - Inventory Slot Transfer (IST) - BotW by `El Duende 05`:
- https://youtu.be/Sc0xA1W7-AI

IST - BotW's Most Powerful Glitch Of 2022 Explained by `RinHara5aki` in GameSpot:
- https://youtu.be/mbthdP2SkNA

Detailed explanation of IST by `kinak`:
- https://pastebin.com/raw/2F8N3xFt

# Tutorials and Other Resources

`Piston`’s simulator:
- https://dupl.itntpiston.app/#simulation

Chained Material Corruption Tutorial by `Jhent`:
- https://youtu.be/B6ztxM3M0Mc

Bow of Light with IST by `El Duende 05`:
- https://youtu.be/nDdsnoXyizg

Invalid Arrow Slots Explanation by `kinak`:
- https://pastebin.com/raw/D0TSKuaw

Protected Autosave by `El Duende 05`:
- https://discord.com/channels/872350971383140422/872350971383140424/1001379595716677642

Entering Blue Hyrule + Save Prompt Storage Guide by `ShinyDuckFish`:
- https://pastebin.com/raw/yUNW1wgX

Save Prompt Storage Instructions by `LetMeThinkOfAUsername`:
- https://discord.com/channels/872350971383140422/997616079977316352/1005561329882497046

# Weapon Modifier Corruption (WMC)

Recipes & Modifiers:
- https://docs.google.com/spreadsheets/d/1efenvai4JJM9iPGziHvvef6jSWvNeUGrx-WV9eWlR3g/edit#gid=619246539

Cooking Price Simulator:
- https://docs.google.com/spreadsheets/d/1tZgfbEg6fyhjxWQPCOVch0U4hGVBQRR8R9bdiwBUo8c/edit?usp=sharing

Explanation and Instructions for WMC:
- https://docs.google.com/document/d/1dtBUM-_3nHNkOiLoTwsvjMuzi46nzzHjpgIryrTE81s/edit?usp=sharing

Hold Prompt Storage by `Jhent`:
- https://discord.com/channels/872350971383140422/992081877861146676/997252270200717382

Hold Prompt Entanglement by `ys`:
- https://discord.com/channels/872350971383140422/997616079977316352/998628291554582568

Holding Two Different Food Items with HPE by `NaN Gogh` (`Schattendoppelgänger`):
- https://discord.com/channels/872350971383140422/997616079977316352/1000057274942894191

k9c Method by `kinak`:
- https://pastebin.com/raw/Hpz01xqm

Invalid Star Guide (Star Icon Invalid Slot, or "SIIS") by `FlushedJosh`:
- https://pastebin.com/raw/3F1iH4RS

# Fixing Your File with IST

Transferring equipment durability to the right by `crystal_l`:
- https://discord.com/channels/872350971383140422/999115384596742194/999314496965333092

Fixing Duplicate Armor by `El Duende 05`:
- https://discord.com/channels/872350971383140422/997164464543645766/997188246536728606

Fixing Too Many Korok Seeds by `El Duende 05`:
- https://discord.com/channels/872350971383140422/997164464543645766/997164920527401050

Acquiring All Inventory Slots with No Korok Seeds Left Over by `jordanbtucker`:
- https://discord.com/channels/872350971383140422/992081877861146676/1003396515580100650

Swapping Two Food Items by `KendleMintJed`:
- https://youtu.be/D8c6Cg3yZOk

Setting Up Star Icon Invalid Slots by `kinak`:
- https://discord.com/channels/872350971383140422/992081877861146676/1005758550410280971

Corrupting Weapons and Arrows with a Shield by `KendleMintJed`:
- https://pastebin.com/raw/Q4wVCVDa

IST - How to Transfer Hylia Shield Durability to Sword and Bow + Arrows in BotW:
- https://youtu.be/6ZZaNqwNJwI

Duplicate Lynels - Gold and white setup by `KendleMintJed`:
- https://discord.com/channels/872350971383140422/999570630502522970/1005749782964350986

K+1 WMC: The basic method:
- https://discord.com/channels/872350971383140422/1000992154140811325/1012501841956831282

`El Duende 05`'s scaling XP checklist / spreadsheet:
- https://docs.google.com/spreadsheets/d/1-GTZQqhZHmYK_Z6RHezFIdHAazNDCMQ6X8ewOOyov-0/edit

`Leoetlino`'s scaling XP spreadsheet:
- https://docs.google.com/spreadsheets/d/e/2PACX-1vRSlyOD7FLAn1TUBn64Pu8Pld-WOfgcVByuywHMWvBTEV0j8potD1wkBs-MJJXf-gvEkpfItUCMqMk6/pubhtml

Master sword shenanigans by `NaN Gogh`:
- https://discord.com/channels/872350971383140422/997616079977316352/1010687335035322530

Arrow Invalid Slot by `乃ℓ๏в` and `FlushedJosh`:
- https://pastebin.com/raw/5Sik8RjB





Meals 1-58 are random meals (Simmered Fruit is good), and if applicable, your recipe items should be in the row (1-5, 21-25, 41-45).
Meal 59 should be the stackable meal (Baked Apples).
Meal 60 should be the WMC meal (target food).

# Transfer Durability of Shield onto Arrow Stack

K = number of key items
N = number of arrow stacks

- Have no dupeable key items (excluding champ abilities) 
- Have at least N empty weapon slots
- Drop, pick up and equip your high durability bow (1 durability = 100 arrows)
- Generate K + N + (No.Champ abilities) * N offset
- Make an autosave
[
    - Enter eventide
    - Pick up 1 weapon
    - Load autosave
    - Make a new autosave without syncing gamedata
] - repeat this N times total picking up 1 additional weapon each time
- Enter eventide
- Load autosave

======

Current:
    Key Items:  8
    Food:       42 [2*20+2] (including 2 WMC meals)
    Materials:  128 [6*20+8]
                -11=117
    Armor:      38 [20+18]
    Shields:    7                   New Game: 4 slots
    Bows:       10 (including BoL)  New Game: 5 slots
    Arrows:     6
    Weapons:    9                   New Game: 8 slots
  Total:        237                 237
    Total - Materials = 244-128=116
    122

Offsets:
    1 (for SIIS)
    4+4+4+4+4 =20   21
    4+4+4+4+4 =20   41
    4+4+4+4+4 =20   61
    4+4+4+4+4 =20   81
    4+4+4+4+4 =20   101
    4+4+4+4+4 =20   121
    1               122

    If I break 128 slots, I'll need to keep (128-111=17) Material slots.
    Because after I transfer these into NM, then come back to MM to get the remainder of the items, I'll still have 128 slots to deal with.

Initialize
    1 MasterSword 1 RoyalBroadsword 1 Flameblade 1 Thunderblade 1 MeteorRod 1 IceRod 1 StoneSmasher 1 AncientBattleAxePlusPlus 1 EdgeOfDuality
    1 BowOfLight 1 AncientBow 1 SavageLynelBow 1 GoldenBow 1 ForestDwellersBow 4 SavageLynelBow 1 LynelBow
    325 NormalArrow 91 FireArrow 144 IceArrow 229 ShockArrow 131 BombArrow 4 AncientArrow
    1 HylianShield 1 MightyLynelShield 1 AncientShield 1 KnightsShield 1 SteelLizalShield
    1 RoyalGuardsBow 1 LynelShield
    2 OldShirt 1 ChampionsTunic 1 HylianTrousers 1 AmberEarrings 1 RubyCirclet 1 SnowquillHeaddress 1 SnowquillTunic 1 SnowquillTrousers 1 SapphireCirclet 1 DesertVoeHeadband 1 DesertVoeSpaulder 1 DesertVoeTrousers 1 GerudoVeil 1 GerudoTop 1 GerudoSirwal 1 TopazEarrings 1 FlamebreakerHelm 1 FlamebreakerArmor 1 FlamebreakerBoots 1 OpalEarrings 1 ZoraHelm 1 ZoraArmor 1 ZoraGreaves 1 RadiantMask 1 RadiantShirt 1 RadiantTights 1 DiamondCirclet 1 BokoblinMask 1 NintendoSwitchShirt 1 KorokMask 1 MajorasMask 1 PhantomHelmet 1 PhantomArmor 1 ClimbingBoots 1 AncientHelm 1 AncientCuirass 1 AncientGreaves
    14 HinoxTooth 16 HinoxGuts 68 AncientScrew 21 AncientSpring 3 AncientGear 54 AncientShaft 16 AncientCore 13 GiantAncientCore 23 Wood 15 HeartyBass 15 BigHeartyTruffle
    37 SimmeredFruit 1 FriedWildGreens 1 SeafoodSkewer 1 BakedApple 1 RoastedEnduraCarrot 1 IcyPrimeMeat 1 SheikahSlate 1 MiphasGracePlus 1 RevalisGalePlus 1 DaruksProtectionPlus 1 UrbosasFuryPlus 1 Paraglider 1 AncientSaddle 1 TravelMedallion
Save
Break 122 slots
Drop
    1 EdgeOfDuality
    4 SavageLynelBow 1 LynelBow
    1 KnightsShield 1 SteelLizalShield 1 RoyalGuardsShield 1 LynelShield





# On Plateau
Initialize 6 Weapon 1 Bow 1 Shield 1 SheikahSlate
Save as PlatAuto
Get 1 SilentShroom
Initialize 1 WoodcuttersAxe[equip] 1 Torch 3 ForestDwellersBow 1 NormalArrow 1 ShockArrow 1 AncientArrow[equip] 1 PotLid[equip] 1 HeartyDurian 1 MightyBananas 1 Rushroom 1 SilentShroom 1 SilentPrincess 1 Honey 1 BirdEgg 1 Acorn 1 FaroshsScale 1 FaroshsClaw 1 ShardOfFaroshsHorn 1 HeartyBass 1 HyruleBass 1 Fairy 1 EnergeticRhinoBeetle 1 Opal 1 LizalfosHorn 1 LizalfosTalon 1 LizalfosTail 1 AncientScrew 1 AncientSpring 1 AncientShaft 1 AncientCore 1 Wood 1 SheikahSlate 8 SpiritOrb 1 Paraglider
Equip ForestDwellersBow in slot 3
Cook 10 MeatPie
Break 12 slots
Dnp 1 Opal 1 LizalfosHorn 1 LizalfosTalon 1 LizalfosTail 1 AncientSpring 1 AncientShaft 1 AncientCore 1 Wood 1 EnergeticRhinoBeetle 1 Fairy 1 HyruleBass 1 HeartyBass 1 Acorn 1 Honey 1 SilentPrincess 1 Rushroom 1 EnduraShroom 4 FleetLotusSeeds 3 AncientScrew 1 EnduraCarrot 5 MightyBananas 1 HeartyDurian 1 SilentShroom 1 BirdEgg 1 FaroshsScale 1 FaroshsClaw 1 ShardOfFaroshsHorn
Save
Reload PlatAuto
# Get Star Invalid Slots
Get 1 Apple
Drop 1 Apple
Get 1 Weapon
Unequip Weapon
Equip Bow
Eat 9 MeatPie
Reload
Save
Reload PlatAuto
# Get Star Invalid Slots
Eat 8 MeatPie
Reload
Shoot 1 Arrow
Save
Reload PlatAuto
Eat 7 MeatPie
Reload
Shoot 1 Arrow
Save
Reload
#simulate sorting
Drop 999 Wood 999 AncientCore 999 AncientShaft 999 AncientSpring 999 LizalfosTail 999 LizalfosTalon 999 LizalfosHorn 1 Opal 999 EnergeticRhinoBeetle 1 Fairy 1 HyruleBass 1 HeartyBass 1 Acorn 1 CourserBeeHoney 1 SilentPrincess 1 Rushroom 1 EnduraShroom 4 FleetLotusSeeds 3 AncientScrew 1 EnduraCarrot 5 MightyBananas 1 HeartyDurian 1 SilentShroom 1 BirdEgg 4 FaroshsScale 4 FaroshsClaw 4 ShardOfFaroshsHorn
Get 1 HeartyDurian 1 MightyBananas 1 Rushroom 1 SilentShroom 1 SilentPrincess 1 CourserBeeHoney 1 BirdEgg 1 Acorn 1 FaroshsScale 1 FaroshsClaw 1 ShardOfFaroshsHorn 1 HeartyBass 1 HyruleBass 1 Fairy 999 EnergeticRhinoBeetle 1 Opal 999 LizalfosHorn 999 LizalfosTalon 999 LizalfosTail 1 AncientScrew 999 AncientSpring 999 AncientShaft 999 AncientCore 999 Wood
#manual sort a bit
Dnp 1 HeartyDurian 1 MightyBananas 1 SilentShroom 1 BirdEgg 1 FaroshsScale 1 FaroshsClaw
Remove 32 SpiritOrb
Get BombArrow
Save
Reload PlatAuto
Eat 9 MeatPie
Get 1 Weapon
Unequip weapon
Reload
Shoot 1 Arrow
Save
Reload PlatAuto
Eat 8 MeatPie
Reload
Shoot 1 Arrow
Save
Reload PlatAuto
Eat 6 MeatPie
Equip Shield
Reload
Shoot 1 Arrow
Save
Reload
Eat SheikahSlate
Eat Paraglider
Remove 40 SpiritOrb
Save as HatenoAuto
# End Of Direct Inventory Corruption
Save
Reload
Sync Gamedata
Save
Reload
Cook 1 MeatPie
Get 1 BakedApple
Get 1 Omelet
Save
Reload
Eat 5 MeatPie
Cook 4 MeatPie
Reload PlatAuto
Drop 1 Shield 6 MeatPie
Equip Weapon in slot 4
Save
Unequip weapon
Reload
Save
Eat 2 BakedApple
Reload
Eat 7 MeatPie
Reload HatenoAuto
Sync Gamedata
Save

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





To swap the order of the last 2 Meals (works in Normal Mode and Master Mode):
    These steps come from KendleMintJed's https://www.youtube.com/watch?v=D8c6Cg3yZOk guide.

    Assumes Food consists of: `58x Simmered Fruit`, `1x Target Meal`, `1x stackable` (like a Baked Apple).

1. Break K+1 slots.
2. Eat **1x Simmered Fruit** so you have a free slot.
    Food now has: `57x Simmered Fruit, 1x Target Meal, 1x stackable`.
3. Generate Autosave 1.
4. Reload Autosave 1.
    Food now has: `1x stackable, 57x Simmered Fruit, 1x Target Meal, 1x stackable` (again).
5. Eat the **second stackable** (3rd Food tab, Row 4, Column 5).
    With a K+1 offset, you would have just eaten the stackable where the "+1" extended onto.
6. Sort the Meals ***ONCE***.
    Food now has: `57x Simmered Fruit, 1x stackable, 1x Target Meal, 1x open slot`.
7. Generate Autosave 2.
8. Eat the **1x stackable** AND the **1x Target Meal**.
    Food now has: `57x Simmered Fruit, 3x open slots`.
9. Reload Autosave 2.
    Food now has: `58x Simmered Fruit, 1x stackable, 1x Target Meal`.



(k refers to your number of key items) 
- have 60 meals ending with a stackable, then the wmc meal
- save
- generate k+1 offset
- load
(account for duped key items to maintain k+1 offset after each load if needed)
- eat all meals except stackable
- get rid of all armour and materials
- have at least one shield of durability 5+ and at least one empty shield slot
- drop, pick up and equip this shield
- save
- unequip shield
- eat stackable
- load (no need to account for key items here) 
- save without syncing gamedata
- eat stackable
- load
- have target weapon immediately to the left of the stackable
- save
(if you have arrows and do not wish to corrupt a shield, generate 1 extra offset for each stack, must have 500+ of each)
- load



Durability Transfer:
1. If needed, drop and pick up Weapon A so it is right-most in the Weapons slot. Equip Weapon A (if not already).
2. Break K+1 slots.
    Broken slots should extend into the last weapon slot.
3. Transfer in Weapon B.
    Does this mean load in that weapon? Pick up some weapon from the ground/chest?
4. Generate Autosave 1.
5. Reload Autosave 1.
    Durability will shift from the equipped weapon (Weapon A) to the RIGHT (Weapon B).
    So if a weapon is unequipped, its durability will not be transferred onto another weapon.

Video:
    4 Shield slots; 2 occupied:
    Shield A (Pot Lid) has heavy damage.
    Shield B (Steel Lizal Shield) has "undamaged" sparkle, and was initially equipped.

1. Shield A was equipped.
2. R-Bumper pressed, waited a second, then L-Bumper pressed.
3. Shield B was (quickly?) selected and Dropped.
4. Autosave was reloaded.
    As seen from Shield Quick Menu, 4 Shield slots; 3 occupied:
    Shield A (Pot Lid) IS equipped and has no damage.
    Shield B (Pot Lid) IS NOT equipped and has heavy damage.
    Shield C (Steel Lizal Shield) IS equipped and has "undamaged" sparkle.
5. Shields tab opened; Shield A and Shield C are both equipped.
6. Shield A removed and then (quickly?) equipped.
    Shield A IS equipped; Shield B and Shield C now ARE NOT equipped.

Per other instructions (Weapons, Bows and Shields all use the same instructions):
    NOTE: Have at least one free Weapon slot.
1. Equip high-durability/undamaged Weapon A.
2. Move low-durability/damaged Weapon B into the last Weapon slot (you can drop and pick it up).
3. Generate K+1 offsets.
    Broken slots should extend onto the last Weapon slot (nothing between Weapon B and Key Items).
4. Generate Autosave 1.
5. Unequip Weapon A (the high-durability/undamaged one).
6. Reload Autosave 1.
    DO NOT SYNC GAMEDATA.
7. Generate Autosave 2.
8. Unequip 

1. Equip a high-durability/undamaged Weapon A.
2. Have a low-durability/damaged Weapon B to the right
1. Have the item (Shield B, ) that you want durability transferred ONTO (such as one with damage) next to 
2. Generate Autosave 1.
3. Equip the weapon/shield/bow you want durability to be transferred ONTO (such as a damaged one).
4. Generate K+1 offsets.
    Broken slots should extend onto the last weapon slot (nothing between the weapon/shield/bow and Key Items).
5. 