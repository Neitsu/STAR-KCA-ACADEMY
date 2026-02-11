# Star KCA Academy / SIEL — Static Website (GitHub Pages)

Site statique (HTML/CSS/JS + Chart.js) pour gérer un concours vocal en ligne avec:
- contestants + profils
- rankings officiels et par juge
- scoring rubric /100
- performances
- votes live-ish (public/admin)
- admin soft mode

## 1) Déploiement ultra simple (GitHub Pages)

1. Push ce repo sur GitHub.
2. Va dans **Settings → Pages**.
3. Source: **Deploy from a branch**.
4. Branch: `main` (ou ta branche de prod), dossier `/root`.
5. Ouvre l'URL GitHub Pages après le déploiement.

> Aucun build requis. Le site fonctionne directement avec `index.html`.

## 2) Config Google Sheets

Dans `index.html`, modifie la constante:

```js
const CONFIG = {
  SHEET_ID: "PASTE_YOUR_GOOGLE_SHEET_ID",
  ADMIN_KEY: "kca-admin",
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

### Publication Google Sheets
- Crée un Google Sheet nommé `DATABASE`.
- Crée les onglets avec les noms exacts ci-dessus.
- Remplis les colonnes d'après `templates/google-sheet-template.md`.
- Fais **Share → Anyone with the link (Viewer)**.
- Le site utilise l'endpoint GViz en lecture seule.

## 3) Mode public/admin votes

- Public: valeurs arrondies de votes.
- Admin: valeurs exactes.

Activer admin:
- URL: `?adminKey=kca-admin`
- ou depuis `/admin`, bouton “Enable admin in this browser”.

> Soft protection seulement (suffisant pour un projet fan/statique).

## 4) Mise à jour des données

- Tu mets à jour ton Google Sheet.
- Le site recharge les votes toutes les 30 secondes.
- Les autres pages se mettent à jour au prochain chargement (ou navigation après refresh).

## 5) Si tu n'as pas encore de Sheet

Le site inclut des données de fallback (22 candidats + rounds + exemples), ce qui permet d'avoir une démo immédiate.

