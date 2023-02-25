# Playing Through the Plateau

Some guides may suggest/require that you begin a new game, unlock the 4 initial shrines on the Great Plateau containing the Runes (Remote Bombs, Magnesis, Statis, Cryonis), get the Paraglider, and then proceed until you've reached Hateno Village (or some kind of stable where you can find a vendor that can buy items *from* Link).

Why?

To avoid dupable items that are obtained through extended play, which could throw off careful calculations and prevent expected corruptions.
- Normally, this isn't a problem if you can "eat" items (like armor) with [Prompt Entanglement](/pe/README.md), but some Key Items get automatically restored on reload if they had ever been used.

## Dupable Items

These are any items which take up a *new* slot, rather than being combined/added to an existing slot, due to [IST](/ist/README.md).

In almost all cases, where the item is stackable and the count is 500 or more, the item slot *does not duplicate*, unless specified otherwise.

The following items can be duplicated:

- Weapons (**NOTE**: Duplicate Master Swords will be removed after closing and restarting the game)
- Bows (**NOTE**: Duplicate [Bows of Light](/ist/Keeping%20the%20Bow%20of%20Light.md) will ***not*** be removed after closing and restarting the game)
- Arrows (**NOTE**: Empty arrow stacks showing `0x` *can* duplicate)
- Shields
- Armor
- Materials
- Food/Meals/Elixers
- Stackable Key Items:
    - Emblems (DLC): Ruta, Medoh, Rudania, Naboris
    - Spirit Orbs
    - Korok Seeds
- Champion+ Abilities (DLC)
    - **NOTE**: Unlike normal Champ Abilities, these ***can dupe into new KI slots*** on reload.

A note on the Champion Abilities (non-DLC), Champion+ Abilities (DLC), and the Travel Medallion:
- These are Key Items with a special fail-safe that will restore them on reload if this item had ever been used before within the current save/play-through.
- You may need to account for this when calculating IST offsets.
