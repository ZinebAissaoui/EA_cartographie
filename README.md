## 1. [CYB x EA - Rapport Global - VF](https://lookerstudio.google.com/u/0/reporting/0fd3451b-1665-4d47-9d63-e9ea26fd15df/page/p_douhpnuysd/edit)
[CYB x EA - Rapport Global - VF](https://lookerstudio.google.com/u/0/reporting/0fd3451b-1665-4d47-9d63-e9ea26fd15df/page/p_xruw101tud/edit)

| # | Nom | Connecteur | Responsable |
|---|-----|------------|-------------|
| 1 | GSC - EA - Site | Search Console |  EF Cybercité |
| 2 | Espace Atypique - Glossaire - Feuille 1 | Google Sheets |  EF Cybercité | 
| 3 | Espaces Atypiques - Data - Facebook - post data | Google Sheets |  On n'a pas accès en modification |
| 4 | ea_matomo_pages_2 | BigQuery | Maxime |
| 5 | Espaces Atypiques Portail National & Agences - GA4 | Google Analytics |  EF Cybercité |
| 6 | ea_matomo_country | BigQuery | Maxime |
| 7 | Espaces Atypiques - Data - TikTok - Global data | Google Sheets | On n'a pas accès en modification |
| 8 | ea_matomo_region | BigQuery | Maxime |
| 9 | Espaces Atypiques - Data - Instagram - Post data organique | Google Sheets | analyse Cybercite |
| 10 | GSC - EA_Url | Search Console |  EF Cybercité | 
| 11 | ea_matomo_device | BigQuery | Maxime |
| 12 | GSC - EA_Discover | Search Console |  EF Cybercité | 
| 13 | ea_total_sessions_vs_objectif_table | BigQuery | Maxime |
| 14 | Espace Atypique_DATA_Pinterest - Pinterest_ok | Google Sheets | EF Cybercité |
| 15 | Espaces Atypiques - Data - Instagram - Profile impressions | Google Sheets | Analyste Cybercité |
| 16 | Espace Atypique Supermetrics_Linkedin - Data content_Linkedin | Google Sheets | Analyste Cybercité  |
| 17 | ea_matomo_country_maj | Google Sheets | Maxime |
| 18 | Espace Atypique_DATA_Pinterest - pinterest_top_pins | Google Sheets | Analyste Cybercité |
| 19  | ea_matomo_conversionperchannel_table | BigQuery | Maxime |
| 20 | Espace Atypique_DATA_Pinterest - owned_pins | Google Sheets | EF Cybercité |
| 21 | Espaces Atypiques - Data - TikTok - Video Data | Google Sheets | |
| 22 | ea_matomo_pages | BigQuery | |
| 23| Espace Atypiques - GSC - Merge - Web - Discover - Feuille 1 | Google Sheets | |
| 24 | Espaces Atypiques - Data - Facebook - Page - Data | Google Sheets | |
| 25 | ea_matomo_channel | BigQuery | |
| 26 | Espaces Atypiques - Data - Instagram - Profil data | Google Sheets | |
| 27 | ea_matomo_temps_moyen | BigQuery | |

---

## Détail des sources

### ea_matomo_pages_2
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_pages_2`
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Source Google Sheets** : https://docs.google.com/spreadsheets/d/17TPGEv18MLKy82zIrWrVz_rZZMPZ8Pab_Xnaf5LSvgA/edit?gid=630014299#gid=630014299
  - **Plage lue** : `page_view!A2:D`
  - **Format source** : Google Sheets
- **Schéma BQ** : date (DATE), entrances (INTEGER), page_view (INTEGER), entry_bounces (INTEGER)
- **Créée le** : 7 août 2025

---

### ea_matomo_country_maj
- **Connecteur Looker Studio** : Google Sheets
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_country_maj`
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Google Sheet** : EspaceAtypiques - Pays et régions — page `country` — https://docs.google.com/spreadsheets/d/1p6BS3vdq4e48n6uPc0wVAsg5_TqtDxg1daxlxQpRxe4/edit?gid=0#gid=0
  - **Plage lue** : `country!A2:D`
  - **Format source** : Google Sheets
  - **Sous-source** : Supermetrics → Google Sheets (EspaceAtypiques - Pays et régions) - Sheet country
    - **Connecteur** : Matomo (MATO)
    - **Site** : espaces-atypiques.com
    - **Type de rapport** : visitor_locations
    - **Métriques** : visits, conversions
    - **Dimensions** : date, country
    - **Période** : last14days
    - **MAJ** : chaque jour à 7AM (trigger automatique)
- **Responsable** : Maxime
- **Créée le** : 6 août 2025

---

### ea_matomo_region
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_region`
- **Responsable** : Maxime
- **Schéma BQ** : date (DATE), region (STRING), visits (INTEGER), conversions (INTEGER)

---

### Espaces Atypiques - Data - Facebook
- **Connecteur Looker Studio** : Google Sheets
- **Note** : On n'a pas accès en modification
- **Google Sheet** : https://docs.google.com/spreadsheets/d/1_q_s0yfdKM4hVuOTlXIOloWEHb866zm-x1lPpM458Pw
- **Compte Supermetrics** : Espaces Atypiques (ID : 169063903273561), Page ID : 106608657359396

#### Page — post data
- **Lien** : https://docs.google.com/spreadsheets/d/1_q_s0yfdKM4hVuOTlXIOloWEHb866zm-x1lPpM458Pw/edit?gid=0#gid=0
- **Plage de sortie** : `post data!A1:X380`
- **Sous-source** : Supermetrics Facebook (FB)
  - **Période** : last365days
  - **Métriques** : page_impressions_organic, post_impressions_organic_unique, page_impressions_paid_unique, page_impressions_unique, post_reactions_total, page_video_views_organic, post_link_clicks, post_shares, post_likes, post_comments, post_reactions (wow, like, love, haha, sorry, anger, pride, thankful), page_impressions
  - **Dimensions** : Date, post_type, post_caption, post_linkto, post_message
  - **MAJ** : trigger automatique tous les jours à 9AM ✓
- **Créée le** : 15 juillet 2025

#### Page — Page - Data
- **Lien** : https://docs.google.com/spreadsheets/d/1_q_s0yfdKM4hVuOTlXIOloWEHb866zm-x1lPpM458Pw/edit?gid=888957527#gid=888957527
- **Plage de sortie** : `Page - Data!A1:K742`
- **Sous-source** : Supermetrics Facebook (FB)
  - **Période** : last3days
  - **Métriques** : page_followers, page_fans, page_fan_adds, page_fan_removes, NetFanGrowth, page_impressions, page_impressions_unique, post_link_clicks, page_other_clicks, page_video_views
  - **Dimensions** : Date
  - **Option** : MERGE_RESULTS
  - **MAJ** : trigger automatique — **⚠ Erreur** : You do not have access to get data from page ID 169063903273561 — dernière tentative : 2026-04-10 09:38:39
- **Créée le** : 23 mai 2025

---

### Espaces Atypiques - Data - TikTok
- **Connecteur Looker Studio** : Google Sheets
- **Note** : On n'a pas accès en modification
- **Google Sheet** : https://docs.google.com/spreadsheets/d/15tAm1BB5QubklIy7MzWMQpcHLFT0gMBZOeXMsD8vfBE
- **Compte Supermetrics** : espaces_atypiques (TIKBA)

#### Page — Global data
- **Lien** : https://docs.google.com/spreadsheets/d/15tAm1BB5QubklIy7MzWMQpcHLFT0gMBZOeXMsD8vfBE/edit?gid=330172991#gid=330172991
- **Plage de sortie** : `Global data!A1:L8791`
- **Sous-source** : Supermetrics TikTok Business (TIKBA)
  - **Type de rapport** : profile
  - **Période** : last59days
  - **Métriques** : video_views, profile_views, total_engagement, likes, comments, shares, new_followers, current_followers
  - **Dimensions** : date, username, display_name, profile_image_url
  - **MAJ** : trigger automatique tous les jours à 6AM ✓ 
- **Créée le** : 23 mai 2025

#### Page — Video Data
- **Lien** : https://docs.google.com/spreadsheets/d/15tAm1BB5QubklIy7MzWMQpcHLFT0gMBZOeXMsD8vfBE/edit?gid=1718529702#gid=1718529702
- **Plage de sortie** : `Video Data!A1:R25`
- **Sous-source** : Supermetrics TikTok Business (TIKBA)
  - **Type de rapport** : videos
  - **Métriques** : videos__video_views, videos__likes, videos__comments, videos__shares, videos__reach, videos__video_duration_sec, videos__video_duration_min, videos__video_completion_rate, videos__total_time_watched_sec, videos__total_time_watched_min, videos__total_time_watched_h, videos__average_view_time
  - **Dimensions** : videos__video_id, videos__caption, videos__create_date, videos__thumbnail_url, videos__share_url, videos__embed_url
  - **Tri** : videos__create_date — limite 10 000 lignes, offset 10
  - **MAJ** : trigger automatique tous les jours à 6AM ✓ 
- **Créée le** : 23 mai 2025

---

### Espaces Atypiques - Data - Instagram
- **Responsable** : Analyste Cybercité
- **Google Sheet** : https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A
- **⚠ Erreur MAJ (toutes les pages)** : `gga.cybercite@gmail.com` doit se reconnecter à Instagram Insights (compte 107200137300248)

#### Page — Post data organique
- **Connecteur Looker Studio** : Google Sheets — https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A/edit?gid=12119620#gid=12119620
- **Plage de sortie** : `Post data organique!A1:J229`
- **Sous-source** : Supermetrics Instagram Insights (IGI)
  - **Compte** : Espaces Atypiques (ID : 17841401046378618), Instagram ID : 107200137300248
  - **Type de rapport** : media
  - **Période** : thisyear
  - **Métriques** : interactions, media_like_count, media_comments_count, media_shares, media_saved, media_reach, media_impressions
  - **Dimensions** : date, media_caption, media_product_type
  - **Dernière donnée valide** : 2026-01-07
- **Créée le** : 29 juillet 2025

#### Page — Profile impressions
- **Connecteur Looker Studio** : Google Sheets — https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A/edit?gid=209091544#gid=209091544
- **Plage de sortie** : `Profile impressions!A1:L454`
- **Sous-source** : Supermetrics Instagram Insights (IGI)
  - **Compte** : Espaces Atypiques (ID : 17841401046378618), Instagram ID : 107200137300248
  - **Type de rapport** : — (niveau profil + media)
  - **Période** : last365days
  - **Métriques** : impressions, reach, interactions, media_comments_count, media_like_count, media_impressions, media_reach, media_saved, media_shares, media_profile_visits, media_follows
  - **Dimensions** : date
  - **Dernière tentative** : 2026-04-09 07:34:53
- **Créée le** : 29 juillet 2025

#### Page — Profil data
- **Responsable** : Analyste Cybercité
- **Connecteur Looker Studio** : Google Sheets — https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A/edit?gid=0#gid=0
- **Plage de sortie** : `Profil data!A1:D143`
- **Sous-source** : Supermetrics Instagram Insights (IGI)
  - **Compte** : Espaces Atypiques (ID : 17841401046378618), Instagram ID : 107200137300248
  - **Type de rapport** : profil
  - **Période** : yesterday
  - **Métriques** : followers_count, follows_count, media_count
  - **Dimensions** : date
  - **Option** : MERGE_RESULTS
  - **MAJ** : ⚠ Erreur —on doit se reconnecter à Instagram Insights — dernière tentative : 2026-04-10 07:20:30
- **Créée le** : 29 juillet 2025

---

### ea_matomo_device
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_device`
- **Responsable** : Maxime
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Plage lue** : `matomo_device!A2:F`
  - **Format source** : Google Sheets
  - **Google Sheet** : pas d'accès — https://docs.google.com/spreadsheets/d/1A3tQErcpB-HhQbjDwNsgP7cNiqpYBx6SJ8YOWECdz5s/edit?gid=1546544600#gid=1546544600
- **Schéma BQ** : date (DATE), device_type (STRING), visits (INTEGER), bounces (INTEGER), conversions (INTEGER), total_visit_lenght (INTEGER)
- **Créée le** : 30 mai 2025

---

### Espace Atypique_DATA_Pinterest
- **Google Sheet** : https://docs.google.com/spreadsheets/d/19suEgJnbHc98Snx3dB01vcBDxgJc7jkoHU9eVpqEDo8
- **Compte Supermetrics** : gcybercite — ESPACES ATYPIQUES DEVELOPPEMENT (ID : 549759793630)
- **⚠ Erreur MAJ (toutes les pages)** : Pinterest Organic failure — Forbidden

#### Page — Pinterest_ok
- **Responsable** : EF Cybercité
- **Lien** : https://docs.google.com/spreadsheets/d/19suEgJnbHc98Snx3dB01vcBDxgJc7jkoHU9eVpqEDo8/edit?gid=1584656261#gid=1584656261
- **Plage de sortie** : `Pinterest_ok!A1:F89`
- **Sous-source** : Supermetrics Pinterest Organic (PIO2)
  - **Type de rapport** : user_analytics
  - **Période** : last90days
  - **Métriques** : impressions, pin_clicks, saves, engagements, outbound_clicks
  - **Dimensions** : date
  - **Dernière tentative** : 2026-04-09 04:45:44
- **Créée le** : 18 septembre 2025

#### Page — pinterest_top_pins
- **Responsable** : Analyste Cybercité
- **Lien** : https://docs.google.com/spreadsheets/d/19suEgJnbHc98Snx3dB01vcBDxgJc7jkoHU9eVpqEDo8/edit?gid=1768182057#gid=1768182057
- **Plage de sortie** : `pinterest_top_pins!A1:F3803`
- **Sous-source** : Supermetrics Pinterest Organic (PIO2)
  - **Type de rapport** : pin
  - **Période** : last89days
  - **Métriques** : pin_analytics__impressions, pin_analytics__pin_clicks, pin_analytics__pin_click_rate, pin_analytics__saves
  - **Dimensions** : pin__url_media_image, pin__title
  - **Dernière tentative** : 2026-04-10 04:34:38
- **Créée le** : 6 août 2025

#### Page — owned_pins
- **Responsable** : EF Cybercité
- **Lien** : https://docs.google.com/spreadsheets/d/19suEgJnbHc98Snx3dB01vcBDxgJc7jkoHU9eVpqEDo8/edit?gid=1883049700#gid=1883049700
- **Plage de sortie** : `owned_pins!A1:H44242`
- **Sous-source** : Supermetrics Pinterest Organic (PIO2)
  - **Type de rapport** : pin
  - **Période** : last4days
  - **Métriques** : pin_analytics__impressions, pin_analytics__pin_clicks, pin_analytics__video_mrc_view, pin_analytics__outbound_clicks
  - **Dimensions** : pin_analytics__date, pin__url_media_image, pin__title, pin__pin_id
  - **Filtre** : pin_analytics__impressions > 0
  - **Dernière tentative** : 2026-04-10 04:34:41
- **Créée le** : 18 septembre 2025

---

### Espace Atypique Supermetrics_LinkedIn - Data content_LinkedIn
- **Connecteur Looker Studio** : Google Sheets
- **Google Sheet** : Espace Atypique Supermetrics_LinkedIn — page `Data content_Linkedin` — https://docs.google.com/spreadsheets/d/1fsfkpQWxCob-Hbly96c5kYvqHvgwGeHCYyrUKRO9LE0/edit?gid=0#gid=0
  - **Plage de sortie** : `Data content_Linkedin!A1:M466`
  - **Sous-source** : Supermetrics LinkedIn Pages
    - **Connecteur** : LinkedIn Pages (LIP)
    - **Compte** : Espaces Atypiques (ID : 9237041)
    - **Période** : lastyeartodate
    - **Métriques** : page_likes, page_impressions, page_clicks, page_comments, page_engagement_rate, page_engagements, page_shares, followers_gain_total, ugc_comments, ugc_likes, ugc_video_views, ugc_video_time_watched_for_views
    - **Dimensions** : date
    - **MAJ** : trigger automatique — Chaque jour 7AM✓
- **Créée le** : 5 août 2025

---

### ea_matomo_conversionperchannel_table
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_conversionperchannel_table`
- **Responsable** : Maxime
- **Type** : Table partitionnée par DAY sur le champ `date`
- **Write preference** : WRITE_TRUNCATE
- **Schéma** : date (DATE), event_name (STRING), event_count (INTEGER), total_conversions_objectif_optimiste (INTEGER), total_conversions_objectif_conservateur (INTEGER)
- **Alimentation** : Requête programmée BigQuery — `ea_conversion_per_channel`
  - **Ressource** : `6887e73d-0000-21f7-ab6b-d4f547e563ac`
  - **Utilisateur** : e-f@amc.cybercite.fr
  - **Planification** : tous les jours à 06:00 UTC
  - **⚠ Erreur** : requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr`
  - **Sources lues (UNION ALL)** :
    1. `ea_gravityform_clean_table` → formulaires (date, nom_formulaire, nombre_formulaire)
    2. `ea_matomo_channel_maj` → click_mail_matomo (SUM click_mail)
    3. `ea_matomo_channel_maj` → click_tel_matomo (SUM click_tel)
    4. `ea_objectifs_maj` → objectifs de conversions (total_conversions_objectif_optimiste, total_conversions_objectif_conservateur)

---

### GSC - EA_Discover
- **Connecteur Looker Studio** : Search Console
- **Responsable** : EF Cybercité
- **Site** : https://www.espaces-atypiques.com/
- **Table** : URL Impression
- **Search type** : Discover

---

---

### Espace Atypiques - GSC - Merge - Web - Discover - Feuille 1
- **Connecteur Looker Studio** : Google Sheets
- **Responsable** : EF Cybercité (e-f@amc.cybercite.fr)
- **Google Sheet** : https://docs.google.com/spreadsheets/d/1Ubb1yL_Po9aP3P_mMakSU7gtY2vP4gdBwGN6s2Om5qQ/edit?gid=0#gid=0
  - **Plage de sortie** : `Feuille 1!A1:D1669`
  - **Sous-source** : Supermetrics Google Search Console (GW)
    - **Site** : https://www.espaces-atypiques.com/
    - **Période** : last30days
    - **Métriques** : impressions, clicks
    - **Dimensions** : Date, searchType
    - **Option** : COMBINE_RESULTS
    - **MAJ** : trigger automatique ✓ — dernière MAJ : 2026-04-10 04:36:11
- **Créée le** : 5 août 2025

---

### ea_matomo_channel
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_channel_maj`
- **Créée le** : 12 août 2025
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Google Sheet** : https://docs.google.com/spreadsheets/d/1pPsRk0p_CLsX73lavmAT2yT8nULckoYIq-MsJEQCCeM/edit?gid=17995086#gid=17995086
  - **Page** : `Acquisition`
  - **Format source** : Google Sheets
  - **Sous-source** : App Script → Matomo API
    - **Site** : espacesatypiques.matomo.cloud (idSite=1)
    - **Méthode Matomo** : `Referrers.getReferrerType`
    - **Objectifs suivis** : goals 1, 2, 3, 13
    - **Granularité** : jour (period=day)
    - **Import incrémental** : repart de la dernière date importée (col A), sinon depuis 2024-01-01
    - **Triggers** :
      - `ImportMatomoData` — tous les jours à 6h00
      - `checkSumAndSendEmail` — tous les jours à 8h00 (alerte si somme colonnes N+Q contient une décimale → email à cedric@cybercite.fr, eporhial@cybercite.fr)
- **Schéma BQ** : date (DATE), channel (STRING), unique_visitors (INTEGER), visits (INTEGER), actions (INTEGER), utilisateurs (INTEGER), max_actions (INTEGER), temps_total_secondes (INTEGER), rebonds (INTEGER), visits_avec_conversions (INTEGER), form_vente (INTEGER), visits_avec_conversions_form_vente (INTEGER), form_vente_revenue (INTEGER), click_mail (INTEGER), visits_avec_conversions_click_mail (INTEGER), click_mail_revenue (INTEGER), click_tel (INTEGER), visits_avec_conversions_click_tel (INTEGER), click_tel_revenue (INTEGER)

---

### ea_matomo_pages
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_pages`
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Google Sheet** : pas d'accès — https://docs.google.com/spreadsheets/d/1A3tQErcpB-HhQbjDwNsgP7cNiqpYBx6SJ8YOWECdz5s/edit?gid=1804781316#gid=1804781316
  - **Plage lue** : à compléter après accès
  - **Format source** : Google Sheets
- **Schéma BQ** : date (DATE), page (STRING), entrances (INTEGER), page_view (INTEGER), entry_bounces (INTEGER)
- **Responsable** : à compléter après accès

---

### ea_matomo_temps_moyen
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_temps_moyen`
- **Responsable** : Maxime
- **Créée le** : 7 août 2025
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Google Sheet** : pas d'accès — https://docs.google.com/spreadsheets/d/17TPGEv18MLKy82zIrWrVz_rZZMPZ8Pab_Xnaf5LSvgA/edit?gid=2121330493#gid=2121330493
  - **Plage lue** : à compléter après accès
  - **Format source** : Google Sheets
- **Schéma BQ** : date (DATE), total_visit_lenght (INTEGER), visits (INTEGER)

---

### ea_total_sessions_vs_objectif_table
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_total_sessions_vs_objectif_table`
- **Responsable** : Maxime
- **Type** : Table partitionnée par DAY sur le champ `date` (partitions sans expiration)
- **Write preference** : WRITE_TRUNCATE
- **Dernière modification** : 31 mars 2026
- **Créée le** : 28 mai 2025
- **Alimentation** : Requête programmée BigQuery — `ea_mega_table`
  - **Lien** : https://console.cloud.google.com/bigquery/scheduled-queries/locations/europe/configs/688a0091-0000-2281-bb15-d43a2cc28207/details?hl=fr&project=eng-ridge-440808-e7
  - **Utilisateur** : e-f@amc.cybercite.fr
  - **Planification** : tous les jours à 06:00 UTC
  - **⚠ Erreur** : requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr`
  - **Colonnes produites** : date, canaux, detail_source, visits, conversions, sessions_objectif_optimiste, sessions_objectif_conservateur, conversions_objectif_optimiste, conversions_objectif_conservateur, total_sessions_objectif_*, total_conversions_objectif_*, total_budget_2025_previsionnel_hors_honoraires, total_honoraires_2025_previsionnel, total_depenses_reelles_hors_honoraires, budget_2025_previsionnel_hors_honoraires, depenses_reelles_hors_honoraires, honoraires_2025_previsionnel
  - **Classification des canaux** (via REGEXP sur source_medium / campaign / channel / campagne) :
    - `Branding` : filrouge2024, teads, smile
    - `SEO` : organic, duckduckgo, ecosia, qwant, mybusiness
    - `SEA (bing cpc, google cpc)` : cpc, dsa_, googlecpc, bingcpc
    - `Réseaux sociaux (organique + paid)` : fb, ig, instagram, facebook, pinterest, linkedin, tiktok, social
    - `Alerte Email` : mail
    - `Direct` : direct
    - `Trafic LLM` : chatgpt, openai, gemini, bard, claude, copilot, gpt, mistral, perplexity, etc.
    - `Referral` : referral, sites
    - `Autres` / `source_inconnue` : reste
  - **Sources lues (6 sources distinctes, 12 blocs UNION ALL)** :

    | Table source | Canaux produits | Métriques alimentées |
    |---|---|---|
    | `ea_gravityform_clean_table` — *voir [Sous-source](#sous-source--ea_gravityform_clean_table)* | Classification REGEXP source_medium/campaign | conversions (formulaires) |
    | `ea_matomo_channel_maj` — *voir [ea_matomo_channel](#ea_matomo_channel)* | SEO / Referral / Direct / Trafic LLM / Autres | visits, conversions (click_tel + click_mail) |
    | `ea_matomo_social_network` — *voir [section](#ea_matomo_social_network)* | Réseaux sociaux (organique + paid) | visits, conversions (click_tel + click_mail) |
    | `ea_matomo_campaigns_maj` — *voir [section](#ea_matomo_campaigns_maj)* | Classification REGEXP campagne | visits, conversions (click_tel + click_mail) |
    | `ea_objectifs_maj` — *voir [section](#ea_objectifs_maj)* | SEA, SEO, Réseaux sociaux, Branding, Total | sessions_objectif_optimiste/conservateur, conversions_objectif, totaux |
    | `ea_budget_cout_maj` — *voir [section](#ea_budget_cout_maj)* | Total + SEA / SEO / RS / Branding | budget_previsionnel, depenses_reelles, honoraires par canal |

#### Sous-source — ea_gravityform_clean_table
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_gravityform_clean_table`
- **Type** : Table native, WRITE_TRUNCATE
- **Alimentation** : Requête programmée BigQuery — `ea_gravity_form_clean`
  - **Utilisateur** : e-f@amc.cybercite.fr
  - **Planification** : tous les jours à 04:00 UTC
  - **⚠ Erreur** : corriger les credentials de `e-f@amc.cybercite.fr`
  - **Source lue** : `sources_dashboard.ea_matomo_gravity_form_all`


##### Sous-sous-source — ea_matomo_gravity_form_all
- **Table BQ** : `sources_dashboard.ea_matomo_gravity_form_all`
- **Alimentation** : Requête programmée `gravity_form_all` — tous les jours à 03:00 UTC (INSERT incrémental dédupliqué depuis `ea_gravity_form_maj`)
- **⚠ Erreur** : corriger les credentials de `e-f@amc.cybercite.fr` (config `68946b32-0000-2cab-bb8b-94eb2c080ffa`)
- **Schéma BQ** : id_formulaire (STRING), nom_formulaire (STRING), utm_source (STRING), utm_medium (STRING), utm_campagne (STRING), titre (STRING), url (STRING), code_postal (STRING), agence (STRING), auteur (STRING), date_entree (DATE)
- **Source lue** : `sources_dashboard.ea_gravity_form_maj`

###### Source — ea_gravity_form_maj
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_gravity_form_maj`
- **Créée le** : 6 août 2025
- **Alimentation** : Table externe BigQuery connectée à Google Sheets
  - **Google Sheet** : pas d'accès — https://docs.google.com/spreadsheets/d/1SDOYRuvII6qTkWv06Ld09cFNzlEGO5jTfAAAO_cRiJc/edit?gid=0#gid=0
- **Schéma BQ** : id_formulaire (STRING), nom_formulaire (STRING), utm_source (STRING), utm_medium (STRING), utm_campagne (STRING), titre (STRING), url (STRING), code_postal (STRING), agence (STRING), auteur (STRING), date_entree (DATE)

---

### ea_objectifs_maj
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_objectifs_maj`
- **Créée le** : 28 juillet 2025
- **Alimentation** : Table externe BQ → Google Sheets
  - **Google Sheet** : https://docs.google.com/spreadsheets/d/1C2M16btLDgLgVfN12wsoc8njDkZZh49OB-tlyJEVlrQ/edit?gid=911967270#gid=911967270
  - **Plage** : `objectifs_optimistes_conservateur!A2:S13`
  - **Note** : ⚠ Saisie manuelle probable — à confirmer avec Espace Atypique
- **Schéma BQ** : date (DATE), sessions_objectif_conservateur (INTEGER), conversions_objectif_conservateur (INTEGER), sessions_objectif_optimiste (INTEGER), conversions_objectif_optimiste (INTEGER), seo_sessions_objectif_conservateur (INTEGER), seo_conversions_objectif_conservateur (INTEGER), seo_sessions_objectif_optimiste (INTEGER), seo_conversions_objectif_optimiste (INTEGER), sea_sessions_objectif_conservateur (INTEGER), sea_conversions_objectif_conservateur (INTEGER), sea_sessions_objectif_optimiste_hors_demand_gen (INTEGER), sea_conversions_objectif_optimiste_hors_demand_gen (INTEGER), rs_sessions_objectif_conservateur (INTEGER), rs_conversions_objectif_conservateur (INTEGER), rs_sessions_objectif_optimiste (INTEGER), rs_conversions_objectif_optimiste (INTEGER), branding_sessions_objectif_conservateur (INTEGER), branding_sessions_objectif_optimiste (INTEGER)

---

### ea_budget_cout_maj
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_budget_cout_maj`
- **Créée le** : 28 juillet 2025
- **Alimentation** : Table externe BQ → même Google Sheet que `ea_objectifs_maj`, page différente
  - **Google Sheet** : https://docs.google.com/spreadsheets/d/1C2M16btLDgLgVfN12wsoc8njDkZZh49OB-tlyJEVlrQ/edit?gid=1591855827#gid=1591855827
  - **Plage** : `budget_cout_source_lookerstudio!A2:O13`
  - **Note** : ⚠ Probable saisie manuelle EA — à confirmer avec Espace Atypique
- **Schéma BQ** : date (DATE), total_budget_2025_previsionnel_hors_honoraires (INTEGER), total_honoraires_2025_previsionnel (INTEGER), total_depenses_reelles_hors_honoraires (INTEGER), seo_total_budget_2025_previsionnel_hors_honoraires (INTEGER), seo_total_honoraires_2025_previsionnel (INTEGER), seo_total_depenses_reelles_hors_honoraires (INTEGER), sea_total_budget_2025_previsionnel_hors_honoraires_hors_demand_gen (INTEGER), sea_total_honoraires_2025_previsionnel (INTEGER), sea_total_depenses_reelles_hors_honoraires_hors_demand_gen (INTEGER), rs_total_budget_2025_previsionnel_hors_honoraires (INTEGER), rs_total_honoraires_2025_previsionnel (INTEGER), rs_total_depenses_reelles_hors_honoraires (INTEGER), branding_total_budget_2025_previsionnel_hors_honoraires (INTEGER), branding_total_depenses_reelles_hors_honoraires (INTEGER)

---

### ea_matomo_social_network
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_social_network`
- **Alimentation** : Table externe BQ → Google Sheets
  - **Google Sheet** : https://docs.google.com/spreadsheets/d/1r3gdxxze-kerXjnFgcA1ldWn3MTG4zlcQNTQzfxlIP4/edit?gid=319599365#gid=319599365
  - **Plage** : `Acquisition-campagnemedia!A2:P`
  - **App Script** : import Matomo `Referrers.getSocials` (goals 2 & 3), période 2024-01-01 → fin année en cours, écrasement total à chaque run
- **Schéma BQ** : date (DATE), social_network (STRING), unique_visitors (INTEGER), visits (INTEGER), actions (INTEGER), utilisateurs (INTEGER), max_actions (INTEGER), temps_total_secondes (INTEGER), rebonds (INTEGER), visits_avec_conversions (INTEGER), click_mail (INTEGER), click_mail_visit_avec_conv (INTEGER), click_mail_revenue (INTEGER), click_tel (INTEGER), click_tel_visit_avec_conv (INTEGER), click_tel_revenue (INTEGER)

---

### ea_matomo_campaigns_maj
- **Table BQ** : `eng-ridge-440808-e7.sources_dashboard.ea_matomo_campaigns_maj`
- **Créée le** : 4 septembre 2025
- **Alimentation** : Table externe BQ → Google Sheets
  - **Google Sheet** : https://docs.google.com/spreadsheets/d/1yg13okOnsHh9AmZUSB_fUBW7ig1vtj0_UThs9ESEsvw/edit?gid=0#gid=0
  - **Plage** : `goal_3!A2:S`
  - **App Script** : import Matomo `MarketingCampaignsReporting.getSourceMedium` (goal 3), écrasement total à chaque run
- **Schéma BQ** : date (DATE), campagne (STRING), unique_visitors (INTEGER), visits (INTEGER), actions (INTEGER), utilisateurs (INTEGER), max_actions (INTEGER), temps_total_secondes (INTEGER), rebonds (INTEGER), visits_avec_conversions (INTEGER), form_vente (INTEGER), form_vente_visit_avec_conv (INTEGER), form_vente_revenue (INTEGER), click_mail (INTEGER), click_mail_visit_avec_conv (INTEGER), click_mail_revenue (INTEGER), click_tel (INTEGER), click_tel_visit_avec_conv (INTEGER), click_tel_revenue (INTEGER)

---

---

## 2. [Sept - 25 - EA-local-Global](https://lookerstudio.google.com/u/0/reporting/a2d405ee-2e75-4d17-a89e-2c0144ab3d69/page/p_2txnjavkwd/edit)

| # | Nom | Connecteur | Responsable |
|---|-----|------------|-------------|
| 1 | Espaces Atypiques Portail National & Agences - GA4 | Google Analytics | EF Cybercité |
| 2 | matomo_actions_table_NEW28102025 | BigQuery | EF Cybercité |
| 3 | ea_matomo_channel_maj | BigQuery | — *voir [Rapport 1](#ea_matomo_channel)* |
| 4 | matomo_duree_table_NEW28102025 | BigQuery |	EF Cybercité |
| 5 | Search Console https://www.espaces-atypiques.com/ | Search Console | EF Cybercité |
| 6 | matomo_conversions_annonces_NEW28102025 | BigQuery | 	EF Cybercité |
| 7 | ea_matomo_temps_moyen | BigQuery | — *voir [Rapport 1](#ea_matomo_temps_moyen)* |
| 8 | ea_total_sessions_vs_objectif_table | BigQuery | — *voir [Rapport 1](#ea_total_sessions_vs_objectif_table)* |
| 9 | matomo_global_local_table_NEW28102025 | BigQuery | 	EF Cybercité |
| 10 | EA Global - Matomo-Visites | Apps Script Add-on (Matomo) | Pauline alloin |

---

## Détail des sources — Sept-25-EA-local-Global



### matomo_actions_table_NEW28102025
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `matomo_extract.matomo_actions_table_NEW28102025`
- **Type** : Table native partitionnée
- **Schéma BQ** : date (DATE), agence (STRING), id_visit (STRING), actions (INTEGER)
- **Alimentation** : Requête programmée BigQuery — `matomo_local_actions_table`
  - **Ressource** : `6904c009-0000-2de9-9e81-14c14ef80d2c`
  - **⚠ Erreur** : corriger les credentials de `e-f@amc.cybercite.fr` (config `68946b32-0000-2cab-bb8b-94eb2c080ffa`)
  - **Planification** : tous les jours à 06:00 UTC
  - **Logique** : DELETE des 7 derniers jours puis INSERT depuis `matomo_global_local_table_NEW28102025` (MAX actions par date/agence/id_visit)
  - **Source lue** : `matomo_extract.matomo_global_local_table_NEW28102025` — *voir [section](#matomo_global_local_table_new28102025)*

---
### matomo_conversions_annonces_NEW28102025
- **Connecteur Looker Studio** : BigQuery
- **Table BQ active** : `matomo_extract.matomo_conversions_annonces_NEW28102025`
- **Table Reusable LS** : `matomo_conversions_annonces` (ancienne version, conservée comme source réutilisable)
- **Type** : Table native
- **Schéma BQ** : date (DATE), agence (STRING), dimension2 (STRING), dimension3 (STRING), dimension4 (STRING), click_tel (INTEGER), click_mail (INTEGER), form_vente (INTEGER), form_conseil_ami (INTEGER), form_rappel_succes (INTEGER), views (STRING)
- **Alimentation** : Requête programmée BigQuery — `matomo_conversions_annonces`
  - **Ressource** : `68b9974a-0000-2ae7-9b42-3c286d4e4ac2`
  - **⚠ Erreur** : corriger les credentials de `e-f@amc.cybercite.fr` (config `68946b32-0000-2cab-bb8b-94eb2c080ffa`)
  - **Planification** : tous les jours à 04:00 UTC
  - **Logique** : DELETE des 7 derniers jours puis INSERT dédupliqué depuis `eng-ridge-440808-e7.matomo_extract.matomo_visits_new`
  - **Événements trackés** (UNION ALL) : `click_tel`, `click_mail`, `form_vendre_succes`, `form_conseil_ami`, `form_rappel_succes`, visits/views
  - **Normalisation agence** : REGEXP_CONTAINS sur `dimension1` → slug agence standardisé (ex. `agence_aix-marseille-arles-alpilles`)

---

### matomo_duree_table_NEW28102025
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `matomo_extract.matomo_duree_table_NEW28102025`
- **Type** : Table native
- **Schéma BQ** : date (DATE), agence (STRING), referrerTypeName (STRING), id_visit (STRING), idVisitBounce (STRING), duree (INTEGER)
- **Alimentation** : Requête programmée BigQuery — `matomo_duree_table`
  - **Ressource** : `68e1139c-0000-2487-b29c-582429b58d00`
  - **Utilisateur** : e-f@amc.cybercite.fr
  - **Planification** : tous les jours à 06:00 UTC
  - **Logique** : DELETE des 7 derniers jours puis INSERT depuis `matomo_global_local_table_NEW28102025` (MAX visitDuration par date/agence/referrerTypeName/id_visit/idVisitBounce)
  - **Source lue** : `matomo_extract.matomo_global_local_table_NEW28102025` — *voir [section](#matomo_global_local_table_new28102025)*

---

### ea_matomo_channel_maj
→ Déjà documenté dans le Rapport 1 — *voir [ea_matomo_channel](#ea_matomo_channel)*

---

### ea_matomo_temps_moyen
→ Déjà documenté dans le Rapport 1 — *voir [ea_matomo_temps_moyen](#ea_matomo_temps_moyen)*

---

### ea_total_sessions_vs_objectif_table
→ Déjà documenté dans le Rapport 1 — *voir [ea_total_sessions_vs_objectif_table](#ea_total_sessions_vs_objectif_table)*

---

---

## 3. [EA-local-Paris Rive Droite](https://lookerstudio.google.com/u/0/reporting/75a0df69-d5c0-4992-b2fd-bb5bf464cc14/page/p_zewr8c5qzc/edit)

| # | Nom | Connecteur | Responsable |
|---|-----|------------|-------------|
| 1 | EA Global - Matomo-Visites | Apps Script Add-on |  Yann Raude-Lahore |
| 2 | matomo_vues_annonces | BigQuery | no edit access |
| 3 | EA-Local- Matomo Nego | Apps Script Add-on | Yann Raude-Lahore |
| 4 | EA-Perf-Annonces-01 - Feuille 1 | Google Sheets | Yann Raude-Lahore |
| 5 | EA-Local- Matomo Event | Apps Script Add-on | Yann Raude-Lahore |
| 6 | EA Local - Matomo Referal | Apps Script Add-on | Yann Raude-Lahore |
| 7 | EA-local- Matomo Campagne | Apps Script Add-on | Yann Raude-Lahore |
| 8 | EA-Perf-Annonces-02 - Feuille 1 | Google Sheets | Yann Raude-Lahore |
| 9 | Search Console https://www.espaces-atypiques.com/ | Search Console | no edit access  |
| 10 | EA-Local- Matomo Event (2e instance) | Apps Script Add-on | Yann Raude-Lahore |
| 11 | EA-local - Matomo - Peripheriques | Apps Script Add-on | Yann Raude-Lahore |
| 12 | EA local - Matomo - Visites | Apps Script Add-on | Yann Raude-Lahore |

---

## Détail des sources — EA-local-Paris Rive Droite

### EA Global - Matomo-Visites
→ Déjà documenté dans le Rapport 2 — *voir [section](#ea-global---matomo-visites)*

---

### matomo_vues_annonces
- **Connecteur Looker Studio** : BigQuery
- **Table BQ** : `matomo_extract.matomo_vues_annonces`
- **Type** : Table native partitionnée — Reusable dans LS
- **Schéma BQ** : date (DATE), dimension2 (STRING), dimension4 (STRING), visites (INTEGER), vues (INTEGER)
- **Alimentation** : Requête programmée BigQuery — `ea_matomo_vues_annonces`
  - **Ressource** : `690dd88f-0000-2f68-866d-14223bb5893a`
  - **Utilisateur** : e-f@amc.cybercite.fr — ⚠ mettre à jour les identifiants
  - **Planification** : tous les jours à 06:30 UTC
  - **Source lue** : `eng-ridge-440808-e7.matomo_extract.matomo_visits_new` (dédupliqué par idVisit)
  - **Logique** : DELETE des 7 derniers jours puis INSERT — COUNT DISTINCT idpageview (vues) et idVisit (visites) par dimension2/dimension4, via UNION ALL

---

### EA-Local- Matomo Nego
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA-Perf-Annonces-01 - Feuille 1
- **Connecteur Looker Studio** : Google Sheets
- **Google Sheet** : pas d'accès — URL manquante
- **Note** : ⚠ Demander l'accès et l'URL à l'équipe EA

---

### EA-Local- Matomo Event
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA Local - Matomo Referal
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA-local- Matomo Campagne
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA-Perf-Annonces-02 - Feuille 1
- **Connecteur Looker Studio** : Google Sheets
- **Google Sheet** : pas d'accès — URL manquante
- **Note** : ⚠ Demander l'accès et l'URL à l'équipe EA

---

### Search Console https://www.espaces-atypiques.com/
→ Déjà documenté dans le Rapport 2 — *voir [section](#search-console)*

---

### EA-Local- Matomo Event (2e instance)
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA-local - Matomo - Peripheriques
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---

### EA local - Matomo - Visites
- **Connecteur Looker Studio** : Apps Script Add-on
- À documenter

---


## Suivi des accès et informations manquantes

| Source | Lien | Accès/ Explication needed | Responsable| Statut |
|--------|------|:------------:|:-----------------:|--------|
| ea_matomo_pages_2 (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/17TPGEv18MLKy82zIrWrVz_rZZMPZ8Pab_Xnaf5LSvgA | Pas d'accès au Google Sheet source |  | En attente |
| Espace Atypique - Glossaire (Google Sheets) | don't have it | Pas d'accès au Google Sheet source | | En attente |
| Instagram - Post data organique (Supermetrics) | https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A | Refresh en erreur — nécessité de reconnecter instagram insights via Supermetric. Dernière donnée valide : 2026-01-07 | Analyste Cybercité | ⚠ Erreur |
| ea_matomo_pages (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/1A3tQErcpB-HhQbjDwNsgP7cNiqpYBx6SJ8YOWECdz5s/edit?gid=1804781316#gid=1804781316 | Pas d'accès au Google Sheet source | | En attente |
| ea_matomo_device (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/1A3tQErcpB-HhQbjDwNsgP7cNiqpYBx6SJ8YOWECdz5s | Pas d'accès au Google Sheet source | Maxime | En attente |
| Pinterest - Pinterest_ok (Supermetrics) | https://docs.google.com/spreadsheets/d/19suEgJnbHc98Snx3dB01vcBDxgJc7jkoHU9eVpqEDo8 | Refresh en erreur — Pinterest Organic Forbidden. Reconnecter le compte gcybercite dans Supermetrics | EF Cybercité | ⚠ Erreur |
| ea_total_sessions_vs_objectif_table (requête programmée ea_mega_table) | https://console.cloud.google.com/bigquery/scheduled-queries/locations/europe/configs/688a0091-0000-2281-bb15-d43a2cc28207/details?hl=fr&project=eng-ridge-440808-e7 | Requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr` | EF Cybercité | ⚠ Erreur |
| ea_matomo_conversionperchannel_table (requête programmée ea_conversion_per_channel) | — | Requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr` (config `6887e73d-0000-21f7-ab6b-d4f547e563ac`) | Maxime | ⚠ Erreur |
| ea_gravityform_clean_table (requête programmée ea_gravity_form_clean) | — | Requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr` | Maxime | ⚠ Erreur |
| ea_matomo_gravity_form_all (requête programmée gravity_form_all) | — | Requête ne fonctionne plus — corriger les credentials de `e-f@amc.cybercite.fr` (config `68946b32-0000-2cab-bb8b-94eb2c080ffa`) | Maxime | ⚠ Erreur |
| ea_budget_cout_maj (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/1C2M16btLDgLgVfN12wsoc8njDkZZh49OB-tlyJEVlrQ/edit?gid=1591855827#gid=1591855827 | Probable saisie manuelle EA (même GSheet que ea_objectifs_maj) — à confirmer avec Espace Atypique | | À clarifier |
| ea_objectifs_maj (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/1C2M16btLDgLgVfN12wsoc8njDkZZh49OB-tlyJEVlrQ/edit?gid=911967270#gid=911967270 | Probable saisie manuelle EA — à confirmer avec Espace Atypique | | À clarifier |
| ea_gravity_form_maj (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/1SDOYRuvII6qTkWv06Ld09cFNzlEGO5jTfAAAO_cRiJc/edit?gid=0#gid=0 | Pas d'accès au Google Sheet source | | En attente |
| Instagram - Profil data (Supermetrics) | https://docs.google.com/spreadsheets/d/1f9vZ22CeY3iNphK_HGQiATZAAadLqsfUVjHx4Ss4G4A/edit?gid=0#gid=0 | Refresh en erreur — gga.cybercite@gmail.com doit se reconnecter à Instagram Insights (compte 107200137300248) | Analyste Cybercité | ⚠ Erreur |
| Facebook - Page - Data (Supermetrics) | https://docs.google.com/spreadsheets/d/1_q_s0yfdKM4hVuOTlXIOloWEHb866zm-x1lPpM458Pw/edit?gid=888957527#gid=888957527 | Refresh en erreur — You do not have access to get data from page ID 169063903273561. Reconnecter l'accès Facebook dans Supermetrics | | ⚠ Erreur |
| ea_matomo_temps_moyen (Google Sheets sous-jacent) | https://docs.google.com/spreadsheets/d/17TPGEv18MLKy82zIrWrVz_rZZMPZ8Pab_Xnaf5LSvgA/edit?gid=2121330493#gid=2121330493 | Pas d'accès au Google Sheet source |  | En attente |
| EA-Perf-Annonces-01 - Feuille 1 | — | Pas d'accès + URL manquante — demander à l'équipe EA | | En attente |
| EA-Perf-Annonces-02 - Feuille 1 | — | Pas d'accès + URL manquante — demander à l'équipe EA | | En attente |
| matomo_vues_annonces (requête programmée ea_matomo_vues_annonces) | — | Mettre à jour les identifiants de e-f@amc.cybercite.fr | EF Cybercité | ⚠ Action requise |

