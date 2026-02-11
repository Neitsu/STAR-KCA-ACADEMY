# Star KCA Academy — Static Site (GitHub Pages)

Version actuelle centrée sur 3 vues uniquement:
- **Contestants**
- **Profile** (fiche candidat)
- **Rankings** (table trajectoire PRERANK → FINAL)

## Déploiement (ultra simple)

1. Push le repo sur GitHub.
2. Ouvre **Settings → Pages**.
3. Choisis **Deploy from a branch**.
4. Sélectionne ta branche (ex: `main`) + dossier `/root`.
5. Ouvre l'URL GitHub Pages.

Aucun build requis: c'est un site statique (`index.html`).

## Configuration Google Sheets

Dans `index.html`, configure `CONFIG.SHEET_ID`.

Le site lit les onglets:
- contestants
- rounds
- submissions
- scores
- judge_rankings
- round_status
- votes_live

Même si certains onglets ne sont pas affichés dans le menu, ils sont gardés pour compatibilité future.

## Point important sur les statuts

Les statuts candidats sont lus uniquement depuis l'onglet `round_status`.

- Si un statut n'existe pas pour un candidat/round, le site affiche **TBD**.
- Le site **n'invente plus de statuts par défaut** (pas de safe/eliminated auto).

Valeurs statut attendues:
- `safe`
- `nominee`
- `saved_judges`
- `saved_public`
- `eliminated`

## Sans Google Sheet

Si `SHEET_ID` n'est pas configuré, le site utilise un fallback local de démonstration.
Ce fallback ne fournit pas de statuts de round (donc affichage `TBD`), pour éviter tout statut arbitraire.

