# This Is Not What You Think It Is

The notes below are just my brainstorming for some player to choose one of several "what setup would I need in order to..." options.

That would generate inputs that could be fed into the [IST Simulator App](https://ist.itntpiston.app).

## Ramblings Below
It would definitely need to borrow some of the https://ist.itntpiston.app simulator's logic, but I'm just mentally walking down the checklist here:

1. If the player indicates that they are willing to use PE, some of the steps may be modified ("before reload, eat unsellable armor", "after reload, eat the duped Champ+ slots", "before save, eat N arrow stacks"). If they are unwilling/unable to use PE, steps might include "start a new game, and play through the plateau without picking up..." to avoid the dupable items in the first place.
2. Knowing a player's entire inventory may not be necessary; they can certainly enter "5 shields" to just use generic placeholders.
3. Knowing the state of some game events for one (or two?) save files may be necessary: `medoh_completed` (for Revali's Champ), `medoh_champ_plus` (for Revali's Champ+, which can cause duplication), which would tie back into the first point, since it may have to take duplication into account in various ways.

The UX might follow a flow something like this:
1. Select "Corrupt weapons with WMC".
2. Provide the following information:
    1. [x] Use Prompt Entanglement (PE)
    2. [-] WMC Meal Has Already Been Created
    3. [x] Has the Master Sword
    4. [x] Has the Bow of Light
    5. [x] Freed Vah Ruta
        1. [-] Completed Vah Ruta DLC
    6. [x] Freed Vah Medoh
        1. [x] Completed Vah Medoh DLC
    7. [x] Freed Vah Rudania
        1. [x] Completed Vah Rudania DLC
    8. [x] Freed Vah Naboris
        1. [-] Completed Vah Naboris DLC
    9. [x] Unlocked Link's House
        1. Number of Bow Mounts: [...]
        2. Number of Weapon Mounts: [...]
        3. Number of Shield Mounts: [...]
    10. Total Unsellable Armor: [...]
    11. [x] Has Arrows
        1. Total Normal Arrows (or -1 if no slot): [...]
        2. Total Ice Arrows (or -1 if no slot): [...]
        3. Total Fire Arrows (or -1 if no slot): [...]
        4. Total Bomb Arrows (or -1 if no slot): [...]
        5. Total Shock Arrows (or -1 if no slot): [...]
        6. Total Ancient Arrows (or -1 if no slot): [...]
    12. Total slots currently broken: [...]

Given inputs like that, we can make a few assumptions about the steps/feedback that would need to be provided, either to the player or to be passed into the IST Simulator:
1. Knowing that a player can use PE means that instructions could include eating some duped items during parts of the process.
2. Knowing that 2 of the 4 Divine Beast DLCs had been completed means that 2 Champ+ abilities dupe while 2 don't, and can be part of the required offset calculations.
3. Knowing that the player is holding the Bow of Light, and has unlocked at least 1 Bow Mount, means that the player is able to remove it from their inventory.
    - If the option for PE is unchecked, the steps might require filling up empty bow slots and then using IST to shift the BoL out of the inventory.
    - If the option for PE is checked, the steps may include instructions on dropping the BoL off a ledge, or entangling it with another bow so dropping the BoL dupes the entangled bow.
