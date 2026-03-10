# Computer Vision Contour Detection

# Détection de Contours en Traitement d'Images
## Comparaison des opérateurs Roberts, Prewitt, Sobel et Canny

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-green.svg)
![NumPy](https://img.shields.io/badge/NumPy-1.19+-orange.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.3+-red.svg)
![Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat&logo=google-colab&logoColor=white)

## 📋 Description du Projet

Ce projet a été réalisé dans le cadre d'un Travail Pratique (TP) sur la détection de contours en vision par ordinateur. L'objectif principal est d'implémenter, comparer et analyser différentes méthodes de détection de contours :

- **Opérateur de Roberts** (1963) - Le plus simple et rapide
- **Opérateur de Prewitt** (1970) - Avec lissage uniforme
- **Opérateur de Sobel** (1968) - Avec pondération gaussienne
- **Détecteur de Canny** (1986) - Considéré comme optimal

## Objectifs du TP

1. **Comprendre les fondements mathématiques** de chaque méthode de détection
2. **Implémenter et appliquer** ces opérateurs sur différents types d'images
3. **Analyser la sensibilité au bruit** de chaque méthode
4. **Comparer la qualité et la précision** des contours détectés
5. **Étudier l'effet des seuils** sur les résultats
6. **Comprendre pourquoi Canny est considéré comme optimal**

## Types d'Images Analysées

Trois types d'images ont été utilisés pour l'expérimentation :
- **Image standard** (photo de chat - cat.jpg)
- **Image avec bruit gaussien** (simulation de capteur bruité)
- **Image avec bruit sel et poivre** (simulation de transmission bruitée)

## Technologies Utilisées

- **Google Colab** - Environnement de développement
- **Python 3.8+** - Langage de programmation
- **OpenCV** - Traitement d'images
- **NumPy** - Calculs numériques
- **Matplotlib** - Visualisation des résultats
- **SciPy** - Opérations de convolution

## Méthodes Implémentées

### 1. Opérateur de Roberts
- Masques 2×2 : [[1,0],[0,-1]] et [[0,1],[-1,0]]
- Très rapide mais sensible au bruit
- Détecte les contours diagonaux

### 2. Opérateur de Prewitt
- Masques 3×3 avec pondération uniforme
- Effet de lissage intégré
- Bonne détection directionnelle

### 3. Opérateur de Sobel
- Masques 3×3 avec pondération gaussienne [1,2,1]
- Meilleure robustesse au bruit
- Plus précise que Prewitt

### 4. Détecteur de Canny
- Algorithme multi-étapes (lissage, gradient, suppression non-maxima, hystérésis)
- Résultats optimaux
- Meilleure continuité des contours


## 🚀 Fonctionnalités du Code

### Implémentation Personnalisée
-  Opérateur de Roberts (filtres 2×2)
-  Opérateur de Prewitt (filtres 3×3)
-  Opérateur de Sobel (via OpenCV et custom)
-  Détecteur de Canny (via OpenCV)

### Analyse et Visualisation
-  Application avec différents seuils (30, 60, 90, 120, 150)
-  Génération d'images bruitées (gaussien, sel & poivre)
-  Visualisation comparative multi-vues
-  Calcul de métriques (densité des contours, intensité moyenne)

### Sauvegarde et Export
-  Sauvegarde automatique des résultats
-  Export vers Google Drive
-  Téléchargement local des résultats
-  Compression ZIP des dossiers

##  Résultats et Observations

### Comparaison des Méthodes

| Méthode | Robustesse au Bruit | Précision | Continuité | Vitesse |
|---------|---------------------|-----------|------------|---------|
| Roberts | ❌ Faible | ⭐⭐ | ⭐ | ⚡ Très rapide |
| Prewitt | ⭐⭐ Moyenne | ⭐⭐⭐ | ⭐⭐ | ⚡ Rapide |
| Sobel | ⭐⭐⭐ Bonne | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⚡ Rapide |
| Canny | ⭐⭐⭐⭐ Excellente | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | 🐢 Lent |

### Points Clés
1. **Roberts** : Idéal pour les applications temps réel sur images peu bruitées
2. **Prewitt** : Bon compromis simplicité/efficacité
3. **Sobel** : Excellent choix général, robuste et précis
4. **Canny** : Résultats optimaux mais plus lent, idéal pour applications critiques

## 🔧 Installation et Utilisation

### Avec Google Colab (Recommandé)
1. Ouvrir [Google Colab](https://colab.research.google.com/)
2. Uploader le notebook `Edge detection LLMs benchmark.ipynb`
3. Uploader l'image `cat.jpg` quand demandé
4. Exécuter toutes les cellules

### En Local
```bash
# Cloner le repository
git clone https://github.com/votre-username/TP-Edge-Detection.git
cd TP-Edge-Detection

# Installer les dépendances
pip install opencv-python numpy matplotlib scipy

# Lancer le notebook
jupyter notebook TP3_Edge_Detection.ipynb
