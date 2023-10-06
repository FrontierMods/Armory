# Armory

*Armory* (`armory`) expands your character's choice of military, riot, police, and militia outfits and equipment.

In particular, it adds a modular equipment framework that gives players the ability to pick the kind of functionality they want their gear to have, without resorting to crafting. This makes the system both easy to manage and easy to expand with other mods.

⚠ Since July 2023, Frontier Mods are being worked on again.


## Status

*Armory* is currently **in development**.

The latest supported version of the game is **0.G**.



### New Pocket Restrictions

Several pockets within the system only allow a handful of items in.

This has been done in part as a proof of concept, and in part to demonstrate the depth of the system. These changes are likely to be carried through the mod, as they add further depth and detail to gameplay.

1. `PAPER_FILE_SIZED`: papers, files, small journals. Simulates carrying documents inside the admin pouch. Intended for important documentation, such as lab journals.¹ Several existing documents have been modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

2. `CARD_STANDARD`: credit cards and IDs. Specifically, cards following the [ISO/IEC 7810](https://en.wikipedia.org/wiki/ISO/IEC_7810) ID-1 standard, the most commonly used standard for such purposes. The MOLLE vest itself, as well as some pouches, have pockets dedicated specifically for these cards. Some existing cards have had their size and weight modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

¹ During development it turned out that lab journals are significantly bigger than anticipated, and would not fit into the admin pouch under any circumstance. This may be omitted in the future, or mod-side changes may be made to accomodate that purpose. It's from the movies, so it's too cool to just pass on.


## Content

## Modular Equipment

*Armory* introduces the concept of modular equipment into the game.

Under this system, players can mix and match different types of pouches, pockets, and decoration with items that allow it. Currently, the MOLLE system is loosely implemented, and belt attachment system is implied though not fleshed out separately from MOLLE.

Using MOLLE equipment is as easy as `[i]`nserting the pouches and decorative pieces into MOLLE gear via the `[e]`xamine menu, or `[a]`ctivating it to attach pouches via in-game menu. Adding more pouches – and inserting more items into those pouches – will increase encumbrance of the piece of equipment you're latching the modules onto.


### Technical Information

This is achieved via using the `flag_restriction` parameter of the foundational MOLLE item (i.e. the one you attach pouches to).

MOLLE accessories are assigned the flag `MOLLE_POUCH`. MOLLE patches and other decorations are assinged the flag `MOLLE_DECOR`.

MOLLE gear itself has pockets that enable adding only items with either of the flag. The gear itself has their own flag, `MOLLE_GEAR`, which notes in its description that it's usable as modular equipment. The `MOLLE_GEAR` flag is only about clarity towards the player; it plays no role of its own.

Shoulder rigs use a similar system: items with the `SHOULDER_RIG` flag accept items with the `SHOULDER_RIG_MODULE` flag.


# License

MIT