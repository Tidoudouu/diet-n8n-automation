# Chef IA — automatisation n8n

Ce dépôt contient l’automatisation qui génère chaque semaine un menu adapté à une perte de poids, l’écrit dans Notion, crée la liste de courses et envoie un récapitulatif par Gmail.

## État du projet

- ✅ Bases Notion : Recettes, Menus hebdomadaires, Courses, Paramètres
- ✅ Première bibliothèque de recettes
- ✅ Configuration Notion centralisée
- ✅ Lecture des paramètres et recettes validées
- ✅ Génération d’un menu JSON structuré avec OpenAI
- ✅ Création du menu dans Notion — v0.2.0
- ✅ Création de la liste de courses liée — v0.2.0
- ✅ Envoi Gmail — v0.2.0
- ⏳ Génération unique des affiches des nouvelles recettes — version ultérieure

## Version stable de lecture

`workflow/Chef-IA-v0.1.4.json`

Cette version lit Notion et génère uniquement le menu JSON. Elle a été validée dans n8n 2.29.10.

## Importer la v0.2.0

1. Télécharge [`workflow/Chef-IA-v0.2.0.json`](workflow/Chef-IA-v0.2.0.json).
2. Dans n8n, utilise `…` puis **Import from File**.
3. Dans les quatre nœuds Notion HTTP, sélectionne **Notion Header Auth**.
4. Dans **Générer le menu**, sélectionne **OpenAI account**.
5. Dans **Envoyer le mail Gmail**, connecte ton compte Gmail.
6. Lance d’abord le workflow depuis **Test manuel**.
7. Vérifie qu’une entrée apparaît dans **Menus hebdomadaires**, qu’une entrée liée apparaît dans **Courses**, puis que le mail est reçu.
8. Active ensuite le workflow pour l’exécution automatique du samedi à 08:00.

## Ce que fait la v0.2.0

```text
Test manuel ou samedi 08:00
        ↓
Lire la configuration active dans Notion
        ↓
Lire les recettes validées
        ↓
Générer le menu avec OpenAI
        ↓
Créer la semaine dans Menus hebdomadaires
        ↓
Créer la liste dans Courses et la relier au menu
        ↓
Envoyer le récapitulatif par Gmail
```

## Bases Notion utilisées

- Paramètres : `782e91be-e6ee-49c6-b645-5dd1faadbe4a`
- Recettes : `9321554a-c670-44a3-9c9a-54e7ef5fb863`
- Menus hebdomadaires : `673f346f-7fd8-4a0b-b4eb-f7770918375e`
- Courses : `72bd3658-ebe1-41cd-bdd0-eb6bcd7cbc90`

Les sources de données et propriétés sont documentées dans [`notion/schema.md`](notion/schema.md).

## Sécurité

Ne jamais stocker dans GitHub :

- le jeton Notion ;
- la clé API OpenAI ;
- les identifiants Gmail ;
- le dossier de données local n8n ;
- un fichier `.env` réel.

Les secrets restent exclusivement dans les Credentials de n8n.
