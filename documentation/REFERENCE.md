# Reference & Notes

## Clothing

### Volume

- **upperwear** (t-shirts, coats, jackets etc.): `chest * (1/2 * height + 1/3 * sleeve) * thickness`, where

  - `chest`: chest circumference; halved to get torso width
  - `height`: total length (or height) of the torso part, measured at the back
  - `sleeve`: length of sleeve
  - `chest` is divided by `6 (= 2 × 3)` to get `1/3` of torso width (assumed to be sleeve width)
  - initial (unsimplified) formula: `(chest / 2 × height + chest / 6 × sleeve × 2) × thickness`
  - if `sleeve` is not provided, assume `sleeve` to be `1/1.75 × chest`

- **lowerwear** (pants, shorts etc.): `(2 * inseam + rise) * waist * thickness`, where

  - `inseam`: inseam length (i.e., length of pant leg between hem and crotch)
  - `rise`: rise length (i.e., length between crotch and top of waistband); if not available, assume:
    - low rise: `<9 in.` (usually `7—9 in.`) — very casual
    - regular/mid rise: `9—11 in.` — mix between casual and formal
    - high rise: `>11 in.` — comfortable
  - `waist`: waistband circumference
  - `thickness`: material thickness

## Ballistic Armor

### Dimensions

Quick reference:

- **MOLLE cell**: 1″ tall × 1.5″ wide

### Ballistic Plates

#### Coverage

Coverage is roughly divided between front/back and side plates. Front/back plates can only cover up to 80% of the torso. Side plates, therefore, can only cover up to 20%. With that in mind, visual reference of coverage area is multiplied by these modifiers in order to get the final value.

**Front / Back plates**:

[_visual reference_](https://help.trex-arms.com/hc/en-us/articles/5917157627415-Body-Armor-For-Beginners)

- **SAPI small plate**: 38% (×80% → 30%) upper torso coverage + 10% (×80% → 08%) lower torso coverage
- **SAPI medium plate**: 42% (×80% → 34%) upper torso coverage + 12% (×80% → 10%) lower torso coverage
- **SAPI large plate**: 45% (×80% → 36%) upper torso coverage + 16% (×80% → 13%) lower torso coverage
- **SAPI XL plate**: 48% (×80% → 38%) upper torso coverage + 20% (×80% → 16%) lower torso coverage

**Side plates**:

[_visual reference_](https://www.apexarmorsolutions.com/post/are-side-plates-necessary)

- **6″ × 6″ plate**: 00% (×20% → 00%) upper torso coverage + 25% (×20% → 05%) lower torso coverage
- **6″ × 8″ plate** (aka **tall side plate**): 12% (×20% → 02%) upper torso coverage + 25% (×20% → 05%) lower torso coverage

#### Cut

**Full cut**: a(n almost) rectangular cut with rounded or slightly-clipped corners. Usually reserved for back and side plates. Provides the most coverage. Most plate carriers do not allow putting a full-cut plate in the front due to their design.

**SAPI cut**: standard way to cut ballistic plates. Used by military plates. Top corners are clipped at a 45° angle.

**Shooter cut** (also: **shooter's cut**): similar to SAPI cut, but with the bottom corners also clipped (to a smaller degree). Trades off a bit of coverage for a bit of increased mobility overall.

**Swimmer cut** (also: **swimmer's cut**): a cut with a sharper angle for top corner clipping. Trades off some coverage for increased shoulder/arm mobility.

#### Curvature

**Single-curve**: standard curvature of a ballistic plate. Relatively-cheap to produce.

**Multi-curve**: advanced curvature. Fits better with the body, removing hot spots and reducing discomfort.
