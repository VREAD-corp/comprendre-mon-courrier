# Courrier clair — comprendre un courrier administratif français

Site : https://outils.vread.fr/comprendre-mon-courrier/ (FR) · https://outils.vread.fr/comprendre-mon-courrier/en/ (EN)

21 guides gratuits, en français et en anglais simples, sur les courriers les plus fréquents (CAF, impôts, ANEF / titre de
séjour, CPAM, URSSAF, amendes) : ce que c'est, délais à vérifier, quoi faire, liens officiels. Un produit de READ FRANCE SAS.

**Information générale uniquement, pas de conseil juridique** (voir `content/avertissement.html` : article 54 de la loi
n° 71-1130 et réponse du ministère de la Justice du 8 avril 2025 à la question écrite n° 3177). Aucun envoi de courrier,
aucune donnée personnelle collectée. Non affilié à une administration.

Téléchargements gratuits (GitHub Releases) : `checklist-courrier-administratif-fr.pdf`, `checklist-official-letter-en.pdf`

Version payante (Courrier clair+, 4,90 €/mois) : **pas encore disponible**, aucun paiement possible.

## Mesure d'audience (depuis le 2026-10-13)

`assets/mesure.js` (compteur d'audience anonyme, `v:2`, robots / navigateurs automatisés / `octave_notrack=1` comptés à
part) et `assets/cro.js` (compteurs agrégés de comportement) sont copiés **à l'identique** depuis
`VREAD-corp/octave-checkout` (`gas/web/`, ne jamais modifier les copies). Chargés sur chaque page par `build.py`
(`data-site="comprendre-mon-courrier"`, avec empreinte `?v=`), ils envoient l'action `track` au backend France `octave-pay-gas`, qui
accepte ce site. Clics comptés : PDF gratuits (`free_download`) et page « version payante » (`cta_click`). Aucun cookie,
aucun identifiant, rien sous Do Not Track / GPC ; nos tests ajoutent `?octave_notrack=1`. Détails :
`content/confidentialite.html`. Après une mise à jour du snippet maître : recopier les deux fichiers puis
`node tests/cro.check.mjs assets/cro.js`.

## Structure

- `content/guides/*.html`, `content/en/guides/*.html` — guides FR / EN (vérifiés le 2026-10-11, sources dans chaque page)
- `pdf/` — sources HTML des check-lists ; `build.py` — générateur statique sans dépendance
- `tests/test_site.py` — vérifications ; `scripts/make_pdf.mjs` — rendu PDF ; `scripts/check_live.mjs` — contrôle en ligne

```sh
python3 build.py && python3 tests/test_site.py
npm i && node scripts/make_pdf.mjs
```

Contenus : CC BY 4.0. Code : MIT. Signaler une erreur : onglet Issues (tickets publics : **aucune donnée personnelle**,
ne décrivez pas votre situation).
