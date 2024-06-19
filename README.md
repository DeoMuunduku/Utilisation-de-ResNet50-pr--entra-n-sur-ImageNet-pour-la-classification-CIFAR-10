Utilisation de ResNet50 pré-entraîné sur ImageNet pour la classification CIFAR-10
Ce projet explore le processus de réglage fin (fine-tuning) d'un modèle ResNet50 pré-entraîné sur l'ensemble de données ImageNet pour la tâche de classification d'images sur l'ensemble de données CIFAR-10. Le modèle ajusté a atteint une précision impressionnante de 93,12 % sur l’ensemble de tests CIFAR-10, démontrant la puissance de l'apprentissage par transfert dans les tâches de vision par ordinateur.

Pour plus de détails, lisez le billet de blog : Fine-Tuning ResNet50 pré-entraîné sur ImageNet pour CIFAR-10

Introduction
Le réglage fin d'un modèle pré-entraîné consiste à adapter un modèle initialement formé sur un grand ensemble de données (comme ImageNet) à une tâche spécifique sur un nouvel ensemble de données (comme CIFAR-10). Ce processus permet de tirer parti des caractéristiques déjà apprises par le modèle, ce qui peut accélérer l'apprentissage et améliorer les performances sur des tâches spécifiques.

Préparation des données
L'ensemble de données CIFAR-10 comprend 60 000 images couleur de 32x32 pixels, réparties en 10 classes avec 6 000 images par classe. Les classes sont uniformément réparties, chaque classe contenant exactement 5 000 images d'entraînement et 1 000 images de test.

Chargement et transformation des données
Les images CIFAR-10 sont d'abord normalisées et augmentées pour améliorer la robustesse du modèle. Voici les transformations appliquées :

Entraînement :

Recadrage aléatoire à 32x32 pixels avec un padding de 4
Retournement horizontal aléatoire
Normalisation avec des moyennes et des écarts-types spécifiques au jeu de données CIFAR-10
Test :

Normalisation avec les mêmes moyennes et écarts-types que pour l'entraînement
Architecture du modèle
Le modèle de base utilisé est ResNet50, pré-entraîné sur l'ensemble de données ImageNet. Quelques modifications ont été apportées pour l'adapter à CIFAR-10 :

Convolution initiale (conv1) : La première couche de convolution a été modifiée pour utiliser un noyau de 3x3 au lieu de 7x7 afin de s'adapter aux petites images de 32x32 pixels de CIFAR-10.
Couche entièrement connectée (fc) : La dernière couche entièrement connectée a été remplacée pour correspondre au nombre de classes de CIFAR-10 (10 classes).
Hyperparamètres
Optimiseur : Descente de gradient stochastique (SGD)
Taux d'apprentissage : 0,01
Momentum : 0,9
Diminution du poids : 5e-4
Nombre d'époques : 60
Taille du lot : 32
Entraînement et évaluation
Processus d'entraînement
Le modèle a été entraîné pendant 60 époques, avec des mesures de précision et de perte prises à chaque époque pour surveiller les performances. Les métriques suivantes ont été utilisées :

Perte d'entraînement : Mesurée par la fonction de perte d'entropie croisée
Précision d'entraînement : Pourcentage de prédictions correctes sur l'ensemble d'entraînement
Perte de test : Mesurée par la fonction de perte d'entropie croisée sur l'ensemble de test
Précision de test : Pourcentage de prédictions correctes sur l'ensemble de test
Résultats de l'entraînement
Précision de l'entraînement : La précision de l'entraînement a augmenté régulièrement, passant de 54,20 % dans la première époque à 91,25 % dans l'époque finale, indiquant une amélioration constante des performances du modèle sur les données d'entraînement.
Perte d'entraînement : La perte d'entraînement a diminué de manière continue, passant de 1,3123 à 0,2671, montrant que le modèle s'adapte de mieux en mieux aux données d'entraînement.
Précision des tests : La précision des tests a montré une amélioration notable, passant de 70,12 % à 88,34 % dans l'époque finale, suggérant que le modèle généralise bien aux nouvelles données.
Perte de test : La perte de test a initialement diminué puis a légèrement fluctué, mais est restée relativement stable, passant de 0,8792 à 0,3489.
Remarque
Les résultats ci-dessus ont été obtenus en utilisant une taille de lot de 32. Lorsque la taille du lot a été augmentée à 64, une précision de 93,45 % a été obtenue, ce qui démontre l'impact de la taille du lot sur les performances du modèle.

Visualisation des résultats
Courbes de perte et de précision
Les courbes de perte et de précision montrent l'évolution des performances du modèle au fil des époques. Les graphiques suivants illustrent la diminution de la perte et l'augmentation de la précision pendant l'entraînement et les tests.

Courbe de perte :


Courbe de précision :


Prédiction d'exemples
Une visualisation des prédictions du modèle sur des images de test montre sa capacité à reconnaître correctement les classes des images. Voici un exemple de prédiction :

Image prédite :


Étiquette prédite : camion
Étiquette réelle : camion
Conclusion
Le réglage fin d'un modèle ResNet50 pré-entraîné sur ImageNet pour la classification d'images CIFAR-10 a montré des résultats prometteurs, atteignant une précision de 93,12 %. Cette approche démontre l'efficacité de l'apprentissage par transfert et de l'optimisation fine pour améliorer les performances sur des tâches de classification spécifiques
