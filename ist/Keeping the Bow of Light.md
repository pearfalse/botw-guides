# Keeping the Bow of Light

The Bow of Light ("**BoL**") is an unbreakable energy-firing bow that is supposed to only be available during the last battle with Ganon's final form. Using [IST](/ist/README.md), you can transfer it back to one of your previous saves.

## Theory

You will generate enough IST offsets to cover the Bow of Light plus any items (Arrows, unsellable Armor, Key Items, etc.) that you cannot reasonably remove from your inventory during the final Ganon battle.

Once the Bow of Light has been acquired, you will drop/use all other Inventory items, and then reload a previous target save. Due to the broken IST slots, the BoL gets transferred (temporarily) as well.

Finally, after some Inventory clean-up, you will be able to transfer the BoL back to your main save.

## Setup

1. You want an 

## Steps

1. You want to minimize the number of items in your Inventory before you generate an autosave outside the Ganon battle (called `Ganon_Autosave` later).
    - Since the Weapon tab is to the left of the Bows tab, you don't need to include Weapons in the IST calculations below.
    - You can keep some useful items on you when you generate the `Ganon_Autosave`: fairies, bows, shields, meals. However, you won't count them in your IST calculations, as you will get rid of them during the final steps, after you've obtained the BoL.
1. Some items cannot be sold or dropped: arrow stacks, some armor, non-stackable Key Items.
    - If you are able to use Prompt Entanglement ("PE") to remove/eat these items (including empty arrow stacks), the total number of IST offsets needed can be reduced.
1. You will need to count duplicating items 2x for IST offset calculations.
1. You will need to count non-duplicating items 1x for IST offset calculations.

Once 

## IST Slot Calculation

1. The total number of IST slots necessary include:
    1. **K**: Count each non-duplicating Key Item 1x, and each duplicating Key Item 2x.
        - The DLC Champ+ Abilities *can* duplicate if you've unlocked them in this game file; if you've transferred some in from another save (but have not re-defeated the Divine Beasts in this game), they won't dupe.
        - Items that have a stack count will duplicate: Korok Seeds, Spirit Orbs, DLC Divine Beast Emblems (Ruta's Emblem, Medoh's Emblem, Rudania's Emblem, Naboris's Emblem).
    1. **U**: Count each Unsellable Armor 2x (as well as any you wish to keep with you in the final battle): all armor can duplicate.
    1. **A**: Count each arrow stack containing 500+ arrows 1x (as those won't duplicate), and any arrow stack containing 1-499 arrows 2x (as those will duplicate).

...


1. You need to create enough offsets to cover all items, up through the BoL slot, that you can't reasonably remove right after picking up the BoL.
2. Each slot that contains items that *can duplicate* should be counted 2x for IST offsets; while each slot that contains non-duping items can be counted 1x.
3. Arrows, Spirit Orbs, and Korok Seeds can be corrupted to 999 so they do not dupe.

You will generate an autosave before the Ganon fight. You CAN still have weapons, shields, bows, and materials (like fairies) at this point.

Defeat the Blight Ganons, if you need, and defeat Ganon's first form (before you start the second form where you get the BoL).



1. You want to have enough offsets to cover the BoL slot.
2. You usually want to get rid of everything else; if your arrows, spirit orbs, and korok seeds won't duplicate, count them with your IST offsets, otherwise you need to get rid of them
3. For each item that will duplicate, count them 2x with your IST offsets