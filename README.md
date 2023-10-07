# Armory

*Armory* (`armory`) expands your character's choice of military, riot, police, and militia outfits and equipment.

In particular, grounds existing equipment in reality by providing them with real names, dimensions, and properties (coverage, protection, breathability etc.), and adds distinct options for each class of items, to provide players with a better choice depending on situation requirements.

⚠ Since July 2023, Frontier Mods are being worked on again.


## Status

*Armory* is currently **in development**.

The latest supported version of the game is **0.G**.


## Design

### New Pocket Restrictions

Several pockets within the system only allow a handful of items in.

This has been done in part as a proof of concept, and in part to demonstrate the depth of the system. These changes are likely to be carried through the mod, as they add further depth and detail to gameplay.

1. `PAPER_FILE_SIZED`: papers, files, small journals. Simulates carrying documents inside the admin pouch. Intended for important documentation, such as lab journals.¹ Several existing documents have been modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

2. `CARD_STANDARD`: credit cards and IDs. Specifically, cards following the [ISO/IEC 7810](https://en.wikipedia.org/wiki/ISO/IEC_7810) ID-1 standard, the most commonly used standard for such purposes. The MOLLE vest itself, as well as some pouches, have pockets dedicated specifically for these cards. Some existing cards have had their size and weight modified to more closely resemble reality, so that their size could be reliably used in modelling pocket sizes.

¹ During development it turned out that lab journals are significantly bigger than anticipated, and would not fit into the admin pouch under any circumstance. This may be omitted in the future, or mod-side changes may be made to accomodate that purpose. It's from the movies, so it's too cool to just pass on.


## License

MIT