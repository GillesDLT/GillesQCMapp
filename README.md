# QCM-gilles-app

Application de révision locale, en français, sans compte ni serveur obligatoire.

## Lancer l'application

Ouvre `index.html` avec Firefox ou Chromium (double-clic ou menu « Ouvrir avec »). La banque et les scores restent dans le stockage local du navigateur utilisé.

Si ton navigateur limite l'ouverture des fichiers locaux, lance plutôt un serveur local dans ce dossier :

```bash
cd ~/QCM-gilles-app
python3 -m http.server 8000
```

Puis ouvre <http://localhost:8000>.

## Fonctions

- Page de menu avec trois icônes de matières (Automatisme, Automatique, Ressources humaines) et compteurs de questions, plus une option de session mixte toutes matières.
- Sélection de matière, choix du nombre de questions et filtres par thème.
- Option pour ne garder que les questions illustrées.
- Mélange des questions et des propositions.
- Correction immédiate après une réponse. Pour les questions à choix multiples, coche toutes les réponses puis clique sur « Vérifier ma sélection ».
- Explication, corrigé détaillé, score, temps, historique des résultats et reprise des erreurs.
- Ajout de questions, y compris une image (PNG/JPEG/WebP recommandé).
- Import/export de la banque en JSON.

## Banque initiale

202 questions d'Automatisme, dont 40 questions à choix multiples récentes dans le style « cases à cocher, une ou plusieurs bonnes réponses » : 15 sur les règles d'évolution (règles 2 et 3, franchissement, variables d'étape) et 25 sur la règle 1, la validation des transitions, l'installation étudiée en séance 2 (étapes initiales 0 et 10, état initial des vérins) et les structures du GRAFCET (saut, reprise de séquence, synchronisation). Le reste : 150 questions GA701 (séance 1), 8 sur la mesure du temps et les règles d'évolution, 3 sur la règle 5, et 2 questions illustrées (chronogramme, portions de grafcets). Les matières Automatique et Ressources humaines sont configurées mais leurs banques sont encore vides.

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
