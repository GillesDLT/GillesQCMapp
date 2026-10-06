# QCM-gilles-app

Application de révision locale, en français, sans compte ni serveur obligatoire.

## Lancer l'application

Ouvre `index.html` avec Firefox ou Chromium. Si l’ouverture locale est limitée, lance depuis ce dossier :

```bash
python3 -m http.server 8000
```

Puis ouvre <http://localhost:8000>.

## Banque actuelle

45 questions d’entraînement à choix multiples pour **GA701 — séance 3 : détecteurs de position**. Les énoncés sont présentés dans un style QCM d’examen, sans thèmes ni rubriques par question. Une ou plusieurs bonnes réponses peuvent être attendues; chaque réponse est suivie d’une correction explicative.

## Fonctions

- Sélection de matière et du nombre de questions.
- Mélange des questions et propositions, correction immédiate et explications.
- Corrigé détaillé, score, temps, historique et reprise des erreurs.
- Ajout de questions, import/export JSON et possibilité de vider la banque.

La banque et les scores sont conservés localement dans le navigateur.
