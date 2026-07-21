# Changelog — CoA Ascension Adaptation

Based on PallyPower-Improved-3.3.5 (Wrath branch / 3.3.5a client).

## Classes
- `PALLYPOWER_MAXCLASSES` raised to 22 (21 CoA classes + Pets).
- `ClassID` / `ClassToID` rebuilt with the client's real internal tokens
  (DEMONHUNTER=Felsworn, FLESHWARDEN=Knight of Xoroth, MONK=Templar, SONOFARUGAL=Bloodmage,
  PROPHET=Venomancer, WILDWALKER=Primalist, SPIRITMAGE=Runemaster, etc.).
- `ClassNames` added (display names + hover tooltips).
- `ClassIcons` pointing to local icons `Icons/CoA_*.tga` (extracted from the Ascension client).

## Spells (Sun Cleric)
- `Spells` / `GSpells` = 4 Devotions (Grace, Dawn, Emperors, Radiance), matched by name
  so all ranks are supported.
- `Seals` = 5 Vows (Grace, Light, Radiance, Dawn, Eclipse).
- Blessing icons pulled from the server.
- Normal/greater buff durations = 30 min.
- Auto-assign `Templates` rebuilt for 22 classes.

## Logic
- Player detection: `class == "PALADIN"` → `"SUNCLERIC"`.
- Paladin talents (`GetTalentInfo`) neutralized (CoA talent trees differ).
- `NeedsBuff`: classic role filters removed — every class can receive all 4 Devotions.
- Vow button (RF/Seal) forced visible.
- Layout forced to "Standard" (computed positioning, compatible with 22 columns).
- **Vow selection in the assignment window**: the (unused) aura slot on your own row now
  controls your Vow (mousewheel / left-click = cycle, right-click = clear), reusing the
  existing `SealCycle` / `SealAssign` functions.

## Interface
- Config window widened (+11 columns) and vertical geometry recomputed
  (class names above the icons, no overlap).
- Window title: "Cleric Power".
