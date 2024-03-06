# 1. Case: Urborg, Tomb of Yawgmoth vs. Blood Moon

### Urborg, Tomb of Yawgmoth
**Legendary Land** 

Rulestext: *Each land is a Swamp in addition to its other land types.* 
https://scryfall.com/card/tsr/287/urborg-tomb-of-yawgmoth

### Blood Moon
**Enchantment** {1}{R}{R}

Rulestext: *Nonbasic lands are Mountains.* 
Notes via Gatherer: *Nonbasic lands will lose any other land types and abilities they had. They will gain the land type Mountain and gain the ability “{T}: Add {R}.”*
https://scryfall.com/card/2xm/118/blood-moon

## Problem
Which continuous effect occurs: Will all other Lands be Swamps in addition to other land types, or will nonbasic Lands become basic Mountains?
The answer depends on the dependency system, rule 613.8

## Expected Outcome
*Blood Moon* will override *Urborg, Tomb of Yawgmoth* ability because of 

*613.8. Within a layer or sublayer, determining which order effects are applied in is sometimes done using a dependency system. If a dependency exists, it will override the timestamp system.* 

All nonbasic lands will be Mountains, which includes Urborg. It loses it's ability.
In this case it doesn't matter, which card was played first: *Blood Moon* will turn *Urborg* into a basic Mountain before it's entering the battlefield.

# 2. Case: Opalescence vs. Humility

### Opalescence
**Enchantment** {2}{W}{W} 

Rulestext: *Each other non-Aura enchantment is a creature in addition to its other types and has base power and base toughness each equal to its mana value.* 
https://scryfall.com/card/uds/13/opalescence

### Humility
**Enchantment** {2}{W}{W} 

Rulestext: *All creatures lose all abilities and have base power and toughness 1/1.* 
https://scryfall.com/card/tpr/16/humility

## Problem
If Humility is played, all creatures will be 1/1. But Opalescence states that every enchantment (in that case: Opalescence and Humilitiy) will be 4/4 creatures. 
This conflict is solved by the timestamp-rule 613.7.
The outcome depends on which card is played first. 

## Expected Outcome
There are 7 layers in which continuous effects are applied to cards (613.1): 
In layer 4, Type-changing effects are applied (the enchantment becomes a creature). 
In layer 6, the cards lose all their abilities.
In layer 7, Power and Thoughness is changed. 

### First Humility, then Opalescence:
All creatures will be 4/4.

### First Opalescence, then Humility:
All creatures will be 1/1.

# 3. Case: Possessed Nomad vs. Humility

### Possessed Nomad
**Creature — Human Nomad Horror** {2}{W}{W}

Rulestext: *Vigilance, Threshold — As long as seven or more cards are in your graveyard, Possessed Nomad gets +1/+1, is black, and has “{2}{B}, {T}: Destroy target white creature.”* 
https://scryfall.com/card/tor/13/possessed-nomad

### Humility
**Enchantment** {2}{W}{W} 

Rulestext: *All creatures lose all abilities and have base power and toughness 1/1.* 
https://scryfall.com/card/tpr/16/humility

## Problem
This case is the most complex. The abilities of *Possessed Nomad* happen in different layers: 
- Layer 5: Colorchanging
- Layer 6: A new ability is added
- Layer 7: Power and Thoughness is changed

## Expected Outcome
