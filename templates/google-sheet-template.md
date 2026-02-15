# Google Sheets template — Star KCA Academy

Créer un Google Sheet avec les onglets suivants.

## 1) contestants
`id,name,photo_url,country,bio,instagram,pronouns`

## 2) rounds
`round_id,round_name,start_date,end_date,description`

## 3) submissions
`round_id,contestant_id,song_title,group_song,bandlab_url,youtube_url,notes`

## 4) scores (optionnel pour ranking si judge_rankings official absent)
`round_id,contestant_id,pitch,vocal_quality,technique,rhythm,pronunciation,interpretation,harmonies,musicality,audio_mixing,attitude,total`

## 5) judge_rankings (recommandé pour contrôle total)
`round_id,judge_name,contestant_id,rank`

Pour le classement officiel, utiliser:
- `judge_name = official`

## 6) round_status
`round_id,contestant_id,status`

Valeurs status:
- safe
- nominee
- saved_judges
- saved_public
- eliminated

Si pas de ligne de statut, le site affiche `TBD`.

## 7) votes_live
`round_id,contestant_id,votes_count,last_updated`

Aucune valeur n'est inventée: si vide, le site montre 0 / pas de données.

---

## Exemple minimal (22 candidats)

| id | name |
|---|---|
| yza | Yza |
| hope | Hope |
| lea | Lea |
| megara | Megara |
| asli | Asli |
| chanel | Chanel |
| heaven | Heaven |
| manuee | Manuee |
| hwa_young | Hwa Young |
| mimi | Mimi |
| eria | Eria |
| panida | Panida |
| kelsy | Kelsy |
| suhaa | Suhaa |
| johi | Johi |
| sun | Sun |
| kora | Kora |
| brahmini | Brahmini |
| katie | Katie |
| donghyun | Donghyun |
| lizy | Lizy |
| kyo | Kyo |

