# Changelog — Adaptation CoA Ascension

Basé sur PallyPower-Improved-3.3.5 (branche Wrath / client 3.3.5a).

## Classes
- `PALLYPOWER_MAXCLASSES` porté à 22 (21 classes CoA + Pets).
- `ClassID` / `ClassToID` régénérés avec les tokens internes réels du client
  (DEMONHUNTER=Felsworn, FLESHWARDEN=Knight of Xoroth, MONK=Templar, SONOFARUGAL=Bloodmage,
  PROPHET=Venomancer, WILDWALKER=Primalist, SPIRITMAGE=Runemaster, etc.).
- `ClassNames` ajoutée (noms affichés + tooltips au survol).
- `ClassIcons` pointant sur les icônes locales `Icons/CoA_*.tga` (extraites du client Ascension).

## Sorts (Sun Cleric)
- `Spells` / `GSpells` = 4 Devotions (Grace, Dawn, Emperors, Radiance), matchées par nom
  pour supporter tous les rangs.
- `Seals` = 5 Vows (Grace, Light, Radiance, Dawn, Eclipse).
- Icônes de bénédiction tirées du serveur.
- Durées buff normal/greater = 30 min.
- `Templates` auto-assign régénérés pour 22 classes.

## Logique
- Détection joueur : `class == "PALADIN"` → `"SUNCLERIC"`.
- Talents paladin (`GetTalentInfo`) neutralisés (arbres CoA différents).
- `NeedsBuff` : filtres de rôle classic supprimés — chaque classe peut recevoir les 4 Devotions.
- Bouton Vow (RF/Sceau) forcé visible.
- Layout forcé en "Standard" (positionnement calculé, compatible 22 colonnes).
- **Sélection du Vow dans la fenêtre d'assignation** : l'emplacement aura (inutilisé)
  de ta propre ligne pilote désormais ton Vow (molette / clic gauche = cycle, clic droit = retire),
  en réutilisant les fonctions `SealCycle` / `SealAssign`.

## Interface
- Fenêtre de config élargie (+11 colonnes) et géométrie verticale recalculée
  (noms de classes au-dessus des logos, sans chevauchement).
- Titre de la fenêtre : "Cleric Power".
