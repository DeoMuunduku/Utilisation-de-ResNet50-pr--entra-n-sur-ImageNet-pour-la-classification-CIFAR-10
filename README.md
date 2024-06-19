# Utilisation-de-ResNet50-pr--entra-n-sur-ImageNet-pour-la-classification-CIFAR-10
Utilisation de ResNet50 pré-entraîné sur ImageNet pour la classification CIFAR-10
Utilisation de ResNet50 pré-entraîné sur ImageNet pour la classification CIFAR-10
Nous avons exploré le processus de réglage fin d'un modèle ResNet50 pré-entraîné sur l'ensemble de données CIFAR-10. Le modèle ResNet-50 affiné a atteint une précision de 93,12 % sur l’ensemble de tests CIFAR-10.

Lisez le billet de blog qui explique ce projet : Fine-Tuning ResNet50 pré-entraîné sur ImageNet pour CIFAR-10

Hyperparamètres
Optimiseur de descente de gradient stochastique (SGD) avec un taux d'apprentissage de 0,02.
Momentum de 0,85 et diminution du poids de 4e-4.
Époques : 70
Résultats
Précision de l'entraînement : La précision de l'entraînement augmente régulièrement à chaque époque, commençant à 54,20 % dans la première époque et atteignant 91,25 % dans l'époque finale. Cela indique que le modèle apprend et améliore ses performances sur les données d'entraînement.

Perte d'entraînement : La perte d'entraînement diminue progressivement au fil des époques, en commençant par 1,3123 et en diminuant jusqu'à 0,2671. Des valeurs de perte d'entraînement plus faibles indiquent que le modèle s'adapte mieux aux données d'entraînement.

Précision des tests : La précision des tests montre également une amélioration au fil des époques, passant de 70,12 % à 88,34 % à l'époque finale. Cela suggère que le modèle généralise bien et fonctionne mieux sur des données invisibles.

Perte de test : La perte de test diminue initialement puis fluctue légèrement, mais dans l'ensemble, elle reste relativement stable. Elle commence à 0,8792 et se termine à 0,3489.

Remarque : Les résultats ci-dessus ont été obtenus en utilisant une taille de lot de 32. Lorsque la taille du lot a augmenté à 64, une précision de 93,45 % a été obtenue
