# Courrier clair — comprendre un courrier administratif français

Site : https://courrier.jalonel.com/ (FR) · https://courrier.jalonel.com/en/ (EN)

2026-10-16: moved to https://courrier.jalonel.com/ (brand Jalonel, a brand of READ FRANCE SAS). Ancienne adresse
https://outils.vread.fr/comprendre-mon-courrier/ : redirection 301 de GitHub Pages vers la même page sur le nouveau domaine.

21 guides gratuits, en français et en anglais simples, sur les courriers les plus fréquents (CAF, impôts, ANEF / titre de
séjour, CPAM, URSSAF, amendes) : ce que c'est, délais à vérifier, quoi faire, liens officiels. Une marque Jalonel (Jalonel est une marque de READ FRANCE SAS).

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
accepte ce site (`mesure.js` déduit l'identifiant `comprendre-mon-courrier` de l'hôte `courrier.jalonel.com` ; `cro.js` :
`data-hosts="courrier.jalonel.com outils.vread.fr"`). Clics comptés : PDF gratuits (`free_download`) et page « version payante » (`cta_click`). Aucun cookie,
aucun identifiant, rien sous Do Not Track / GPC ; nos tests ajoutent `?octave_notrack=1`. Détails :
`content/confidentialite.html`. Après une mise à jour du snippet maître : recopier les deux fichiers puis
`node tests/cro.check.mjs assets/cro.js`.

## Structure

- `content/guides/*.html`, `content/en/guides/*.html` — guides FR / EN (vérifiés le 2026-10-11, sources dans chaque page)
- `pdf/` — sources HTML des check-lists ; `build.py` — générateur statique sans dépendance (site servi à la racine
  `/`, origine `https://courrier.jalonel.com` dans `site.json` ; écrit aussi `CNAME` et la clé IndexNow
  `5be19f56d46ca3d2553bee28ebfa8edd.txt` à la racine de `_site/`)
- `tests/test_site.py` — vérifications ; `scripts/make_pdf.mjs` — rendu PDF ; `scripts/check_live.mjs` — contrôle en ligne

```sh
python3 build.py && python3 tests/test_site.py
npm i && node scripts/make_pdf.mjs
```

Contenus : CC BY 4.0. Code : MIT. Signaler une erreur : onglet Issues (tickets publics : **aucune donnée personnelle**,
ne décrivez pas votre situation).
