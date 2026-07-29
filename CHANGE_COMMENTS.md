# Résumé des modifications

## 2026-07-29 — Page et navigation d'enseignement

- **Problème :** Le site français ne comportait ni onglet « Enseignement » dans le menu principal ni page pour le cours d'automne 2026.
- **Cause fondamentale :** Aucune page d'enseignement ni entrée de navigation n'avait été configurée.
- **Solution :** Ajout de `teaching.qmd`, reprise en anglais du contenu de `Fall2026.md` dans la section Automne 2026 et ajout du lien dans `_quarto.yml`. Après la première version, suppression de la seconde ligne « Time and Location », identique à la première et héritée de la source.
- **Résultat :** Les visiteurs peuvent accéder aux informations concises du cours d'automne 2026 depuis la navigation principale du site français, avec l'horaire affiché une seule fois.
- **Fichiers modifiés :** `_quarto.yml`, `teaching.qmd` (version initiale : commit `985b5c2`; suppression du doublon pas encore validée).
