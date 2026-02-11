# Star KCA Academy — Static Site (GitHub Pages)

Le site est maintenant centré sur :
- **Contestants** (auto triés sur le dernier classement officiel)
- **Profile** (fiche individuelle + performances + évolution)
- **Rankings** (trajectoire complète par round + graphique global)
- **Votes** (0 par défaut tant qu'aucune donnée réelle n'est fournie)

## Déploiement (très simple)

1. Push le repo sur GitHub.
2. `Settings` → `Pages`.
3. `Deploy from a branch`.
4. Branche `main` (ou autre) + dossier `/root`.
5. Ouvrir l'URL GitHub Pages.

Aucun build requis (`index.html` statique).

## Configuration Google Sheets

Dans `index.html`, renseigner :

```js
const CONFIG = {
  SHEET_ID: "TON_SHEET_ID",
  SHEETS: {
    contestants: "contestants",
    rounds: "rounds",
    submissions: "submissions",
    scores: "scores",
    judge_rankings: "judge_rankings",
    round_status: "round_status",
    votes_live: "votes_live"
  }
}
```

## Comment modifier le classement (important)

Le site prend le classement officiel via **2 options** :

1. **Option prioritaire** : onglet `judge_rankings` avec `judge_name = official`
   - Colonnes : `round_id, judge_name, contestant_id, rank`
   - Exemple : `ROUND_2, official, yza, 1`

2. **Option de secours** : onglet `scores`
   - Colonnes : `round_id, contestant_id, total`
   - Le site trie automatiquement les `total` pour produire le rank.

👉 Si tu veux un contrôle total et clair : utilise l'option 1 (`judge_rankings` + `official`).

## Comment modifier les statuts des candidats

Onglet : `round_status`

Colonnes :
- `round_id`
- `contestant_id`
- `status`

Statuts supportés :
- `safe`
- `nominee`
- `saved_judges`
- `saved_public`
- `eliminated`

Règle du site :
- aucun statut inventé
- si absent → affichage `TBD`

Les cartes Contestants affichent automatiquement les statuts du **dernier round disponible** (selon ranking/status data).

## Votes (sans valeurs inventées)

Le site lit les votes uniquement depuis `votes_live` :
- `round_id, contestant_id, votes_count, last_updated`

Si aucune donnée n'existe, les valeurs restent à `0` / vide.

### Option A — manuel
Tu mets à jour `votes_live` à la main.

### Option B — Google Form (recommandé)
1. Formulaire Google pour collecter les votes.
2. Réponses liées à un Google Sheet.
3. Agréger les réponses vers `votes_live` (Apps Script ou formule/pivot).
4. Le site se rafraîchit automatiquement.

## Notes

- Le fallback local sert seulement de démo visuelle (pas de faux classements/statuts/votes).
- Le tableau Rankings n'affiche plus de `#5 · score` : uniquement les rangs par round.

