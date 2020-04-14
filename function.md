## Layout:

(R1)>(R2)(C1)(C2)(C3)(C4)(C5)

## Commands:

**(R1, Delay: 2)**: testfor @e[type=item, tag=summontrap]

**(R2, Execute on 1st: False, Delay: 7)**: execute @e[type=item, tag=summontrap, c=1] ~ ~ ~ summon armor_stand "sTrap" ~ ~ ~

**(C1)**: execute @e[type=item, tag=summontrap] ~ ~ ~ effect @e[type=armor_stand, name=sTrap, tag=, r=1] invisibility 100000000 2 true

**(C2)**: execute @e[type=item, tag=summontrap] ~ ~ ~ effect @e[type=armor_stand, name=sTrap, tag=, r=1] fire_resistance 100000000 2 true

**(C3)**: execute @e[type=armor_stand, name=sTrap, tag=, c=1] ~ ~ ~ particle minecraft:totem_particle ~ ~1 ~]

**(C4)**: execute @e[type=armor_stand, name=sTrap, tag=, c=1] ~ ~ ~ playsound random.anvil_land @a[r=10]

**(C4)**: execute @e[type=item, tag=summontrap] ~ ~ ~ title @p actionbar §aTrap has been successfully deployed
