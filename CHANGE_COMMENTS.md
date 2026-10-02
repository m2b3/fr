# Résumé des modifications

## 2026-07-29 — Page et navigation d'enseignement

- **Problème :** Le site français ne comportait ni onglet « Enseignement » dans le menu principal ni page pour le cours d'automne 2026.
- **Cause fondamentale :** Aucune page d'enseignement ni entrée de navigation n'avait été configurée.
- **Solution :** Ajout de `teaching.qmd`, reprise en anglais du contenu de `Fall2026.md` dans la section Automne 2026 et ajout du lien dans `_quarto.yml`. Après la première version, suppression de la seconde ligne « Time and Location », identique à la première et héritée de la source.
- **Résultat :** Les visiteurs peuvent accéder aux informations concises du cours d'automne 2026 depuis la navigation principale du site français, avec l'horaire affiché une seule fois.
- **Fichiers modifiés :** `_quarto.yml`, `teaching.qmd` (version initiale : commit `985b5c2`; suppression du doublon pas encore validée).

## 2026-09-05 — Projection Equal Earth de la carte

- **Problème :** La carte des membres utilisait une disposition longitude/latitude non projetée qui exagérait visuellement la superficie des terres aux hautes latitudes.
- **Cause fondamentale :** La couche principale `World` ne précisait aucun SCR projeté pour l'affichage; `tmap` dessinait donc directement les coordonnées WGS 84 de la source.
- **Solution :** Définition du SCR principal sur Equal Earth (`EPSG:8857`); `tmap` reprojette ensemble les polygones du monde et les points des membres actuels et anciens.
- **Résultat :** La carte « D’où Venons-Nous? » conserve maintenant les superficies relatives tout en gardant les emplacements, couleurs, tailles et styles existants.
- **Fichiers modifiés :** `members.qmd` (modification pas encore validée dans Git).

## 2026-10-01 — CanViT news item link and logo

- **Problem:** The top News item about CanViT at NeurIPS 2026 had no link to the project page and no visual identifier.
- **Solution:** Linked "CanViT" to the project page `https://m2b3.github.io/CanViT/` (the lowercase `/canvit` path returns 404 because GitHub Pages paths are case-sensitive). Added the official CanViT wordmark (`images/canvit-wordmark.svg`, copied from `m2b3/CanViT` `site/assets/logos/`) at the end of the line, inline at `height=1.3em` so it matches the text line; the logo also links to the project page.
- **Result:** Visitors can jump to the CanViT project page from the home page; the logo fits within the news line.
- **Files Modified:** `index.qmd`, `images/canvit-wordmark.svg`, rendered `docs/` (commits `canvit`).
- **Iteration (2026-10-01):** On the live page the trailing logo rendered larger than the text and wrapped onto its own line. The logo now *replaces* the "CanViT" text link (still linking to the project page), styled `display: inline; height: 1em; width: auto; vertical-align: -0.1em` so it sits on the text baseline at text height. Files: `index.qmd`, rendered `docs/` (not yet committed).

## 2026-10-01 — CanViT link cue and manuscript links in News

- **Problem:** The CanViT wordmark did not look clickable, and several manuscript news items had no link to the paper, or linked only to the preprint after the paper was published.
- **Solution:** Gave the logo a hover/focus effect (brightens, lifts and gets an underline) and a tooltip, and added a "(project page ↗)" text link after it (`.canvit-logo-link`, `.canvit-cue` in `styles.css`). Linked the manuscripts using the URLs on the Output page: meaning maps → bioRxiv, auditory static distractor → arXiv, forward remapping → Journal of Vision DOI. Added the published Communications Biology and Brain Sciences links next to the existing LFP-variability and insula preprint links.
- **Result:** The CanViT link is visible on desktop and touch screens, and every news item about a manuscript now links to the correct version.
- **Files Modified:** `index.qmd`, `styles.css`, rendered `docs/` (not yet committed).
