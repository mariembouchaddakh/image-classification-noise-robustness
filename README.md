# Image Classification — Noise Robustness

Étude de l'effet du bruit (gaussien, sel & poivre, speckle) sur la classification d'images
Fashion-MNIST (5 classes × 100 images), avec des descripteurs HOG et deux classifieurs (SVM, k-NN).

## Contenu
- `mini_projet_bruit.ipynb` : notebook complet (parties 1 à 3 + comparaison), déjà exécuté
- `mini_projet_bruit.html` : version HTML du notebook, lisible sans Jupyter
- `data/fashion_mnist/<classe>/` : les 500 images utilisées, un dossier par classe

## Plan
1. **Préparation** : chargement, exemples, répartition des classes, redimensionnement 64×64 en niveaux de gris, découpage 70/30
2. **Images propres** : HOG, SVM et k-NN, accuracy, matrice de confusion, précision/rappel/F1
3. **Images bruitées** : 10 %, 25 % et 50 % des images bruitées au hasard, découpage stratifié (classe, bruitée), mêmes descripteurs et classifieurs
4. **Comparaison** : tableaux, courbes, moyenne sur 10 tirages

## Résultats (accuracy moyenne sur 10 tirages)

| | Sans bruit | 50 % gaussien | 50 % sel & poivre | 50 % speckle |
|---|---|---|---|---|
| SVM | 0,955 | 0,945 | 0,946 | 0,949 |
| k-NN | 0,923 | 0,893 | 0,890 | 0,909 |

## Exécution
```bash
pip install numpy pandas matplotlib seaborn pillow scikit-learn scikit-image jupyter
jupyter lab mini_projet_bruit.ipynb
```
