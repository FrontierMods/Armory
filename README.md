# Armory

*Armory* (`armory`) expands your character's choice of military, riot, police, and militia outfits and equipment.

In particular, it adds a modular equipment framework that gives players the ability to pick the kind of functionality they want their gear to have, without resorting to crafting. This makes the system both easy to manage and easy to expand with other mods.


## Status

*Armory* is currently in **DEMO 1**.

**DEMO 1** is the initial pre-release of the mod, demonstrating the potential of modular equipment. It isn't playable, but it is usable for the purpose of testing.

The goal of **DEMO 1** is to gauge public interest and get feedback on both the concept and the details of implementation. Feel free to play with the modular equipment via debug menu and leave your impressions in the Discussions section, and criticism or feature requests – in the Issues section.

**NOTE**: this mod, including demo versions, is compatible with the latest stable release only.


### How to Test Modular Equipment in DEMO 1

* You can spawn MOLLE equipment via the debug menu.

* `[i]`nsert MOLLE accessories into MOLLE modular vest.

* The accessories remain usable as storage while inserted into the vest. They cannot be worn as separate pieces of equipment. Attached accessories are part of the vest and will be taken off and put back on along with it.

* The accessories may also be used as dedicated containers outside the modular equipment system.

NOTE: MOLLE items currently have no description. This is adequate for the early stage this mod is in. Polish shall be applied down the line.


#### New Pocket Restrictions

Several pockets within the system only allow a handful of items in.

This has been done in part as a proof of concept, and in part to demonstrate the depth of the system. These changes are likely to be carried through the mod, as they add further depth and detail to gameplay.

1. `PAPER_FILE_SIZED`: papers, files, small journals. Simulates carrying documents inside the admin pouch. Intended for important documentation, such as lab journals.¹ Several existing documents have been modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

2. `CARD_STANDARD`: credit cards and IDs. Specifically, cards following the [ISO/IEC 7810](https://en.wikipedia.org/wiki/ISO/IEC_7810) ID-1 standard, the most commonly used standard for such purposes. The vest itself, as well as some pouches, have pockets dedicated specifically for these cards. Some existing cards have had their size and weight modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

¹ During development it turned out that lab journals are significantly bigger than anticipated, and would not fit into the admin pouch under any circumstance. This may be omitted in the future, or mod-side changes may be made to accomodate that purpose. It's from the movies, so it's too cool to just pass on.

Unfortunately, there's currently no way to tell which is which. Consult the JSON to alleviate that: item descriptions contain generous comments on their origins and details.


# Content


## Modular Equipment

*Armory* introduces the concept of modular equipment into the game.

Under this system, players can mix and match different types of pouches, pockets, and decoration with items that allow it. Currently, the MOLLE system is loosely implemented.

Using MOLLE equipment is as easy as `[i]`nserting the pouches and decorative pieces into MOLLE gear via the `[e]`xamine menu. Adding more pouches – and inserting more items into those pouches – will increase encumbrance of the piece of equipment you're latching the modules onto.


### Technical Information

This is achieved via using the `flag_restriction` parameter of the foundational MOLLE item (i.e. the one you attach pouches to).

MOLLE accessories are assigned the flag `MOLLE_POUCH`. MOLLE patches and other decorations are assinged the flag `MOLLE_DECOR`.

MOLLE gear itself has pockets that enable adding only items with either of the flag. The gear itself has their own flag, `MOLLE_GEAR`, which notes in its description that it's usable as modular equipment. The `MOLLE_GEAR` flag is only about clarity towards the player; it plays no role of its own.


# License

MIT