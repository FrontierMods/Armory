# Desired Features

You can help the mod by implementing the following features for the next stable release.

## Overcapacity

**TL;DR**: allow containers to support more weight/volume/length than they're rated for, in exchange for tangible negatives.

In reality, many containers (jacket pockets, backpacks, holsters, duffel bags...) can carry more than the original design intended for, in exchange for the carry being cumbersome or unwieldy. Think about carrying short wooden planks in a duffel bag: it is certainly possible, and something of a challenge by way of wild swinging if you're not careful. At the same time, using the same duffle bag to carry your gym outfit is not challenging, because the design of the bag supports the weight and the volume to be distributed evenly inside the bag, with any potential extra encumbrance mitigated by the support of the walls and the top of the bag.

Most of the time, even in a survival situation, one does not find themselves suddenly carrying something that's larger than any of their containers intend. However, which it becomes necessary – say, for a desired weapon, or a long-sought-after tool – one would _really_ wish that the game's containers followed real-life logic. For occasions such as these, it would be great to have some pockets be able to take in larger-than-designed-for items at a penalty to encumbrance. Both volume and length would contribute to the resulting malus. (Weight should be considered for encumbrance as well, but isn't in the base game – for the most part, anyway – and so isn't being explored here, either.)

Roughly-speaking, non-rigid pockets should allow for a level of (definable, but defaulting to a preset value) elasticity and overboard length.

### Elasticity

**Elasticity** could be a property of the pocket's/item's material, where it would serve as a default, as well as a property of the pocket itself; pocket settings override material settings. With a mandatory `max_contains_volume` and the new `elasticity`, for each pocket, contained volumes between `max_contains_volume` and `max_contains_volume × elasticity` would incur a penalty at 2× the `volume_encumber_modifier`, in addition to the pocket's baseline maximum encumbrance. For example:

Imagine a pocket with `max_contains_volume` of `500 ml`, `volume_encumber_modifier` unset (defaults to `1.0`), and `elasticity` of `1.5`:

- at `250 ml` contained, the pocket would incur 1 encumbrance
- at `500 ml`, it would incur 2 instead
- at `750 ml` (`500 ml × 1.5`), it would incur 4 encumbrance
  - `250 ml` × (`2 × 1.0`) of baseline maximum encumbrance, plus
  - `250 ml` × (`1 × (1.0 × 2)`) of elastic maximum encumbrance

### Overboard Length

**Overboard length** would default to 1.5× the pocket's `max_item_length`, and could be adjusted per pocket with `overboard_length`. `overboard_length` is always a multiplier; for it to work, `max_item_length` must be defined.

Similarly to elasticity, overboard length could add encumbrance of items of the length between `max_item_length` and `max_item_length × overboard_length`. 1 unit of encumbrance would accumulate for each 20% of `max_item_length × overboard_length`, on top of the item's volume-based encumbrance (already modified by the elasticity calculation).

### Considerations

Together, the two measures of overcapacity would represent a container's ability to handle larger-items in exchange for extra burden. This creates both a potential for extra loot and a possibility of perishing to one's greed, both of which represent important in-game considerations for new and experienced players. It expands the options available to the player, while providing adequate in-game response that corresponds with the player's understanding of reality. Overall, it pushes the skill floor slightly-higher (because it is another mechanic that may not be readily-apparent to new players), while allowing experienced players to maximize their loot.

Each pocket that provides elastic or overboard overcapacity should have the option to toggle filling the pocket with either, independently or together. The default state of the options should be "on", as otherwise the option may remain undiscoverable for a lot of players until much-later. Toggling overfilling off would allow experienced players to manage their encumbrance more-effectively, by controlling the loot flow between the environment and their pockets.

One of the stretch goals of this feature could be warning the player if one of the items they're about to loot would trigger overcapacity (regardless of its nature). Another may be prompting the player to enable overcapacity on a pocket with overcapacity off, should that pocket be the only one able to take in a particular item with overcapacity on.

Overcapacity could, among other things, enable certain pistol holsters to take in larger pistols (such as those with suppressors) at a cost, eliminating the need for the large holster, which is an item inadequate to reality. This, in turn, could create an opportunity field for custom, survivor-grade holsters explicitly designed to take in suppressed pistols, which would provide a less-encumbering pocket for those in exchange for longer draw times.

## Multimodal pockets

**TL;DR**: some pockets should be definable as usable in multiple ways (e.g. either a holster for an object above defined dimensions, or a non-holster pocket for many smaller items), where using one way disqualifies all others for that pocket.

[proper outline TBD]

## Volume calculation from dimensions

**TL;DR**: allow initial volume and longest-side values to be calculated from a provided `dimensions` object (or an array of objects).

[proper outline TBD]

## Slot-based pocket restrictions

**TL;DR**: allow pockets to be grids of [non-specific] slots, and calculate restrictions based on items' `slots` property.

Currently, the only system to benefit from the idea of slots is PALS (aka MOLLE), for which quantities of slots are abstracted. This in itself makes it slightly awkward to use smaller MOLLE pouches. For example, in-game grenade pouches take up the same amount of slots as sheaths, holsters, and gadget pouches. In real life, grenade pouches take up fewer PALS slots; depth (i.e., distance from the grid outwards) contributes to their size the most, not width or height (both of which dictate the amount of slots required for mounting the pouch).

### Pockets all the way down

PALS could be expanded into a specialized pocket-based system, which would allow slots to be taken up in a manner consistent with reality. Making it pocket-based would allow for an easier pocket management for the system, by enabling players to put on and take off pouches quickly by simply inserting or dropping them like any other item. Allowing PALS webbing to be defined as multiple pockets would also make the system more realistic, by dividing grids which are not connected on the item (e.g. single large belly/thorax webbing and small grids on each shoulder strap); this serves as an extension of the pocket system mechanically and semantically, as it meaningfully limits the amount of space available for extra pouches.

With this genericized approach to slots, the system could be expanded to include common, rare, and fictional modular-equipment systems. For example, ALICE (one of the predecessors to MOLLE), Smerch (the Russian rig system), Tragesystem 95 (the German system)... Even belts and shoulder straps could be modelled as having "slots" for generic belt-capable equipment: pouches, tools, holsters, sheaths, rings (to hold other, non-belt-capable equipment), and adapters for other slot-based systems.

The pocket definition for the system would look something like this:

```json
[
  {
    "pocket_type": "SLOTS",
    "system": "pals",
    "//slots": "for PALS, one cell = one slot",
    "slots": 24,
    "description": "Front PALS webbing",
    "volume_encumber_modifier": 0.75,
    "//moves": [
      "only affects the speed of attaching/detaching to the slots, NOT retrieving item from the pouch using the slots",
      "overrides default move cost; see slot system definition"
    ],
    "moves": 220
  }
]
```

One would then define the system as a separate JSON object, in a way similar to defining flags:

```json
[
  {
    "type": "SLOT_SYSTEM",
    "id": "pals",
    "name": "PALS",
    "//default_noise": [
      "default noise for moving pouches etc. to/from this system",
      "only affects pouches etc., NOT items inside those"
    ],
    "default_noise": 3,
    "//default_moves": [
      "default move cost for moving pouches etc. to/from this system",
      "only affects pouches etc., NOT items inside those",
      "each pouch may have its own move cost, which WOULD affect items inside them"
    ],
    "default_moves": 200
  },
  {
    "type": "SLOT_SYSTEM",
    "id": "velcro",
    "name": "hook-and-loop",
    "//default_noise": "Velcro is noisy",
    "default_noise": 15,
    "//default_moves": "Velcro is fast to operate",
    "default_moves": 80
  }
]
```

### Why this is better for the player

One crucial difference between regular, volume-based pockets and these slot-based ones is being able to handle effects that would otherwise be realistic in a consistent and player-friendly manner. For volume-based pockets, items which suddenly overflow the pocket's volume capacity can slip out of the pocket; this is perfectly-reasonably for regular pockets, but would make no sense for slot-based ones due to how they attach to the grid. (Attempts to implement a volume-based PALS system by Armory have failed for this reason in particular.)

Another crucial difference is being able to treat slot-based pockets as "integral" pockets of the item they're attached to, for the purpose of inventory management. Rather than show as part of any other pocket (like a rock would inside a pants pocket), they could be reasonably expected to appear as though they're part of the "primary layer" of pockets. This is one advantage of the current PALS system: helping players maintain a reasonable mental model for their equipment.

The latter also avoids pocket depth rot, where each pocket adds extra move cost for retrieving an item inside. As slot systems would generally position their attached pockets in a way that's easy to access, the slot pocket would not impose extra move cost onto containers inside it. In other words, the flashlight pouch on your ballistic vest would remain easy to access, even though the pouch is technically inside a pocket of its own. (Of course, putting the vest inside a large bag would impose retrieval cost limitations on the pouch as expected.)

### Surface area slots

A slot-based system could also serve as a reasonable approximation for equipment that relies on surface area, such as Velcro (aka hook-and-loop) pouches, hangers, and identification/morale patches. What constitutes a "slot" for something that doesn't follow a standardized grid can be derived experimentally, based on real-world options. For example, a Velcro slot can be defined as 1 in² based on morale patches from popular stores generally adhering to 0.5-inch-based steps in dimensions; then, an 11-inch by 3-inch Velcro panel that displays the name of the owner's law enforcement agency would take up 33 slots of hook-and-loop surface. The same system could be applied to morale patches (3.5″ × 1.25″ ≈ 5 slots, rounded up), pouches (6.5″ × 3″ ≈ 20 slots), and so on.

## Whitelisted gunmods

**TL;DR**: some holsters should allow guns with certain (classes of) gunmods to be put inside by discounting their volume and length (but not weight) for volume/length restriction calculations.

[proper outline TBD]
