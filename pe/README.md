# Prompt Entanglement

Tricking the Inventory menu into thinking its cursor is somewhere that it's not.

In order to optimize memory usage, only three tabs' worth of items are loaded at any given time. By using special sequences of inputs, a cursor may appear to hover over one item currently loaded in memory, while the actions that may be performed on it are based on another item that has been unloaded from memory.

This allows a player to entangle an edible Material or Meal, shift to a different tab (in groups of 3), and use the "Eat, Drop, Cancel" prompt from that Material on another item, even of a different type.

## Star Icon Invalid Slot (`SIIS`)

*Also commonly known simply as Star Invalid Slot (`SIS`).*

- <details>
    <summary>Initial Setup</summary>

    I personally like to have a protected autosave within the Shrine of Resurrection, before Link picks up the Sheikah Slate, to quickly activate `SIIS` without waiting through the initial "Open your eyes..." cutscene.

    1. Set your system clock into the future, and manually save.
        - An example would be to set it to one year plus one day from today.
    1. Change your system clock again, setting it earlier than before, but after today's date.
        - For example, set it to one year (but not "plus one day") from today.
    1. If you have broken any IST slots, close and relaunch the game to clear them: you want Link's inventory to be empty when the autosave is generated.
    1. From the title screen, start a New Game and wait through the initial cutscene until an autosave is generated within the Shrine of Resurrection (I often refer to this as the `SoR` autosave). This autosave usually occurs as soon as you have control to move Link around.
    1. Reset your system clock to today's date.

    You can now reload any progressed save and play normally.
    </details>

- <details>
    <summary>SIIS Setup</summary>

    Activating `SIIS` requires breaking `K+1` slots (number of Key Items, plus one), reloading the `SoR` autosave, and entering a few inputs.

    1. Count your number of Key Items ("`K`").
    1. Generate 1 more than this number of IST offsets in whatever manner you choose.
    1. Before reloading the `SoR` autosave, ensure that you have at least one other item (usually a Material or Meal).
        - The purpose is to have Inventory items from two different slots (KIs + Meals, or KIs + Materials).
    </details>

- <details>
    <summary>SIIS Activation</summary>

    You should have `K+1` IST offsets, then reload the `SoR` autosave.

    1. Press `[+]` to pause and open the menu. You should be on the Save/Load screen.
    1. Press `[L]` (left bumper) to switch to the Inventory tabs; you should see an arrow pointing to the right.
    1. Press `(R)-right` (right stick to the right) to move to the next tab.
    1. Press `[+]` to close the menu.

    Repeat steps 1-4 two to three times until you can press `[+]` and then `[D]-left` while your cursor is over the Save/Load options and make it disappear.
    - The number of repetitions actually required is determined by a few factors, like number of KIs you had to transfer over, or whether your `+1` was a Meal, Material, or something else.
    - You may have to repeat steps 1-4 more than three times in a few rare cases.

    Once your cursor disappears on the Save/Load menu, load any progressed save to have `SIIS` activated in it.
    </details>

## Prompt Entanglement

(Under construction)

1. Unlock [row 3](https://discord.com/channels/872350971383140422/997616079977316352/1007061460632993814):
    1. Row 4, Column 5
    1. `(R)-left`, `[D]-up`, `(R)-right`, `[D]-left`
    1. This should leave you on the current page, column 0
1. `[D]-left`
1. Move cursor to row 4 col 1
1. `[D]-left`, `[D]-right`, 2x `(R)-right`, `[D]-right`
