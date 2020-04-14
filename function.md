## Layout:

**_Summon Trap:_**

(R1)>(R2)(C1)(C2)(C3)(C4)(C5)

**_Safety Time:_**

(R1)(C1)(C2)(C3)(C4)

## Commands:
**Note:**
1. create scoreboard named "traptimer"

**_Summon Trap:_**

**(R1, Delay: 2):** testfor @e[type=item, tag=summontrap]

**(R2, Execute on 1st: False, Delay: 7):** execute @e[type=item, tag=summontrap, c=1] ~ ~ ~ summon armor_stand "sTrap" ~ ~ ~

**(C1):** execute @e[type=item, tag=summontrap] ~ ~ ~ effect @e[type=armor_stand, name=sTrap, tag=, r=1] invisibility 100000000 2 true

**(C2):** execute @e[type=item, tag=summontrap] ~ ~ ~ effect @e[type=armor_stand, name=sTrap, tag=, r=1] fire_resistance 100000000 2 true

**(C3):** execute @e[type=armor_stand, name=sTrap, tag=, c=1] ~ ~ ~ particle minecraft:totem_particle ~ ~1 ~]

**(C4):** execute @e[type=armor_stand, name=sTrap, tag=, c=1] ~ ~ ~ playsound random.anvil_land @a[r=10]

**(C5):** execute @e[type=item, tag=summontrap] ~ ~ ~ title @p actionbar  §aThe trap has been deployed and will arm in §c4 §asecond

**(C6):** execute @e[type=item, tag=summontrap] ~ ~ ~ scoreboard players set @e[type=armor_stand, name=sTrap, tag=, r=1, c=1] traptimer 20

**_Safety Time:_**

**(R1, Delay: 4):** scoreboard players remove @e[type=armor_stand, name=sTrap, scores={traptimer=1..}] traptimer 1

**(C1, C):** tag @e[type=armor_stand, name=sTrap, scores={traptimer=..0}] add traparmed

**(C2, C):** execute @e[type=armor_stand, name=sTrap, scores={traptimer=..0}] ~ ~ ~ playsound block.false_permissions @a[r=10]

**(C3, C):** execute @e[type=armor_stand, name=sTrap, scores={traptimer=..0}] ~ ~ ~ title @a[r=10] actionbar §cThe trap has been armed

**(C4, C):** scoreboard players reset @e[type=armor_stand, name=sTrap, tag=traparmed] traptimer
