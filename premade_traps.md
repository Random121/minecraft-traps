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

**_Remote Mine (Buggy):_**\
(R1)(C1)(C2)(C3)\
(R2)(C4)\
(I, Item: fireworkscharge (Name:Activate Mine)) <== Located on C1

## Commands:

**Note:**
1. Delays on repeating command blocks are 2
2. C = Conditional
3. Unless told all command blocks are unconditional
4. Remote Mine C2 requires coordinate of item frame with item

**_Geyser Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Geyser)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Geyser)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add geysertrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Geyser)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=geysertrap] ~ ~ ~ tag @a[r=2] add geyseractive

**(C3, C):** execute @a[tag=geyseractive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=geysertrap, r=2, c=1]

**(C4):** playsound mob.wither.shoot @a[tag=geyseractive]

**(C5):** execute @a[tag=geyseractive] ~ ~ ~ particle minecraft:knockback_roar_particle ~ ~ ~

**(C6):** effect @a[tag=geyseractive] levitation 1 25 true

**(C7, C):** tag @a[tag=geyseractive] remove geyseractive

**_Mine Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Mine)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Mine)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add minetrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Mine)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=minetrap] ~ ~ ~ tag @a[r=1.5] add mineactive

**(C3, C):** execute @a[tag=mineactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=minetrap, r=1.5, c=1]

**(C4, C):** execute @a[tag=mineactive] ~ ~ ~ summon ender_crystal ~ ~ ~ minecraft:crystal_explode

**(C5, C):** tag @a[tag=mineactive] remove mineactive

**_Bear Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Bear)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Bear)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add beartrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Bear)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=beartrap] ~ ~ ~ tag @a[r=1.25] add bearactive

**(C3, C):** execute @a[tag=bearactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=beartrap, r=1.25, c=1]

**(C4, C):** execute @a[tag=bearactive] ~ ~ ~ summon evocation_fang ~ ~ ~

**(C5, C):** playsound mob.blaze.hit @a[tag=bearactive]

**(C6, C):** kill @a[tag=bearactive]

**(C7):** tag @a[tag=bearactive] remove bearactive

**_Smite Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Smite)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Smite)", tag=summontrap] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add smitetrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Smite)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=smitetrap] ~ ~ ~ tag @a[r=1.75] add smiteactive

**(C3, C):** execute @a[tag=thunderactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=thundertrap, r=2, c=1]

**(C4, C):** execute @a[tag=smiteactive] ~ ~ ~ summon lightning_bolt ~ ~ ~

**(C5, C):** effect @a[tag=smiteactive] blindness 10 255 true

**(C6, C):** effect @a[tag=smiteactive] wither 3 10 true

**(C7, C):** tag @a[tag=smiteactive] remove smiteactive

**_Frost Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Froat)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Froat)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add frosttrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Froat)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=frosttrap] ~ ~ ~ tag @a[r=1.75] add frostactive

**(C3, C):** execute @a[tag=frostactive] ~ ~ ~ kill @e[type=armor_stand, name=sTrap, tag=frosttrap, r=1.75, c=1]

**(C4, C):** effect @a[tag=frostactive] slowness 30 5 true

**(C5, C):** effect @a[tag=iceactive] mining_fatigue 30 2 true

**(C6, C):** execute @a[tag=frostactive] ~ ~ ~ /fill ~-1 ~-1 ~-1 ~1 ~2 ~1 packed_ice 0 keep

**(C7):** playsound random.glass @a[tag=frostactive]

**(C8):** tag @a[tag=frostactive] remove frostactive

**_Remote Mine (Buggy):_**

**(R1):** tag @e[type=item, name="Trap Capsule (Remote Mine)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Remote Mine)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add remotetrap

**(C2, C):** execute @e[type=item, name="Trap Capsule (Remote Mine)"] ~ ~ ~ execute @p ~ ~ ~ clone x y z x y z ~ ~1 ~

**(C3, C):** kill @e[type=item, name="Trap Capsule (Remote Mine)", tag=summontrap, c=1]

**(R2):** execute @e[type=item, name="Activate Mine"] ~ ~ ~ execute @e[type=armor_stand, name=sTrap, tag=remotetrap, rm=6, r=50, c=1] ~ ~ ~ summon ender_crystal ~ ~ ~ minecraft:crystal_explode

**(C4, C):** kill @e[type=item, name="Activate Mine", c=1]
