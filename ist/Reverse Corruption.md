# Reverse Corruption

The process of copying the durability from one item onto another by using an **mCount** at, or below, `0`. In the case where durability transfers to stackable items, such as Arrows or Key Items, 

Using a negative **mCount** to transfer corruption from, for example, a Hylian Shield to a Weapon or Bow.

## Terminology
<details open>
<summary>[toggle]</summary>

- **`[F]`**: Item (like a shield) to transfer durability ***from***.
- **`[T]`**: Item (like a weapon) to transfer durability ***to***.
- **`[SL]`**: **S**ellable/Droppable items *to the **L**eft* of **`[F]`**, like a Torch.
- **`[UL]`**: **U**nsellable/Undroppable items *to the **L**eft* of **`[F]`**, like the Master Sword.
- **`[SR]`**: **S**ellable/Droppable items *to the **R**ight* of **`[F]`**, like a Material.
- **`[UR]`**: **U**nsellable/Undroppable items *to the **R**ight* of **`[F]`**, like armor or Key Items.
- **`[DG]`**: **D**roppable **G**ear which you can drop and pick back up: includes *all* weapons, bows and shields *as well as* **`[F]`**; excludes Master Sword or Bow of Light (unless you know how to drop them via **[Prompt Entanglement](/pe/README.md)**).
- **`[TotalU]`**: **Total U**nsellable items (**`[UL]`**+**`[UR]`**), on either side of **`[F]`**.
- **`[TotalS]`**: **Total S**ellable items (**`[SL]`**+**`[SR]`**), on either side of **`[F]`**.
</details>

## Theory

<details open>
<summary>[toggle]</summary>

The number of IST slots you will need to generate equals:

> **`[UL]`** + **`[UR]`** + **`[SL]`** - `1`

There are 3 important numbers for this:

1. **`[UL]`**: Number of undroppable items *left* of the Hylian Shield ("**`[F]`**").
1. **`[UR]`**: Number of undroppable items *right* of the Hylian Shield ("**`[F]`**").
1. **`[SL]`**: Number of sellable/droppable items *left* of the Hylian Shield ("**`[F]`**").

- For example, let's say that you had:
    - **`[UL]`** == `29` (1x MS, 1x BoL, 27x arrow stacks)
    - **`[SL]`** == `41` (19x axes, 12x bows, 10x shields - excludes the Hylian Shield)
    - **`[UR]`** == `40` (10x armor, 30x KIs)

    Then your `mCount` would equal 29+41+40=`110`.


- For example, if you had 29 **`[UL]`** (1x MS, 1x BoL, 27x arrow stacks), 41 **`[SL]`** (19x axes, 12x bows, 10x shields - not counting the Hylian Shield), and 40 **`[UR]`** (10x armor, 30x KIs), then your `mCount` would equal 29+41+40=`110`.
- You would want to generate *1 fewer* than this, so 110-1=`109` total IST slots.
- This might mean that you need to add or remove some weapons, bows, or shields to get to this target number.

Once you have broken this number of slots, you will discard all other items (sellable Armor, all Materials, all Meals). This SHOULD leave your `mCount=1`.

Then, you DNP ("drop-and-pick up") all of your weapons, bows, and shields in a specific order.
- The **first** DNP'd item will be the one that ***receives*** durability.
- The **last** DNP'd item will be the one that ***donates*** durability (so DNP the Hylian Shield *last*).
- The order of the other items doesn't really matter.
</details>

Finally, after closing and reopening the game, the 

<details>
<summary>IST Simulator Example</summary>
```
# make sure your amount of droppable gear is 1 greater than your amount of unsellable items on the right of the hylian shield. in this example we have 40 unsellable items on the right of the hylian shield, so we drop a shield to reach 41 droppables.
drop ...
# create 1 less offset than the amount of items in your inventory minus any sellable armor or materials. we have 110 items excluding any sellable things, so we break 109 slots.
break 109 slots
# Sell all materials and armor: You should be at **mcount 1**.
sell all materials
# DNP all weapons, bows, shields: the 1st item picked up **RECEIVES** durability; the last item picked up **TRANSFERS** durability
dnp ... 1 Hylian Shield
# Unequip axe and bow to avoid collateral damage
unequip axe
unequip bow
save
close game
# Desynced inventory will corrupt item on reload (even with no IST)
reload
# Save WITHOUT SYNCING GAME DATA.
save
```
</details>