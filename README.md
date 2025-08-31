# Transfer-_par_-segmentation
# 🧠 Apprentissage par Transfert pour la Segmentation d'Images

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![PyTorch](https://img.shields.io/badge/PyTorch-1.8%2B-red)
![License](https://img.shields.io/badge/License-MIT-green)

Ce dépôt présente un travail pratique (TP) sur **l'apprentissage par transfert appliqué à la segmentation sémantique d'images**, en utilisant des architectures modernes comme **U-Net**, **DeepLabV3+**, et la génération de données avec des **GANs**. Le tout est implémenté en Python avec TensorFlow/Keras et PyTorch.

➡️ **Objectif** : Explorer, comparer et améliorer des modèles de segmentation sur le dataset **COCO**, en appliquant des techniques avancées comme l’attention, le transfer learning, et l’augmentation de données génératives.

🔗 **Accéder au rapport complet** : [Rapport PDF](transfer_segmentation.pdf)  
💻 **Code source** : [https://github.com/marwaneouz/Transfer-_par_-segmentation](https://github.com/marwaneouz/Transfer-_par_-segmentation)

---

## 📚 Sommaire

- [Objectifs](#objectifs)
- [Dataset utilisé](#dataset-utilisé-coco)
- [Modèles implémentés](#modèles-implémentés)
- [Métriques d'évaluation](#métriques-dévaluation)
- [Résultats principaux](#résultats-principaux)
- [Structure du dépôt](#structure-du-dépôt)
- [Comment exécuter](#comment-exécuter)
- [Optimisations](#optimisations)
- [Conclusion](#conclusion)
- [Références](#références)

---

## 🎯 Objectifs

- Implémenter et comparer des modèles de segmentation : **U-Net**, **U-Net avec attention**, **DeepLabV3+**.
- Appliquer le **transfert learning** en utilisant des backbones pré-entraînés (ResNet50, ResNet101, Xception).
- Améliorer les performances avec des techniques comme l’**attention**, les **connexions sautées**, et les **pertes combinées**.
- Générer de nouvelles images d'entraînement avec des **GANs** (notamment SAGAN).
- Optimiser l'entraînement avec **mixed precision**, **augmentation avancée**, et **modèles d'ensemble**.

---

## 🖼️ Dataset utilisé : COCO

Le dataset [**COCO (Common Objects in Context)**](https://cocodataset.org) est utilisé pour l'entraînement et l'évaluation :

- 80 classes d'objets courants
- Images haute résolution avec annotations de segmentation précises
- Idéal pour tester des modèles de segmentation sémantique et d'instances

🔗 Officiel : [https://cocodataset.org](https://cocodataset.org)

---

## 🏗️ Modèles implémentés

| Modèle | Description |
|-------|-------------|
| **U-Net (basique)** | Architecture encodeur-décodeur avec skip connections |
| **U-Net + Attention** | Ajout de mécanismes d'attention pour mieux localiser |
| **U-Net + ResNet50** | Encoder basé sur ResNet50 pré-entraîné sur ImageNet |
| **DeepLabV3+ (Xception)** | Utilise ASPP et décodeur pour segmentation fine |
| **DeepLabV3+ (ResNet101)** | Version améliorée avec meilleur contexte |
| **GAN (Pix2Pix/SAGAN)** | Génération d'images pour augmentation de données |

---

## 📊 Métriques d'évaluation

Les modèles sont évalués avec les métriques suivantes :

- **Dice Similarity (DS)** : Mesure de superposition entre masques
- **IoU (Intersection over Union)** : Qualité de la segmentation
- **Précision & Rappel** : Performance par classe
- **Accuracy** : Taux de pixels correctement classifiés
- **mIoU** : Moyenne de l'IoU sur toutes les classes

---

## 📈 Résultats principaux

| Modèle | Précision | mIoU | Temps/époque |
|--------|---------|-------|-------------|
| U-Net (basique) | 78.5% | 0.654 | 25 min |
| U-Net + Attention | 81.7% | 0.702 | 28 min |
| U-Net + ResNet50 | 84.1% | 0.728 | 32 min |
| DeepLabV3+ (Xception) | 86.3% | 0.751 | 45 min |
| **DeepLabV3+ (ResNet101)** | **87.1%** | **0.763** | 52 min |

✅ **Meilleur modèle** : **DeepLabV3+ avec ResNet101**

---

 
