# 🅿️ Smart Parking IoT — Système de Stationnement Intelligent

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![IoT](https://img.shields.io/badge/plateforme-IoT-orange.svg)
![Java](https://img.shields.io/badge/langage-Java-red.svg)

**Une solution innovante de gestion de parking utilisant l’Internet des Objets (IoT)**

</div>

---

## 📖 Table des Matières
- [🎯 Aperçu du Projet](#-aperçu-du-projet)
- [🚀 Fonctionnalités](#-fonctionnalités)
- [🛠️ Technologies Utilisées](#️-technologies-utilisées)
- [🏗️ Architecture du Système](#️-architecture-du-système)
- [📦 Installation](#-installation)
- [🎮 Utilisation](#-utilisation)
- [🔧 Configuration](#-configuration)
- [👥 Auteur](#-auteur)
- [📄 Licence](#-licence)

---

## 🎯 Aperçu du Projet

Le **Smart Parking IoT** est une solution intelligente de gestion de stationnement exploitant les technologies **IoT** pour faciliter la recherche et la gestion des places de parking en temps réel.  
Grâce à une **application web intuitive**, les utilisateurs peuvent consulter la disponibilité des places, effectuer des réservations et recevoir des alertes de sécurité.

### 🌟 Problématiques Résolues
- ✅ Recherche rapide des places disponibles  
- ✅ Réduction du temps de stationnement  
- ✅ Économie de carburant et réduction de la pollution  
- ✅ Sécurité renforcée (détection de gaz)  
- ✅ Gestion optimisée et centralisée du parking  

---

## 🚀 Fonctionnalités

### 🔑 Principales
- 🔐 **Authentification sécurisée** des utilisateurs  
- 📊 **Visualisation en temps réel** des places (libre / occupée / réservée)  
- 📅 **Réservation en ligne** via l’application web  
- 🚨 **Détection de fuites de gaz** avec alarme sonore  
- 📱 **Interface responsive** accessible sur tous les appareils  

### 💡 Indications Visuelles
| Couleur | Signification |
|----------|---------------|
| 🟢 LED Verte | Place disponible |
| 🔴 LED Rouge | Place occupée |
| 🔵 LED Bleue | Place réservée |
| 📟 LCD | Affichage des informations en temps réel |

---

## 🛠️ Technologies Utilisées

### 💻 **Matériel (Hardware)**
| Composant | Description |
|-----------|-------------|
| **Arduino Uno** | Microcontrôleur principal |
| **Capteur Ultrason HC-SR04** | Détection de présence véhicule |
| **Capteur de Gaz MQ-2** | Détection de fuites de gaz |
| **Afficheur LCD** | Informations du parking |
| **LEDs (Rouge/Vert/Bleu)** | Indicateurs visuels |
| **Buzzer** | Alerte sonore |
| **Breadboard** | Prototypage des circuits |

### 🌐 **Logiciel (Software)**
| Technologie | Utilisation |
|-------------|-------------|
| **Java / Java EE** | Backend de l’application |
| **HTML / CSS / JavaScript** | Interface web |
| **MySQL** | Base de données |
| **Node-RED** | Communication IoT |
| **Arduino IDE** | Programmation des capteurs |
| **Apache Tomcat** | Serveur web |
| **Eclipse IDE** | Développement et déploiement |

---

## 🏗️ Architecture du Système

```mermaid
graph TD
    A[Capteurs Ultrason] --> B[Arduino Uno]
    C[Capteur Gaz MQ-2] --> B
    D[LEDs Indicateurs] --> B
    B --> E[Node-RED]
    E --> F[Base de Données MySQL]
    F --> G[Application Web]
    G --> H[Utilisateur Final]

## 📋 Description des Couches

Couche Capteurs → collecte de données en temps réel

Couche Contrôleur → traitement via Arduino & Node-RED

Couche Données → stockage dans MySQL

Couche Application → interface web utilisateur

Couche Sécurité → authentification & système d’alerte
---

##  📦 Installation
### ⚙️ Prérequis

Arduino IDE 1.8.x ou supérieur

Java JDK 8+

Apache Tomcat 9+

MySQL 5.7+

Node-RED

🧩 Étapes d’Installation
1️⃣ Cloner le dépôt
git clone https://github.com/votre-utilisateur/smart-parking-iot.git
cd smart-parking-iot

2️⃣ Configuration de la base de données
CREATE DATABASE smart_parking;
USE smart_parking;
SOURCE database/schema.sql;

3️⃣ Configuration Arduino

Ouvrir arduino/smart_parking.ino dans Arduino IDE

Configurer les pins selon le montage

Téléverser sur la carte Arduino

4️⃣ Déploiement de l’application web
mvn clean install
cp target/smartparking.war $TOMCAT_HOME/webapps/

5️⃣ Configuration Node-RED

Importer node-red/smart-parking-flow.json

Configurer les connexions MQTT/HTTP

🎮 Utilisation
👤 Utilisateur

Accéder à l’application : http://localhost:8080/smartparking

Créer un compte / se connecter

Consulter les places disponibles

Réserver une place libre

Stationner et visualiser les alertes en temps réel

🛠️ Administrateur

Suivre l’état du parking en temps réel

Gérer les réservations

Recevoir les alertes de sécurité

Analyser les statistiques d’utilisation

🔧 Configuration
⚙️ Fichier database.properties
db.url=jdbc:mysql://localhost:3306/smart_parking
db.username=your_username
db.password=your_password

⚙️ Fichier arduino.properties
arduino.port=COM3
arduino.baudrate=9600

⚙️ Fichier email.properties
email.host=smtp.gmail.com
email.port=587
email.username=your_email@gmail.com
email.password=your_password

⚡ Configuration des Pins Arduino
const int trigPin = 9;
const int echoPin = 10;
const int gasSensor = A0;
const int redLed = 2;
const int greenLed = 3;
const int blueLed = 4;
const int buzzer = 5;

👥 Auteur

👩‍💻 Zineb Drissi
🎓 Licence Sciences Mathématiques et Informatique
📍 Faculté des Sciences Ben M’Sick — Promotion 2023/2024

📄 Licence

Projet académique réalisé dans le cadre d’un projet de fin d’études.
Licence MIT — libre d’utilisation à des fins éducatives.