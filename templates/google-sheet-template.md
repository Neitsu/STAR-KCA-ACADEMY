# Google Sheets template — Star KCA Academy / SIEL

Crée un Google Sheet avec les onglets suivants et **exactement** ces colonnes.

## 1) contestants
`id,name,photo_url,country,bio,instagram,pronouns`

### Exemple (22 candidats)
| id | name | photo_url | country | bio | instagram | pronouns |
|---|---|---|---|---|---|---|
| yza | Yza | assets/yza.jpg | TBD | Rising vocalist in Star KCA Academy. | @yza | she/her |
| hope | Hope | assets/hope.jpg | TBD | Rising vocalist in Star KCA Academy. | @hope | |
| lea | Lea | assets/lea.jpg | TBD | Rising vocalist in Star KCA Academy. | @lea | |
| megara | Megara | assets/megara.jpg | TBD | Rising vocalist in Star KCA Academy. | @megara | she/her |
| asli | Asli | assets/asli.jpg | TBD | Rising vocalist in Star KCA Academy. | @asli | |
| chanel | Chanel | assets/chanel.jpg | TBD | Rising vocalist in Star KCA Academy. | @chanel | |
| heaven | Heaven | assets/heaven.jpg | TBD | Rising vocalist in Star KCA Academy. | @heaven | she/her |
| manuee | Manuee | assets/manuee.jpg | TBD | Rising vocalist in Star KCA Academy. | @manuee | |
| hwa_young | Hwa Young | assets/hwa_young.jpg | TBD | Rising vocalist in Star KCA Academy. | @hwa_young | |
| mimi | Mimi | assets/mimi.jpg | TBD | Rising vocalist in Star KCA Academy. | @mimi | she/her |
| eria | Eria | assets/eria.jpg | TBD | Rising vocalist in Star KCA Academy. | @eria | |
| panida | Panida | assets/panida.jpg | TBD | Rising vocalist in Star KCA Academy. | @panida | |
| kelsy | Kelsy | assets/kelsy.jpg | TBD | Rising vocalist in Star KCA Academy. | @kelsy | she/her |
| suhaa | Suhaa | assets/suhaa.jpg | TBD | Rising vocalist in Star KCA Academy. | @suhaa | |
| johi | Johi | assets/johi.jpg | TBD | Rising vocalist in Star KCA Academy. | @johi | |
| sun | Sun | assets/sun.jpg | TBD | Rising vocalist in Star KCA Academy. | @sun | she/her |
| kora | Kora | assets/kora.jpg | TBD | Rising vocalist in Star KCA Academy. | @kora | |
| brahmini | Brahmini | assets/brahmini.jpg | TBD | Rising vocalist in Star KCA Academy. | @brahmini | |
| katie | Katie | assets/katie.jpg | TBD | Rising vocalist in Star KCA Academy. | @katie | she/her |
| donghyun | Donghyun | assets/donghyun.jpg | TBD | Rising vocalist in Star KCA Academy. | @donghyun | |
| lizy | Lizy | assets/lizy.jpg | TBD | Rising vocalist in Star KCA Academy. | @lizy | |
| kyo | Kyo | assets/kyo.jpg | TBD | Rising vocalist in Star KCA Academy. | @kyo | she/her |

## 2) rounds
`round_id,round_name,start_date,end_date,description`

## 3) submissions
`round_id,contestant_id,song_title,group_song,bandlab_url,youtube_url,notes`

## 4) scores
`round_id,contestant_id,pitch,vocal_quality,technique,rhythm,pronunciation,interpretation,harmonies,musicality,audio_mixing,attitude,total`

## 5) judge_rankings
`round_id,judge_name,contestant_id,rank`

## 6) round_status
`round_id,contestant_id,status`

Statuts possibles:
- safe
- nominee
- saved_judges
- saved_public
- eliminated

## 7) votes_live
`round_id,contestant_id,votes_count,last_updated`

Utilisation recommandée:
- Google Form / Apps Script pour agréger automatiquement
- ou mise à jour manuelle des `votes_count`

