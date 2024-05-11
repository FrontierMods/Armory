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

## Surface-area-based pocket restrictions

**TL;DR**: allow pockets to be surfaces, and calculate restrictions based on items' `dimensions`.

[proper outline TBD]

## Whitelisted gunmods

**TL;DR**: some holsters should allow guns with certain (classes of) gunmods to be put inside by discounting their volume and length (but not weight) for volume/length restriction calculations.

[proper outline TBD]

## Required gunmods for holsters

**TL;DR**: certain holsters are built to latch onto specific models of gunmods. Guns without these gunmods cannot be allowed into the holster (while also respecting other restrictions).

[proper outline TBD]
