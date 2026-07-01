# Features

## Modular chest rigs

Many chest rigs are now modelled as two separate parts: the _placard_, which holds PALS webbing or integrated pouches, and the _harness_, which allows the placard to be worn on one's person. This is how most modern chest rigs, including those issues to the military, function today.

This allows players to

- maintain multiple loadouts which are easy to swap
- manage encumbrance by managing their tactical kit
- more easily modularize their equipment

Different placards provide different affordances: some feature an abundance of integrated pouches, while others enable complete freedom in which pouches to attach by providing varying amounts of PALS webbing.

Different harnesses contribute to the equipment equation by handling placards differently: one harness may fit better for lighter loadouts because its small initial encumbrance grows quickly with heavier loads, while another may offer greater support for a lot of kit because its high initial encumbrance scales far slower. Beyond that, harnesses themselves may provide PALS webbing for small pouches (for e.g. knives, grenades, or suppressors), and may feature other unique traits that may each more useful for a particular situation.

## PALS attachments audit

Existing pouches have been audited for PALS compatibility and size.

Items which weren't described as MOLLE-compatible – such as handcrafted unconventional pouches – aren't so anymore. (They may be adopted for other attachment systems in the future.)

Valid PALS-attached equipment has been audited to use the most-reasonable `PALS_*` flag commensurate with the amount of PALS cells they take. The basis of `PALS_LARGE` is the triple-stacker pouch, which takes up 36 cells (2×6 = 12 cells per magazine pocket, times three pockets), it being the largest pouch in the arsenal. Every other pouch has then been scaled on the amount of 2×6-cell slots it takes: `PALS_MEDIUM` is two slots, `PALS_SMALL` is one. (Many pouches are even smaller than that in reality, so they would be taking even less space than `PALS_SMALL`. Many single-grenade pouches, for example, take up onto 2×2 cells.)

## Magazine pouch remodelling

Magazine pouches have been differentiated by their closure mechanism:

- open-top, where the magazine is held in place with an elastic strap
- flap, either hook-and-loop or magnetic
- plastic buckle

Based on this, plus the pouch's own characteristics (e.g. it's designed for shorter magazines, or it has a plastic insert that would keep the magazine firmer in place), give each pouch a unique performance profile.

Open-top pouches, for example, are the quickest to draw from, so they're useful in fast-paced firefights, but the loose retention mechanism may allow magazines to fall out when you're grabbed. On the other hand, buckle pouches' closure is so firm, the magazine can never fall out, though the same quality contributes to comparatively-slow reloads.

Higher-capacity magazines are now naturally slower to reload from because of the difficulty of indexing the magazine. Note that underloading large pouches doesn't affect this in any way.

## Belts

Load-bearing belts: a combat belt for fast access to holsters and MOLLE pouches, a duty belt for larger pockets and comfort.

## Ballistic plates and carriers

The plates and carriers are remodelled, with more of each. Ceramic plates stop armor-piercing rifle rounds but crack as they absorb hits and wear out over several; steel plates stop less and weigh much more but take repeated hits without degrading. Side plates cover the flanks. Carriers come as distinct models — a slick low-profile one, the issued IOTV and MSV, a law-enforcement model — differing in weight, encumbrance, and what they accept, along with their cummerbunds, shoulder pads, and protectors.

## Soft ballistic vests

Soft-armor vests — covert and stab-resistant, lower-tier concealable — that stop pistol rounds and blades but not rifle fire. Their panels are integral and can't be swapped out.

## Gloves

Tactical gloves steady recoil while worn. Models trade warmth, bulk, and dexterity: a thin breathable glove, a lighter fire-resistant one, a heavy insulated mitt with a separate trigger finger, a liner to wear underneath.

## Ballistic-armor training

Wearing a plate carrier or ballistic vest trains a proficiency that lowers its encumbrance and raises its protection. It builds up passively through wear.

## Loadouts

Military and police characters spawn with kit matching their real role and era — a pilot has no chest rig, a park ranger carries a baton, an older veteran wears his decade's gear. Roles trained on armor start with the fitting proficiency; others can take a Ballistic Armor Training hobby for it. Enemies drop role-appropriate armor: police carry soft vests, not military plates.
