# 📚 Gestion de Parking

---

## 📁 Table de matieres

- [🗂 Contexte](#-Contexte)
- [❓ Problématique](#-Problématique)
- [🎯 Objectif](#-Objectif)
- [📊 Diagrammes](#-Diagrammes)
- [🗃 Tables de Données](#-Tables-de-Données)
- [✨ Fonctionnalités Principales](#-Fonctionnalités-Principales)
- [🔍 Requêtes SQL](#-Requêtes-sql)
- Architecture
- [🛠 Technologies Utilisées](#-Technologies-Utilisées)
- [🎥 Démo Vidéo](#-Démo-video)

---
## 🗂 Contexte :

Dans le domaine de la gestion des parkings, l'organisation efficace des places de stationnement, le suivi des véhicules et la gestion des entrées/sorties sont essentiels pour assurer un service fluide et éviter les conflits d'occupation.
Les méthodes traditionnelles basées sur des registres papier ou des fichiers Excel peuvent entraîner des erreurs, des chevauchements de réservation et une mauvaise optimisation de l'espace.
Afin d'améliorer la gestion quotidienne d'un parking, il est nécessaire de mettre en place une application informatique permettant d'automatiser les opérations principales comme la gestion des places, l'enregistrement des stationnements et le calcul automatique des montants.

---
## ❓ Problématique:

Les gestionnaires de parkings rencontrent souvent plusieurs difficultés dans leur gestion quotidienne :
- Difficulté à suivre en temps réel la disponibilité des places
- Risque de chevauchement des réservations
- Gestion manuelle des entrées/sorties peu fiable
- Calcul complexe des montants de stationnement
- Manque de centralisation des informations des véhicules
- Absence de statistiques pour analyser le taux d'occupation et les revenus
- Ces limites rendent la gestion moins efficace et compliquent la prise de décision pour optimiser l'utilisation du parking.

- ---

## 🎯 Objectif:


L'objectif de ce projet est de développer une application desktop permettant de faciliter la gestion d'un parking à travers une interface simple et intuitive.
L'application vise à :
- Gérer les places de stationnement (type, statut, tarif)
- Gérer les véhicules et leurs informations
- Enregistrer les entrées et sorties des véhicules
- Calculer automatiquement le montant dû en fonction de la durée
- Générer des statistiques sur le taux d'occupation et les revenus

---
## L'application doit :


- Permettre l'ajout, modification et suppression des places de stationnement
- Gérer les véhicules liés aux stationnements
- Enregistrer les entrées et sorties des véhicules
- Mettre à jour automatiquement le statut des places après chaque stationnement
- Afficher les statistiques (ex : taux d'occupation, revenus par période)

---

## 📊 Diagrammes :
---

##  Diagramme de cas d'utilisation:


<img width="1344" height="887" alt="Screenshot (408)" src="https://github.com/user-attachments/assets/b70f0b44-1ccb-4b7a-ac2f-f9723704804f" />



---
##  Diagramme de classe :


<img width="957" height="596" alt="Screenshot (409)" src="https://github.com/user-attachments/assets/faa47df9-0609-4ffe-94c5-b9a7b0347453" />

---
## 🗃 Tables de Données:
---

-Place ( , numero , type , statut , tarifHoraire )

-Vehicule (  immatricule , marque , categorie )

-Stationnement( id , numero, matricule, dateEntree , dateSortie , montant )

-Utilisateur( id ,  nomUtilisateur, motDePasse , role , email,datecreation,reset-token,reset-token-expiry )

---
## ✨ Fonctionnalités Principales:


1. *Gestion des places*
---
   
Ajouter une place : Formulaire pour saisir le numéro, type (Auto/Moto/PMR), statut (Libre/Occupée) et tarif horaire

Modifier une place : Mettre à jour les informations d'une place existante

Supprimer une place : Retirer une place de la base de données

Lister les places : Afficher toutes les places dans un tableau avec leur statut en temps réel

Filtrer les places : Par type (Auto, Moto, PMR) ou par statut (Libre, Occupée)

---

2. *Gestion des véhicules*

---
   
Ajouter un véhicule : Saisie du matricule, de la marque et de la catégorie (Auto/Moto)

Modifier un véhicule : Mettre à jour les données d'un véhicule existant

Supprimer un véhicule : Retirer un véhicule de la base de données

Lister les véhicules : Afficher la liste des véhicules enregistrés

Rechercher un véhicule : Par matricule ou par marque

---

3. *Gestion des stationnements*
 
---
 
Enregistrer une entrée : Sélectionner une place libre et un véhicule, enregistrement automatique de la date/heure

Enregistrer une sortie : Calcul automatique du montant (durée × tarif) et libération de la place

Empêcher les chevauchements : Vérification qu'une place ne peut être occupée deux fois simultanément

Consulter l'historique : Afficher tous les stationnements avec leurs détails

Rechercher par matricule : Voir l'historique complet d'un véhicule spécifique

---

4. *Filtrage et recherche*
---

Filtrer les places : Par type (Auto, Moto, PMR) ou par statut (Libre, Occupée)

Filtrer les stationnements : Par période (date de début et date de fin)

Rechercher : Par matricule de véhicule dans l'historique

Filtrer les résultats : Interface intuitive avec comboBox et champs de recherche


---


5. *Statistiques*

---
 
Taux d'occupation par mois : Pourcentage de temps d'occupation des places

Revenus mensuels : Montant total perçu par mois

Statistiques par type : Occupation et revenus par type de place (camemberts)

Graphiques interactifs : Visualisation des données avec JFreeChart

---

6. *Authentification et sécurité*

---
   
Connexion sécurisée : Vérification des identifiants avec hashage BCrypt

Gestion des utilisateurs : Différents rôles (admin, user) avec permissions

Récupération de mot de passe :

Envoi d'un code à 6 chiffres par email

Validation du code (valable 15 minutes)

Réinitialisation du mot de passe

Protection des données : Aucun mot de passe stocké en clair

---

7. *Interface utilisateur*

---
   
Fenêtre principale avec menu (Gestion, Recherche, Graphes, Aide)

Fenêtres internes (JInternalFrame) pour chaque module

Barre de statut : Informations sur la connexion à la base de données

Messages de confirmation et d'erreur avec JOptionPane

Design intuitif : Couleurs apaisantes (fond rose pâle #FFCCCC)

---
##  🔍 Requêtes sql 

---

Création des tables:

---

<img width="750" height="216" alt="Screenshot (455)" src="https://github.com/user-attachments/assets/d5dded59-a001-4be2-bf2b-388b34bc0c8a" />

<img width="779" height="261" alt="Screenshot (456)" src="https://github.com/user-attachments/assets/0895672e-5922-453d-b211-a67214217cb4" />

<img width="771" height="292" alt="Screenshot (457)" src="https://github.com/user-attachments/assets/fc455e9a-4a37-498a-b23a-4dbdc1f9da83" />

<img width="771" height="292" alt="Screenshot (457)" src="https://github.com/user-attachments/assets/d652fe4b-2cf3-4a40-ab58-0136751c249b" />

---

``
🏛 Architecture

---

<img width="345" height="581" alt="Screenshot (450)" src="https://github.com/user-attachments/assets/f4b76627-0a4d-43dd-8d11-bd6445dd5cb3" />


---

## 🛠 Technologies Utilisées:
---

- **Framework d'interface graphique :** Java Swing
- **Base de données :** MySQL
- **Accès aux données :** JDBC
- **Outils de développement :**
NetBeans (IDE Java)
StarUml (Outil de diagramme)
- **Gestion de base de données :** MYSQL Workbench

- 
---
## 🎥 Démo video



https://github.com/user-attachments/assets/6b69fc47-04e2-4bdf-8f00-3582f33438e7

---
👩‍💻 Auteur
---
  AIT LECHGUEUR basma
  
  AIT ELMAHJOUB Asma


