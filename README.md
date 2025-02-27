## Description

Ce projet présente une analyse de clustering non supervisé appliquée au jeu de données des chiffres manuscrits (digits) fourni par scikit-learn. L’objectif est de regrouper les images (représentées par 64 caractéristiques, issues d’une image 8×8) en 10 clusters à l’aide de l’algorithme K-means, puis d’évaluer la correspondance entre les clusters obtenus et les vraies classes.

## Étapes de l’analyse

1. **Chargement des données**  
   Le jeu de données `digits` est chargé, contenant 1797 échantillons avec 64 caractéristiques chacun.

2. **Clustering avec K-means**  
   - Application de l’algorithme K-means pour créer 10 clusters.
   - Remarque : Un avertissement indique que la valeur par défaut du paramètre `n_init` changera dans une future version. Il est recommandé de le spécifier explicitement.

3. **Association des clusters aux classes réelles**  
   - Comme K-means attribue des labels arbitraires, chaque cluster est associé à la classe réelle la plus fréquente parmi ses membres à l’aide de la fonction `mode` de SciPy.

4. **Évaluation des performances**  
   - **Précision** : Après le réassignement des labels, l’accuracy est d’environ 79%.
   - **Matrice de confusion** : Visualisation sous forme de heatmap pour comparer les labels prédits aux véritables labels.
   - Calcul d’autres métriques :
     - **Indice de silhouette** ≈ 0.18 (indiquant une séparation modérée des clusters).
     - **Indice de Rand ajusté** ≈ 0.67 (mesurant l’accord entre le clustering et les vraies classes).

5. **Visualisations**  
   - **Centres des clusters** : Les centres obtenus par K-means sont remodelés en images 8×8 afin de visualiser les prototypes de chiffres.
   - **Projection en 2D** : Une réduction de dimensionnalité avec PCA permet de visualiser la distribution des données et la répartition des clusters dans un espace 2D.
   - **Matrice de confusion** : Affichée à l’aide de Seaborn pour observer la correspondance entre les clusters et les classes réelles.

## Dépendances

Pour exécuter cette analyse, vous aurez besoin des bibliothèques suivantes :

- Python 3
- scikit-learn
- numpy
- matplotlib
- seaborn
- scipy

## Utilisation

Pour reproduire cette analyse :

1. Assurez-vous que toutes les dépendances sont installées (vous pouvez utiliser `pip install scikit-learn numpy matplotlib seaborn scipy`).
2. Ouvrez le notebook `clustering_digits.ipynb` dans un environnement compatible avec Jupyter (par exemple, Jupyter Notebook ou Google Colab).
3. Exécutez les cellules du notebook pour observer les résultats de l’analyse, y compris les visualisations et les métriques d’évaluation.

## Conclusion

Cette analyse démontre que, même en étant non supervisé, l’algorithme K-means parvient à capturer une structure significative dans le jeu de données des chiffres manuscrits. Les métriques obtenues, comme l’accuracy, l’indice de silhouette et l’indice de Rand ajusté, indiquent une correspondance modérée entre les clusters et les vraies classes. Des améliorations peuvent être envisagées, par exemple en ajustant les paramètres de l’algorithme ou en explorant d’autres techniques de réduction de dimensionnalité.
