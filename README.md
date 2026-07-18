# 🗃️ Projet SQL — Analyse des ventes au détail

![SQL](https://img.shields.io/badge/SQL-MySQL-4479A1?logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/Statut-Terminé-brightgreen)

Ce projet analyse un jeu de données de ventes au détail (retail) à l'aide de requêtes **SQL** : nettoyage des données, statistiques descriptives et réponses à 10 questions métier via des requêtes avancées (agrégations, fenêtres, `CASE`, `CTE`).

## 📁 Contenu du dépôt

| Fichier | Description |
|---|---|
| [`Projet SQL.sql`](./Projet%20SQL.sql) | Script SQL complet : création de la base, nettoyage des données et 10 requêtes d'analyse. |
| [`Analyse des ventes au détail - SQL - donnees.csv`](./Analyse%20des%20ventes%20au%20d%C3%A9tail%20-%20SQL%20-%20donnees.csv) | Jeu de données brut (2000 transactions) à importer dans la table `ventes_détaillants`. |
| `README.md` | Ce fichier. |

## 🧾 Jeu de données

La table `ventes_détaillants` contient les colonnes suivantes :

| Colonne | Description |
|---|---|
| `id_transaction` | Identifiant unique de la transaction |
| `date_vente` | Date de la vente |
| `temps_vente` | Heure de la vente |
| `id_client` | Identifiant du client |
| `sexe` | Sexe du client |
| `age` | Âge du client |
| `categorie` | Catégorie du produit (Vêtements, Beauté, ...) |
| `quantite` | Quantité vendue |
| `prix_par_unite` | Prix unitaire |
| `cout_marchise_vendu` | Coût de la marchandise vendue |
| `vente_total` | Montant total de la vente |

## 🔍 Analyses réalisées

1. Ventes réalisées à une date précise (`2022-11-05`)
2. Transactions "Vêtements" de novembre 2022 avec quantité ≥ 4
3. Total des ventes par catégorie
4. Âge moyen des clients ayant acheté dans la catégorie « Beauté »
5. Transactions dont le montant total dépasse 1 000
6. Nombre de transactions par sexe et par catégorie
7. Chiffre d'affaires moyen par mois et mois le plus performant de chaque année (fonction fenêtre `RANK()`)
8. Top 5 des clients par montant total d'achats
9. Nombre de clients uniques par catégorie
10. Répartition des commandes par tranche horaire (matin / après-midi / soir) via une `CTE`

## 🛠️ Installation et utilisation

1. Créer une base de données MySQL et importer le CSV dans une table nommée `ventes_détaillants` (les noms de colonnes doivent correspondre à ceux listés ci-dessus).
2. Exécuter le script [`Projet SQL.sql`](./Projet%20SQL.sql) dans votre client SQL (MySQL Workbench, DBeaver, etc.).

```sql
CREATE DATABASE bdd_projet_vente_detail;
USE bdd_projet_vente_detail;
-- puis importer le CSV dans la table ventes_détaillants
-- et exécuter les requêtes du script
```

> ⚠️ Le script utilise des fonctions spécifiques à **MySQL** (`DATE_FORMAT`, `EXTRACT`, fonctions fenêtre). Pour PostgreSQL ou SQL Server, adaptez la syntaxe si besoin.

## 🧰 Technologies

- **SQL (MySQL)**
- Fonctions d'agrégation (`SUM`, `COUNT`, `AVG`)
- Fonctions fenêtre (`RANK() OVER`)
- Expressions conditionnelles (`CASE`) et CTE (`WITH`)

## 📄 Licence

Projet personnel réalisé à des fins d'apprentissage (Data Analyst).
