# Corrupting Arrows to 999+

`K` = number of key items<br>
`C` = number of Champ Abilities<br>
`N` = number of arrow stacks

1. Have no stackable Key Items.
1. Have at least `N` empty weapon slots.
1. D&P (drop, pick up, and equip) your high-durability bow (1 durability = 100 arrows).
1. Generate `K` + `N` + (`C` * `N`) offsets.
1. Make an autosave
    1. Enter Eventide
    1. Pick up `1`\* weapon *(\*see Step 6 below)*
    1. Load autosave (Step 5)
    1. **Without syncing GameData**, make a new autosave
1. Repeat steps `5.1` - `5.4` a total of `N` times, picking up 1 additional weapon each time
1. Enter Eventide
1. Load autosave made from the last `5.4` step above.
