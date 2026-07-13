# Schéma Notion — Chef IA

## Bases et sources de données

| Base | Database ID | Data source ID |
|---|---|---|
| Recettes | `9321554a-c670-44a3-9c9a-54e7ef5fb863` | `90c49ead-0e38-4fe8-a02f-eae41921c0f4` |
| Menus hebdomadaires | `673f346f-7fd8-4a0b-b4eb-f7770918375e` | `90d87eaa-a8c2-4160-b924-29944f841f2f` |
| Courses | `72bd3658-ebe1-41cd-bdd0-eb6bcd7cbc90` | `1d5a2002-5d88-464c-a6bb-fc483c6edd35` |
| Paramètres | `782e91be-e6ee-49c6-b645-5dd1faadbe4a` | `7491fd28-b9a9-453d-b347-8141676405be` |

## Paramètres

La ligne active porte le titre `Configuration principale` et contient :

- `Personnes` : nombre ;
- `Objectif` : sélection ;
- `Calories cibles` : nombre ;
- `Budget hebdomadaire` : nombre ;
- `Email` : e-mail ;
- `Nouvelles recettes max` : nombre ;
- `Saison` : sélection ;
- `Jours de cuisine` : sélection multiple ;
- `Générer les images` : case à cocher ;
- `Générer le PDF` : case à cocher ;
- `Actif` : case à cocher.

## Recettes

Propriétés principales utilisées par le workflow :

- `Nom` ;
- `Type` ;
- `Saison` ;
- `Temps préparation` ;
- `Temps cuisson` ;
- `Portions` ;
- `Calories par portion` ;
- `Protéines (g)` ;
- `Difficulté` ;
- `Validée` ;
- `Note` ;
- `Ingrédients` ;
- `Préparation` ;
- `Dernière utilisation`.

## Accès API

La connexion Notion `Chef IA` doit avoir les permissions suivantes :

- lire le contenu ;
- mettre à jour le contenu ;
- insérer du contenu.

Les quatre bases doivent être partagées avec cette connexion.
