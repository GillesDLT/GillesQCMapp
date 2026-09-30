# QCM-gilles-app

Application de révision de QCM des matières de GM, en français, sans compte ni serveur obligatoire.

## Lancer l'application

Ouvre `index.html` avec Firefox ou Chromium (double-clic ou menu « Ouvrir avec »). La banque et les scores restent dans le stockage local du navigateur utilisé.

Si ton navigateur limite l'ouverture des fichiers locaux, lance plutôt un serveur local dans ce dossier :

```bash
cd ~/QCM-gilles-app
python3 -m http.server 8000
```

Puis ouvre <http://localhost:8000>.

## Fonctions

- Sélection de matière, choix du nombre de questions et filtres par thème.
- Option pour ne garder que les questions illustrées.
- Mélange des questions et des propositions.
- Correction immédiate après une réponse. Pour les questions à choix multiples, coche toutes les réponses puis clique sur « Vérifier ma sélection ».
- Explication, corrigé détaillé, score, temps, historique des résultats et reprise des erreurs.
- Ajout de questions, y compris une image (PNG/JPEG/WebP recommandé).
- Import/export de la banque en JSON.

## Banque initiale

159 questions d'Automatisme : 150 questions GA701 déjà présentes dans l'espace de travail (séance 1), 8 questions créées à partir des extraits de la séance 2 transmis dans la conversation, et 1 question associée à un chronogramme pédagogique créé pour l'application. Les matières Automatique et Ressources humaines sont configurées mais leurs banques sont encore vides.

Le filtre « uniquement les questions avec une image » fonctionne déjà avec la question du chronogramme. Tu peux aussi ajouter tes propres questions illustrées dans l'onglet « Banque de questions ».

## Format JSON (pour préparer une banque ailleurs)

Chaque question suit ce schéma :

```json
{
  "id": "rh-001",
  "subject": "rh",
  "type": "multiple",
  "category": "Recrutement",
  "prompt": "Énoncé de la question",
  "options": ["Proposition A", "Proposition B", "Proposition C"],
  "correct": [0, 2],
  "explanation": "Explication facultative",
  "image": null,
  "source": "Cours / chapitre / page"
}
```

`subject` vaut `automatisme`, `automatique` ou `rh`. `type` vaut `single` (choix unique) ou `multiple` (choix multiples). Dans `correct`, les indices commencent à 0. Pour une image ajoutée dans l'application, l'image est intégrée au JSON exporté.
