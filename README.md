# Chef IA — automatisation n8n

Ce dépôt contient l’automatisation qui génère chaque semaine un menu adapté à une perte de poids, enregistre les résultats dans Notion et envoie un récapitulatif par e-mail.

## État du projet

- ✅ Bases Notion créées : Recettes, Menus hebdomadaires, Courses, Paramètres
- ✅ Première bibliothèque de recettes
- ✅ Configuration Notion centralisée
- ✅ Workflow n8n v0.1 importable
- ⏳ Écriture automatique dans les bases Menus et Courses
- ⏳ Envoi Gmail
- ⏳ Génération unique des affiches des nouvelles recettes

## Importer le workflow

1. Ouvrir n8n sur `http://localhost:5678`.
2. Ouvrir le workflow **Chef IA**.
3. Cliquer sur `…` puis **Import from File**.
4. Importer `workflow/Chef-IA-v0.1.json`.
5. Dans les nœuds Notion, sélectionner l’identifiant **Notion account**.
6. Dans le nœud OpenAI, sélectionner l’identifiant **OpenAI account**.
7. Exécuter d’abord le workflow manuellement.

Le workflow v0.1 lit la configuration active et les recettes validées, construit le prompt, appelle OpenAI et retourne un menu JSON. Il ne modifie pas encore les bases Menus/Courses : cela sera ajouté dans la v0.2 après validation du format généré.

## Bases Notion utilisées

- Paramètres : `782e91be-e6ee-49c6-b645-5dd1faadbe4a`
- Recettes : `9321554a-c670-44a3-9c9a-54e7ef5fb863`
- Menus hebdomadaires : `673f346f-7fd8-4a0b-b4eb-f7770918375e`
- Courses : `72bd3658-ebe1-41cd-bdd0-eb6bcd7cbc90`

## Sécurité

Ne jamais stocker dans GitHub :

- le jeton Notion ;
- la clé API OpenAI ;
- les identifiants Gmail ;
- le dossier de données local n8n.

Les secrets restent exclusivement dans les Credentials de n8n.
