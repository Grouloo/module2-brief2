# Module 2 Brief 2

## Installation

```bash
python -m venv .venv

source .venv/bin/activate

pip install -r requirements.txt
```

## Structure du dépôt

- /data
  - **raw_dataset.csv :** Jeu de données brut
  - **encoded_dataset.csv :** Jeu de données brut avec les valeurs non-numériques encodées
  - **cleaned_dataset.csv :** Jeu de données nettoyé
  - **final_dataset.csv :** Jeu de données nettoyé et conforme éthiquement
- **workflow.ipynb :** Notebook Jupyter permettant d'évaluer et de nettoyer le jeu de données brut.

## Jeu de données

Chaque ligne du jeu de données fourni permet de relier le montant d'un emprunt bancaire aux caractérisiques de l'individu l'ayant contracté.

Il présente des valeurs numériques, du texte (nom, prénom), et des données catégorielles (niveau d'étude, license sportive, nationalité française, région, fumeur, sexe, situation familliale).

## Nettoyage

Lors du nettoyage du jeu de données, nous avons :

- Remplacé les valeurs manquantes par les médianes des colonnes
- Supprimé les erreurs apparentes du jeu de données (loyers négatifs)
- Supprimé les valeurs aberrantes des colonnes `taille`, `poids`, `revenu_estime_mois` et `montant_pret`

Nous sommes passé de 10 000 lignes avant nettoyage, à 9 733 lignes après nettoyage.

Le détail des évaluations et des décisions peut être retrouvé dans le fichier `workflow.ipynb`

## Mise en conformité

Afin que le jeu de données final soit conforme à la loi (RGPD), nous avons réalisé les modifications suivantes :

- Remplacement des colonnes `taille` et `poids` par une colonne IMC, afin d'éviter des comportements discriminatoires
- Suppression des colonnes `nom`, `prenom`, `sexe`, `region`, `nationalité_francaise`, `taille`, et `poids`
