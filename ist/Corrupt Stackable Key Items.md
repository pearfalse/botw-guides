# Corrupting Stackable Key Items

Corrupting stackable Key Items to 999 will prevent them from duplicating.

Stackable KIs include: Korok Seeds, Spirit Orbs, Divine Beast DLC Medalians.

The following script can be fed into the IST Simulator's script section to demonstrate corrupting Korok Seeds (corrupting Spirit Orbs use practically identical steps). [This link](https://ist.itntpiston.app/?c=H4sIAAAAAAACA61VX2%2FaMBB%2Fz6c4iYcWjXUC9lL6MHWsa1EnmAjb1EeTXIiHsTOfU2CffmeHQII2qdP25Bbsu9%2B%2FOzqwyCVBIjQsEYTeQ2HNyiIRpkDiGWGbo0XYmxIEn2KpEJyBFWq0wiGQ2SBM4gWQMo6iiZZOCiV%2FIgzgtihUOBNjNfThmzEpH4%2FGmnWM6P%2F%2BLKxYKZmi5X%2FiHOVa5LHiwlHMzaMOzJGcsA5WYhMaJwqFDUBxJ8lJvTp178H3kpy%2FxVxIZBiNlSEMb7nUbelMoNQfwWz66YmRSYcbGgVgSekc2guC2x3CJf4oZVFg2uVWaQ0MKmQdmM4WdyOYZEGWraQ8IDPWloWDuJBWOpjZJYHU5FCkYLKKNXjajPMon8tZ0xrXNpes11a6XGoQMC8108it1BjdozsT6KBnBZsYdFAMBIV6%2FSbfwYHv8AV8e22yvcCfLUjWwfrHCVyemICxDbrdA8qjvy1EA0b00ZpNoHwWsoYgg2CnyTJCR3BJiDB%2BuBs%2FsqXKbLvRnA%2BRRu8tijVfDr4Hybhxlbd%2BlTduFx4yW6mUd8q2qfmQOCs0ZWgtA5GaTTxl5B0XeA1TM%2BIIFihcwK1x53xXhwWDswHLK7bJq9flRIrEqT0Md1fh8ROy1Qozd4zon4vVb98231q5yv%2Fm8YAfVwIdQvClgnaelJfc6bQudf7tFsx0Ui2RPAQSxA4J5pP7B%2B91IERV3CpNwyezxcPd%2FDgdTdA%2BSx9mfgwhfpqOw%2B17HvIPwgm2NTO8qQ6J8guCl9uxSud0kXJTqtQfW7i%2Bvgbys%2FnG8Nz2DqP4VZL0qZ%2FoZ%2BR02D3r7cPknxCPU2DhB2TAg0GtuA%2B504Jh9XeNyecd8Yw%2Ba8t9cDUpOXnaO6d978Pmsrjha2lN5BjJYb2mvQ6Y%2Fj%2Br2x4G2M2Jp1opbbi1XvGuZhBtKje1cU20RjshtXeA5d0123h1vAD806NZ%2FVDL3%2FNGtofUq%2Bs%2F9RVaqG7Yr%2Bq7jdctzPfZWqmXRQfivU5qPfkbbtUDVNRIzdboC8ckMoWJ%2B31HuopCnfpN8PsXCXNekEEHAAA%3D) can be used as a direct link as well.


```
# This can be any progressed save where you are able to generate some IST slots
Initialize 2 Apple 2 Acorn 1 Wood 1 KorokSeed 1 Paraglider 1 SheikahSlate
Save
# Restart game to clear any existing IST slots, just to be safe
Close game
# Autosave 1: ONLY 2 items: Woodcutter's Axe (equipped) and Sheikah Slate
# NOTE: If you wish to corrupt Spirit Orbs instead of Korok Seeds, generate the autosave while within a Rune shrine
Get 1 SheikahSlate 1 WoodcuttersAxe
Save as auto1
# Autosave 2: ONLY 3 items: Woodcutter's Axe (equipped), Sheikah Slate, and stackable KI (Korok Seed or Spirit Orb)
Get 1 KorokSeed
Save as auto2
# From the progressed save, generate 2 IST offsets (see CHECK below)
Reload
Break 2 slots with 1 Apple 1 Acorn
# CHECK: Will your Sheikah Slate be transferred into Autosave 1?
# - No: Repeat the next 2 steps (reload+unequip) exactly 3x.
# - Yes, left IST slot: Repeat the next 2 steps exactly 4x.
# - Yes, right IST slot: Repeat the next 2 steps exactly 2x.
Reload auto1
Unequip WoodcuttersAxe
Reload auto1
Unequip WoodcuttersAxe
#Reload auto1
#Unequip WoodcuttersAxe
#Reload auto1
#Unequip WoodcuttersAxe
# Once you have 2 axes RIGHT of the slate, reload the OTHER autosave
Reload auto2
# DO NOT SYNC the GameData before generating an autosave
# GameData should show 999 seeds/orbs, while Visible Inventory still shows 3 axes and 2 KIs
Save as auto3
# The 1x Korok Seed covered by IST currently needs to be removed before Autosave 3 can be loaded.
Reload auto1
Unequip WoodcuttersAxe
Reload auto1
Unequip WoodcuttersAxe
Reload auto1
# The stackable KIs should no longer be covered by IST; reload Autosave 3 containing 999x
Reload auto3
# IST is now covering the Sheikah Slate and the 999x stackable KI; send them to your progressed save
Reload
# Sync before saving, else GameData won't reflect the 999x stackable KIs.
Sync GameData
Save
```
