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

**_Remote Mine (Buggy):_**
(R1)(C1)(C2)\
(R2)(C3)\
(I, Item: fireworkscharge (Name:Activate Mine)) <== Located on C1

## Commands:

**Note:**
1. Delays on repeating command blocks are 2
2. C = Conditional
3. Unless told all command blocks are unconditional

**_Geyser Trap:_**

**(R1):** tag @e[type=item, name="Trap Capsule (Geyser)", tag=, c=1] add summontrap

**(C1):** execute @e[type=item, name="Trap Capsule (Geyser)"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] add geysertrap

**(C2, C):** kill @e[type=item, name="Trap Capsule (Geyser)", tag=summontrap, c=1]

**(R2):** execute @e[type=armor_stand, name=sTrap, tag=geysertrap] ~ ~ ~ tag @a[r=2.25] add geyseractive

**(C3, C):** execute @a[tag=levactive] ~ ~ ~ kill @e[type=armor_stand, name=trap, tag=levitate, r=2.25, c=1]

**(C4):** playsound mob.wither.shoot @a[tag=geyseractive]

**(C5):** execute @a[tag=geyseractive] ~ ~ ~ particle minecraft:knockback_roar_particle ~ ~ ~

**(C6):** effect @a[tag=geyseractive] levitation 1 25 true

**(C7, C):** tag @a[tag=geyseractive] remove levactive

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

**(C4, C):** playsound mob.blaze.hit @a[tag=bearactive]

**(C5, C):** kill @a[tag=bearactive]

**(C6):** tag @a[tag=bearactive] remove bearactive
