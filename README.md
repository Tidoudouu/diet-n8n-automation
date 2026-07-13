# Chef IA — automatisation n8n

Ce dépôt contient l’automatisation qui génère chaque semaine un menu adapté à une perte de poids à partir des recettes stockées dans Notion.

## État du projet

- ✅ Bases Notion : Recettes, Menus hebdomadaires, Courses, Paramètres
- ✅ Première bibliothèque de recettes
- ✅ Configuration Notion centralisée
- ✅ Workflow n8n v0.1 importable
- ✅ Lecture des paramètres et recettes validées
- ✅ Génération d’un menu JSON structuré avec OpenAI
- ⏳ Écriture automatique dans Menus et Courses — v0.2
- ⏳ Envoi Gmail — v0.2
- ⏳ Génération unique des affiches des nouvelles recettes — version ultérieure

## Importer le workflow v0.1

1. Ouvre le fichier [`workflow/Chef-IA-v0.1.json`](workflow/Chef-IA-v0.1.json) dans GitHub.
2. Clique sur **Download raw file** ou télécharge le dépôt en ZIP.
3. Ouvre n8n sur `http://localhost:5678`.
4. Dans le workflow **Chef IA**, clique sur `…` puis **Import from File**.
5. Importe `Chef-IA-v0.1.json`.
6. Dans les deux nœuds Notion, sélectionne le credential **Notion account**.
7. Dans le nœud OpenAI, sélectionne le credential **OpenAI account**.
8. Clique sur **Execute workflow**.
9. Ouvre le dernier nœud **Menu JSON final** pour voir le résultat.

Le workflow comprend aussi un déclencheur automatique chaque samedi à 08:00, mais il reste désactivé jusqu’à la validation du test manuel.

## Ce que fait la v0.1

```text
Test manuel ou samedi 08:00
        ↓
Lire la configuration active dans Notion
        ↓
Lire les recettes validées
        ↓
Construire une demande structurée
        ↓
Appeler l’API OpenAI Responses
        ↓
Retourner un menu JSON exploitable
```

La v0.1 ne modifie pas encore les bases Menus/Courses et n’envoie pas encore d’e-mail. Cette séparation permet de valider d’abord la sélection des recettes et le format JSON avant d’autoriser les écritures automatiques.

## Bases Notion utilisées

- Paramètres : `782e91be-e6ee-49c6-b645-5dd1faadbe4a`
- Recettes : `9321554a-c670-44a3-9c9a-54e7ef5fb863`
- Menus hebdomadaires : `673f346f-7fd8-4a0b-b4eb-f7770918375e`
- Courses : `72bd3658-ebe1-41cd-bdd0-eb6bcd7cbc90`

Les identifiants de sources de données et les propriétés sont documentés dans [`notion/schema.md`](notion/schema.md).

## Prompts

- [`prompts/menu.md`](prompts/menu.md) : règles de génération du menu.
- [`prompts/image.md`](prompts/image.md) : charte des affiches de recettes.

## Sécurité

Ne jamais stocker dans GitHub :

- le jeton Notion ;
- la clé API OpenAI ;
- les identifiants Gmail ;
- le dossier de données local n8n ;
- un fichier `.env` réel.

Les secrets restent exclusivement dans les Credentials de n8n.
