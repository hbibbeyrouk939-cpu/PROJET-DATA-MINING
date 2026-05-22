## Exécution du Pipeline
```bash
# Pour lancer et visualiser le notebook de segmentation
jupyter notebook RFM_Segmentation_Pipeline_Executed.ipynb

```
## Présentations Vidéos
Pour accompagner notre rapport et valider l'implémentation technique de chaque partie, vous pouvez visionner les explications détaillées et les démonstrations de code en cliquant sur les liens ci-dessous :
| # | Partie du Projet | Intervenant | Lien de la Vidéo |
|---|---|---|---|
| 1 | Ingestion, Nettoyage et Construction du Modèle RFM | Mohamed Lehbib Mbarek Beyrouk | Regarder la vidéo |
| 2 | Normalisation, K-Means et Optimisation (K optimal) | Aly Mohamed Aly | Regarder la vidéo |
| 3 | Interprétation des Clusters et Stratégies Commerciales | Maidla Isselmo | Regarder la vidéo |
| """ |  |  |  |
with open("README_Data_Mining.md", "w", encoding="utf-8") as f:
f.write(readme_dm_content)
print("File README_Data_Mining.md created successfully without emojis.")
```
Votre fichier Markdown est prêt
[file-tag: code-generated-file-0-1779417959124380203]

Voici la version finale et épurée de votre fichier `README.md` pour le projet de **Data Mining**, rédigée entièrement en français, en conservant exactement la structure stricte, l'alignement de votre équipe et le tableau final pour vos liens, sans aucun émoji.

```markdown
# Projet de Data Mining - 2026

## Informations de l'Équipe
- Présenté par :
  - Mohamed Lehbib Mbarek Beyrouk — C27888
  - Aly Mohamed Aly — C28916
  - Maidla Isselmo — C28462
- Filière : L2 (MIAGE / DA2I) — S4

## Description du Projet
Ce dépôt contient le pipeline complet de Data Mining dédié à la segmentation stratégique des clients via le modèle RFM (Récence, Fréquence, Montant) et l'algorithme de clustering K-Means. L'objectif est de transformer des données transactionnelles brutes en segments de clients exploitables afin d'optimiser les stratégies de marketing ciblé.

### Étapes Réalisées
1. **Phase 1 : Ingestion et Optimisation (Big Data Ingestion)** : Chargement des données transactionnelles initiales (Online_Retail.csv), conversion et stockage au format optimisé Parquet. L'analyse comparative a démontré une vitesse de lecture 10.83 fois supérieure pour le format Parquet grâce au stockage colonnaire et aux mécanismes de compression.
2. **Phase 2 : Nettoyage et Préparation des Données** : Identification et suppression des valeurs manquantes (notamment 24.92% de CustomerID absents), élimination des transactions annulées ou erronées (quantités et prix négatifs ou nuls) pour retenir 397 884 transactions valides. Calcul de la variable clé MontantTotal (Quantité x Prix Unitaire).
3. **Phase 3 : Ingénierie des Caractéristiques (Modèle RFM)** : Agrégation des données par client pour calculer la Récence (jours écoulés depuis le dernier achat), la Fréquence (nombre de factures uniques via nunique) et le Montant (total des dépenses). Traitement de l'asymétrie de la distribution par transformation logarithmique log(x+1) et normalisation des données via StandardScaler pour le calcul des distances écommentées.
4. **Phase 4 : Clustering et Optimisation** : Implémentation et entraînement de l'algorithme K-Means. Détermination du nombre optimal de clusters (K=3) en combinant la méthode du coude (Elbow Method) et l'évaluation du score de Silhouette pour garantir la cohérence interne des groupes.
5. **Phase 5 : Data Storytelling et Actions Commerciales** : Profilage et interprétation des trois segments obtenus (Champions, Clients à risque, et Clients potentiels fidèles), formulation de recommandations stratégiques adaptées à chaque profil, et génération de visualisations avancées en 2D et 3D.

## Technologies Utilisées
- Langage : Python 3.x
- Bibliothèques : Pandas, Scikit-Learn, Matplotlib, Seaborn, PyArrow
- Environnement : Jupyter Notebook

## Installation des Dépendances

```bash
pip install pandas scikit-learn matplotlib seaborn pyarrow

```
## Exécution du Pipeline
```bash
# Pour lancer et visualiser le notebook de segmentation
jupyter notebook RFM_Segmentation_Pipeline_Executed.ipynb

```
## Présentations Vidéos
Pour accompagner notre rapport et valider l'implémentation technique de chaque partie, vous pouvez visionner les explications détaillées et les démonstrations de code en cliquant sur les liens ci-dessous :
| # | Partie du Projet | Intervenant | Lien de la Vidéo |
|---|---|---|---|
| 1 | Ingestion, Nettoyage et Construction du Modèle RFM | Mohamed Lehbib Mbarek Beyrouk | Regarder la vidéo |
| 2 | Normalisation, K-Means et Optimisation (K optimal) | Aly Mohamed Aly | Regarder la vidéo |
| 3 | Interprétation des Clusters et Stratégies Commerciales | Maidla Isselmo | Regarder la vidéo |
```

```

