## Layout:

(R1)(C1)(C2)(C3)(C4)

## Commands:

**(R1, Delay: 2)**: execute @e[type=item, name="Trap Jammer"] ~ ~ ~ tag @e[type=armor_stand, name=sTrap, r=15] add deltrap

**(C1)**: execute @e[type=armor_stand, tag=deltrap] ~ ~ ~ particle minecraft:splash_spell_emitter ~ ~ ~

**(C2)**: kill @e[type=armor_stand, tag=deltrap]

**(C3)**: execute @e[type=item, name="Trap Jammer"] ~ ~ ~ title @p actionbar §eFound and jammed all nearby traps

**(C4)**: kill @e[type=item, name="Trap Jammer"]
