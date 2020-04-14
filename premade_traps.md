## Layout:

**_Geyser Trap:_**\
(R1)(C1)(C2)\
(R2)(C3)(C4)(C5)(C6)(C7)

**_Mine Trap:_**\
(R1)(C1)(C2)\
(R2)(C3)(C4)(C5)

**_Bear Trap:_**\
(R1)(C1)(C2)\
(R2)(C3)(C4)(C5)(C6)

**_Smite Trap:_**\
(R1)(C1)(C2)\
(R2)(C3)(C4)(C5)(C6)(C7)

**_Frost Trap:_**\
(R1)(C1)(C2)\
(R2)(C3)(C4)(C5)(C6)(C7)(C8)

## Commands:

**Note:**
1. Delays on repeating command blocks are 4

**_Geyser Trap:_**

**(R1):** tag @e[type=endermite, name="Trap Capsule (Geyser)", tag=, c=1] add summontrap

**(C1):** execute @e[type=endermite, name="Trap Capsule (Geyser)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add geysertrap

**(C2, C):** /execute @e[type=armor_stand, name=sTrap, tag=geysertrap] ~ ~ ~ kill @e[type=endermite, name="Trap Capsule (Geyser)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=traparmed, tag=geysertrap] ~ ~ ~ tag @a[r=4] add geyseractive

**(C3, C):** execute @a[tag=geyseractive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=geysertrap, r=4, c=1]

**(C4):** playsound mob.wither.shoot @a[tag=geyseractive]

**(C5):** execute @a[tag=geyseractive] ~ ~ ~ particle minecraft:knockback_roar_particle ~ ~ ~

**(C6):** effect @a[tag=geyseractive] levitation 1 25 true

**(C7):** tag @a[tag=geyseractive] remove geyseractive

**_Mine Trap:_**

**(R1):** tag @e[type=endermite, name="Trap Capsule (Mine)", tag=, c=1] add summontrap

**(C1):** execute @e[type=endermite, name="Trap Capsule (Mine)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add minetrap

**(C2, C):** /execute @e[type=armor_stand, name=sTrap, tag=minetrap] ~ ~ ~ kill @e[type=endermite, name="Trap Capsule (Mine)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=traparmed, tag=minetrap] ~ ~ ~ tag @a[r=2] add mineactive

**(C3, C):** execute @a[tag=mineactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=minetrap, r=2, c=1]

**(C4, C):** execute @a[tag=mineactive] ~ ~ ~ summon ender_crystal ~ ~ ~ minecraft:crystal_explode

**(C5):** tag @a[tag=mineactive] remove mineactive

**_Bear Trap:_**

**(R1):** tag @e[type=endermite, name="Trap Capsule (Bear)", tag=, c=1] add summontrap

**(C1):** execute @e[type=endermite, name="Trap Capsule (Bear)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add beartrap

**(C2, C):** /execute @e[type=armor_stand, name=sTrap, tag=beartrap] ~ ~ ~ kill @e[type=endermite, name="Trap Capsule (Bear)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=traparmed, tag=beartrap] ~ ~ ~ tag @a[r=1.5] add bearactive

**(C3, C):** execute @a[tag=bearactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=beartrap, r=1.5, c=1]

**(C4, C):** execute @a[tag=bearactive] ~ ~ ~ summon evocation_fang ~ ~ ~

**(C5, C):** playsound mob.blaze.hit @a[tag=bearactive]

**(C6, C):** kill @a[tag=bearactive]

**(C7):** tag @a[tag=bearactive] remove bearactive

**_Smite Trap:_**

**(R1):** tag @e[type=endermite, name="Trap Capsule (Smite)", tag=, c=1] add summontrap

**(C1):** execute @e[type=endermite, name="Trap Capsule (Smite)", tag=summontrap] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add smitetrap

**(C2, C):** /execute @e[type=armor_stand, name=sTrap, tag=smitetrap] ~ ~ ~ kill @e[type=endermite, name="Trap Capsule (Smite)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=traparmed, tag=smitetrap] ~ ~ ~ tag @a[r=3] add smiteactive

**(C3, C):** execute @a[tag=smiteactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=smitetrap, r=3, c=1]

**(C4, C):** execute @a[tag=smiteactive] ~ ~ ~ summon lightning_bolt ~ ~ ~

**(C5, C):** effect @a[tag=smiteactive] blindness 10 255 true

**(C6, C):** effect @a[tag=smiteactive] wither 3 10 true

**(C7):** tag @a[tag=smiteactive] remove smiteactive

**_Frost Trap:_**

**(R1):** tag @e[type=endermite, name="Trap Capsule (Frost)", tag=, c=1] add summontrap

**(C1):** execute @e[type=endermite, name="Trap Capsule (Frost)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add frosttrap

**(C2, C):** kill @e[type=endermite, name="Trap Capsule (Frost)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=traparmed, tag=frosttrap] ~ ~ ~ tag @a[r=3] add frostactive

**(C3, C):** execute @a[tag=frostactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=frosttrap, r=3, c=1]

**(C4, C):** effect @a[tag=frostactive] slowness 30 5 true

**(C5, C):** effect @a[tag=frostactive] mining_fatigue 30 2 true

**(C6, C):** execute @a[tag=frostactive] ~ ~ ~ /fill ~-1 ~-1 ~-1 ~1 ~2 ~1 packed_ice 0 keep

**(C7):** playsound random.glass @a[tag=frostactive]

**(C8):** tag @a[tag=frostactive] remove frostactive
