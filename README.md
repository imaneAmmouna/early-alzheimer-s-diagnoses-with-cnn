# Early Alzheimer's Diagnoses with CNN
## Maladie d’Alzheimer et sa progression
La maladie d’Alzheimer est une maladie neurodégénérative progressive qui affecte principalement la mémoire, les fonctions cognitives et le comportement. C’est la cause la plus fréquente de démence chez les personnes âgées.
<p align="center">
  <img src="Alzheimer.JPG" alt="IRM Alzheimer" width="400">
</p>
**1. Physiopathologie**
- Accumulation anormale de protéines bêta-amyloïdes formant des plaques dans le cerveau.
- Formation de dégénérescences neurofibrillaires dues à la protéine tau.
- Ces anomalies entraînent la mort des neurones et une réduction du volume cérébral, particulièrement dans l’hippocampe et le cortex.
**2. Stades de la maladie**
La progression d’Alzheimer est généralement divisée en quatre stades principaux :
*a. Aucun déficit (No Impairment)*
- Pas de symptômes cliniques.
- Fonction cognitive normale.
*b. Troubles très légers (Very Mild Impairment)*
- Oublis occasionnels de mots ou d’objets.
- Légère perte de mémoire à court terme, souvent confondue avec le vieillissement normal.
*c. Troubles légers à modérés (Mild/Moderate Impairment)*
- Difficultés croissantes pour accomplir des tâches quotidiennes (gestion de finances, organisation).
- Oublis plus fréquents, désorientation spatiale et temporelle.
*d. Troubles sévères (Severe Impairment)*
- Perte importante de mémoire et des fonctions cognitives.
- Incapacité à reconnaître des proches, troubles du langage et dépendance totale pour les activités de la vie quotidienne.
<p align="center">
  <img src="Alzheimer_diagnoses.JPG" alt="Alzheimer Diagnoses" width="400">
</p>
**3. Importance du diagnostic précoce**
Détecter la maladie avant l’apparition des symptômes sévères permet :
- Une meilleure gestion clinique et thérapeutique.
- La planification de soins adaptés.
- La possibilité de ralentir la progression grâce aux traitements disponibles.

## Motivation du recours au Deep Learning pour la détection de l’Alzheimer
La maladie d’Alzheimer est une pathologie neurodégénérative complexe dont le diagnostic repose principalement sur l’analyse d’images cérébrales (IRM). Cependant, l’interprétation manuelle de ces images est difficile, longue et sujette à des erreurs humaines, surtout dans les stades précoces où les changements sont très subtils.
Le Deep Learning (DL), et plus particulièrement les réseaux de neurones convolutifs (CNN), offre une solution performante pour automatiser et améliorer cette détection. Grâce à leur capacité à extraire automatiquement des caractéristiques discriminantes des images, ces modèles permettent :
- d’identifier les anomalies cérébrales associées à la maladie,
- d’améliorer la précision du diagnostic,
- et de réduire le temps d’analyse pour les cliniciens.
Ainsi, l’application du DL à la classification d’IRM dans le cadre d’Alzheimer contribue à un diagnostic plus rapide, objectif et fiable.

## Jeu de données
Le jeu de données utilisé provient de Kaggle, intitulé “Best Alzheimer MRI Dataset (99% Accuracy)”. Il contient des images IRM cérébrales classées selon différents stades de la maladie d’Alzheimer.
Les données sont réparties en plusieurs catégories (ou classes) représentant les différents niveaux de progression de la maladie, tels que :
- Non Demented : sujets sains sans signes de démence,
- Very Mild Demented : premiers signes légers de déclin cognitif,
- Mild Demented : stade intermédiaire de la maladie,
- Moderate Demented : stade avancé avec perte cognitive notable.
Chaque classe contient plusieurs centaines d’images IRM, permettant d’entraîner un modèle de Deep Learning capable de distinguer automatiquement les différents stades.
Avant l’entraînement, les images sont redimensionnées, normalisées et organisées par classes afin de garantir une bonne qualité d’apprentissage et d’évaluation.

## Modèle CNN proposé
Pour la détection et la classification des stades de la maladie d’Alzheimer, nous avons utilisé un modèle basé sur ResNet50, renforcé par des couches CNN supplémentaires.
- ResNet50 est un réseau de neurones convolutionnel profond connu pour sa capacité à extraire des caractéristiques visuelles complexes grâce à son architecture à résidus (skip connections) qui évite le problème du vanishing gradient.
- Ce modèle sert ici de base d’extraction de caractéristiques.
- Des couches convolutionnelles supplémentaires ont été ajoutées pour affiner l’apprentissage aux spécificités des IRM cérébrales.
- Enfin, des couches fully connected et Dropout ont été intégrées pour la classification finale et pour réduire le surapprentissage.
Le modèle prend en entrée des images de taille normalisée et produit en sortie une prédiction multi-classes correspondant aux différents stades d’Alzheimer (Non, Very Mild, Mild, Moderate).

## Paramètres d’entraînement du modèle
## Évaluation du modèle
