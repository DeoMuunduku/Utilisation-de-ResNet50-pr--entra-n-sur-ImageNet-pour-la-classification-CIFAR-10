Fine-Tuning du Modèle ResNet50 pour la Classification d'Images CIFAR-10
Description du Projet
Ce projet a été développé par Deo. L'objectif principal de ce projet est de classifier les images du dataset CIFAR-10 en utilisant un modèle ResNet50 pré-entraîné, modifié et ajusté (fine-tuned) pour cette tâche spécifique. Le projet inclut le chargement des données, le fine-tuning du modèle, et l'évaluation de ses performances.

Objectifs
Charger et prétraiter le dataset CIFAR-10
Modifier et adapter le modèle ResNet50 pour la classification des images CIFAR-10
Effectuer le fine-tuning du modèle sur les données d'entraînement et évaluer ses performances sur les données de test
Sauvegarder le modèle fine-tuné et les métriques de performance
Visualiser les pertes et les précisions au cours de l'entraînement
Fonctionnalités Principales
Chargement et prétraitement des données CIFAR-10
Modification du modèle ResNet50 pour la classification CIFAR-10
Fine-tuning du modèle avec gestion de l'optimiseur et du scheduler
Évaluation des performances du modèle
Visualisation des pertes et des précisions
Technologies Utilisées
Langages de programmation : Python
Bibliothèques : PyTorch, Torchvision, Matplotlib, Numpy
Installation et Configuration
Clonez le dépôt
Clonez le dépôt :
bash
Copier le code
git clone [URL du dépôt]
Accédez au répertoire du projet :
bash
Copier le code
cd [nom du répertoire]
Installez les dépendances :
bash
Copier le code
pip install -r requirements.txt
Utilisation
Pour lancer le projet, exécutez :
bash
Copier le code
python main.py
Le code pour charger les données :
python
Copier le code
trainset, trainloader, testset, testloader, classes = load_dataset()
Le code pour effectuer le fine-tuning du modèle :
python
Copier le code
model, train_losses, train_accuracies, test_losses, test_accuracies = train_epochs(
    model, trainloader, testloader, criterion, optimizer, device,
    num_epochs, save_interval
)
Pour visualiser les performances :
python
Copier le code
plot_loss(train_losses, test_losses)
plot_accuracy(train_accuracies, test_accuracies)
Contribution
Les contributions sont les bienvenues. Veuillez suivre les étapes ci-dessous pour contribuer :

Fork le dépôt
Créez une branche de fonctionnalité (git checkout -b feature/AmazingFeature)
Commitez vos changements (git commit -m 'Add some AmazingFeature')
Poussez vers la branche (git push origin feature/AmazingFeature)
Ouvrez une Pull Request
