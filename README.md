Voici le **Cahier des Charges (CdC)** pour le projet de plateforme de cours et QCM de Physique-Chimie, formaté dans un fichier **README.md**.

---

# 📚 README du Projet : Plateforme Physique-Chimie Lycée

Ce document sert de Cahier des Charges (CdC) pour la plateforme web de cours et de quiz en Physique-Chimie, ciblant les élèves du lycée (Seconde, Première, Terminale).

## 1. Objectifs et Contexte du Projet

| Champ | Description |
| :--- | :--- |
| **Titre du Projet** | Plateforme Web de Cours et QCM de Révision en Physique-Chimie |
| **Objectif** | Fournir un support pédagogique structuré et interactif pour la révision des programmes de Physique-Chimie au Lycée. |
| **Public Cible** | Élèves de **Seconde**, **Première** et **Terminale**. |
| **Auteur/Développeur** | Thomas NGUYEN (selon les mentions dans les fichiers sources, étudiant en BTS SIO option SLAM à l'ENC). |

## 2. Architecture et Structure du Site

Le site est organisé autour d'une navigation principale fixe et comprend deux types de pages majeurs : les **Cours** et les **Quiz**.

### 2.1. Structure des Fichiers et Navigation

La navigation principale doit être accessible depuis un **bandeau fixe** sur toutes les pages.

| Fichier / Page | Titre | Description |
| :--- | :--- | :--- |
| `index.html` | Accueil | Page de présentation du site. |
| `Cours de 2nd.html` | Cours de 2nde | Liste des ressources (Cours & Exercices) pour la Seconde. |
| `1ere année.html` | Cours de 1ère Année | Liste des ressources (Cours & Exercices) pour la Première. |
| `Terminale.html` | Cours de Terminale | Liste des ressources (Cours & Exercices) pour la Terminale. |
| `Quiz de révision de seconde.html` | QCM Seconde | Page d'examen/quiz pour la Seconde. |
| `Quiz de révision de 1ère Année.html` | QCM Première | Page d'examen/quiz pour la Première. |
| `Quiz de révision de Terminale.html` | QCM Terminale | Page d'examen/quiz pour la Terminale. |

### 2.2. Pages de Cours (`*année.html`)

Ces pages doivent présenter le contenu sous forme de listes de liens :
* **Liste des Cours** (ex : Chimie 1, Physique 1, Cours 4, etc.).
* **Liste des Exercices** (ex : Exercice 1, Exercice 2, etc.).

**TODO :** Remplacer les `href="URL"` par les liens réels vers les fichiers de cours et d'exercices.

## 3. Périmètre Fonctionnel Détaillé : Les Quiz (QCM)

Les pages de quiz (ex: `Quiz de révision de seconde.html`) implémentent un module interactif de Questions à Choix Multiples (QCM) avec classement.

| Fonctionnalité | Description Détaillée |
| :--- | :--- |
| **Affichage du Quiz** | Présentation d'une série de questions avec des options de réponse radio (QCM). |
| **Validation** | Bouton **"Valider mes réponses"** pour calculer le score. |
| **Affichage du Résultat** | Affiche le score sous forme de points (`X/Total`), un pourcentage de réussite, et un commentaire d'évaluation (`Excellent`, `Good`, `Average`, etc.). |
| **Explications** | Chaque question doit disposer d'un bouton pour **afficher/masquer une explication** de la réponse correcte. |
| **Réinitialisation** | Bouton **"Réinitialiser le quiz"** pour effacer les sélections et permettre de recommencer le quiz (avec potentiellement une régénération des questions si le quiz est dynamique). |
| **Classement (Leaderboard)** | Affichage d'un tableau des meilleurs scores comprenant : **Rang**, **Nom**, **Score** (`X/Total` et `%`), **Date** et **Commentaire**. |
| **Sauvegarde du Score** | Bouton **"Sauvegarder mon score"** pour enregistrer le résultat actuel dans le classement local. L'utilisateur doit pouvoir saisir son nom. |
| **Gestion du Classement** | Boutons pour **Afficher** / **Masquer** le classement et une fonction pour **Effacer tout le classement** (avec une demande de confirmation). |

## 4. Exigences Techniques

| Type | Exigence | Détail Technique |
| :--- | :--- | :--- |
| **Technologies** | Utilisation standard **HTML5**, **CSS3** et **JavaScript** (JS Vanilla). |
| **Stockage** | Le classement des quiz doit être géré en **local** sur le navigateur de l'utilisateur via l'API **`localStorage`**. |
| **Design/Accessibilité** | Le site doit être entièrement **Responsive Design**. Le menu de navigation principal (`.bandeau`) doit se transformer en **"menu burger"** (`.menu-btn`) sur les petits écrans (tablettes et mobiles, généralement sous `768px`). |
| **CSS** | Les fichiers sources contiennent un mélange de styles **CSS inline** et de blocs `<style>`. Une refonte pour utiliser des **fichiers CSS externes** est fortement recommandée pour la maintenabilité. |
| **Ressources** | Les images de fond (`background-image: url(...)`) sont souvent liées à des sites tiers (ex: `freepik.com`, `flickr.com`). **S'assurer des droits d'utilisation** et idéalement **héberger les images en local**. |

## 5. Exigences de Maintenance et Évolution

1.  **Ajout de Contenu :** Le site doit permettre l'ajout facile de nouveaux cours, exercices et questions de quiz pour chaque niveau sans nécessiter de modification majeure du code JavaScript.
2.  **Séparation des Données :** Pour les QCM, les questions, réponses et explications devraient être stockées dans un **fichier de données séparé** (ex : JSON ou fichier JS dédié) pour faciliter les mises à jour et la lisibilité.
