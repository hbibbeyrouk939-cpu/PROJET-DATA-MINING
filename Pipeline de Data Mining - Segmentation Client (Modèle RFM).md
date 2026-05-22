# Pipeline de Data Mining - Segmentation Client (Modèle RFM)

Ce projet implémente un pipeline complet de Data Mining pour la segmentation client basée sur le modèle RFM (Récence, Fréquence, Montant) en utilisant le jeu de données `Online Retail`.

## Contexte Métier

Le service Marketing d'une entreprise d'E-commerce souhaite regrouper ses clients selon leurs comportements d'achat afin de lancer des campagnes personnalisées. Ce projet transforme des données transactionnelles brutes en connaissances actionnables via le clustering.

## Jeu de Données

Le jeu de données utilisé est le `Online Retail Dataset`, disponible sur le [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail). Il contient les transactions réelles survenues entre le 01/12/2010 et le 09/12/2011 pour un commerce de détail en ligne basé au Royaume-Uni.

### Variables Clés

| Variable | Description |
|---|---|
| `InvoiceNo` | Identifiant unique de transaction (commence par 'C' pour une annulation) |
| `StockCode` | Code unique du produit |
| `Description` | Nom de l'article ou du service |
| `Quantity` | Quantités de chaque article par transaction |
| `InvoiceDate` | Date et heure de génération de la facture |
| `UnitPrice` | Prix unitaire de l'article en livres sterling (£) |
| `CustomerID` | Identifiant unique du client (crucial pour le clustering) |
| `Country` | Nom du pays où réside le client |

## Phases du Projet

Le pipeline est structuré en 5 phases principales, détaillées dans le notebook Jupyter `RFM_Segmentation_Pipeline_Executed.ipynb`.

### Phase 1 : Acquisition et Ingestion (Ingestion Big Data)

*   **Q1. Collecte :** Téléchargement du dataset `Online Retail`.
*   **Q2. Formats :** Chargement du fichier `.csv` et conversion au format `.parquet`. Comparaison des temps de lecture et explication des avantages du format Parquet.

### Phase 2 : Data Cleaning (Le défi du monde réel)

*   **Q3. Analyse des manquants :** Identification du pourcentage de valeurs nulles et suppression des lignes sans `CustomerID`.
*   **Q4. Nettoyage métier :** Élimination des transactions avec des quantités négatives (annulations) et des prix unitaires aberrants (inférieurs ou égaux à 0).
*   **Q5. Ingénierie de base :** Création de la variable `MontantTotal = Quantity × UnitPrice`.

### Phase 3 : Feature Engineering (Transformation RFM)

Transformation des données transactionnelles en une structure 
"Une ligne = Un Client" en calculant les indicateurs RFM :

*   **Récence (R) :** Jours écoulés depuis la dernière commande.
*   **Fréquence (F) :** Nombre de factures uniques par client.
*   **Montant (M) :** Somme totale des dépenses.

*   **Q6. Agrégation RFM :** Réalisation de l'agrégation pour obtenir le DataFrame `df_RFM`.
*   **Q7. Analyse de la distribution :** Tracé de l'histogramme de la variable `Montant` et observation de l'asymétrie.
*   **Q8. Transformation Log :** Application d'une transformation logarithmique (`log(x+1)`) pour réduire l'impact des valeurs extrêmes.
*   **Q9. Standardisation :** Utilisation de `StandardScaler` pour normaliser les variables R, F et M, avec explication de la nécessité mathématique pour le K-Means.

### Phase 4 : Clustering et Optimisation

*   **Q10. Recherche du K optimal :** Implémentation de la méthode du coude (Elbow Method) en calculant l'inertie pour k allant de 1 à 10.
*   **Q11. Validation :** Utilisation du Silhouette Score pour confirmer le nombre de clusters.
*   **Q12. Application :** Entraînement du modèle K-Means final et récupération des étiquettes de clusters.

### Phase 5 : Découverte de Connaissances (Data Storytelling)

*   **Q13. Analyse des moyennes :** Analyse des moyennes de R, F et M pour chaque cluster.
*   **Q14. Profilage :** Identification du cluster des 
"Champions" et celui des "Clients à Risque de Départ".
*   **Q15. Action Commerciale :** Proposition de stratégies marketing différentes pour chacun des clusters identifiés.

## Livrables

*   `RFM_Segmentation_Pipeline_Executed.ipynb` : Le notebook Jupyter complet avec toutes les phases exécutées et les visualisations.
*   `README.md` : Ce fichier descriptif du projet.
*   `Online_Retail.csv` : Le jeu de données original converti en CSV.
*   `Online_Retail.parquet` : Le jeu de données converti au format Parquet.

## Auteur

Manus AI
