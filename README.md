# Restalo
 
[![CI - Restalo](https://github.com/A25-Restalo-equipe-2/A25-Restalo-equipe-2/actions/workflows/ci.yml/badge.svg)](https://github.com/A25-Restalo-equipe-2/A25-Restalo-equipe-2/actions/workflows/ci.yml)
[![CD - Restalo](https://github.com/A25-Restalo-equipe-2/A25-Restalo-equipe-2/actions/workflows/cd.yml/badge.svg)](https://github.com/A25-Restalo-equipe-2/A25-Restalo-equipe-2/actions/workflows/cd.yml)
 
Le meilleur logiciel de réservation en restauration!
 
## 📋 Description
 
Restalo est une API REST complète pour la gestion de restaurants et de réservations. Le système permet aux propriétaires de restaurants de gérer leurs établissements, leurs capacités, leurs horaires et leurs régimes alimentaires offerts, tout en offrant aux clients la possibilité de rechercher des disponibilités et de créer des réservations.
 
## ✨ Fonctionnalités
 
### Gestion des restaurants
- Créer un restaurant
- Obtenir un restaurant
- Lister les restaurants d'un propriétaire
- Supprimer un restaurant
- Modifier la capacité d'un restaurant
- Rechercher un restaurant
- Ajouter des régimes alimentaires (Vegan, Halal, Casher, Végétarien)
 
### Gestion des réservations
- Créer une réservation
- Obtenir une réservation
- Rechercher une réservation
- Configurer une réservation
- Supprimer une réservation
- Ajouter une note sur une réservation
 
### Recherche de disponibilités
- Rechercher les disponibilités d'un restaurant pour une date et plage horaire données
 
### Persistance
- Support InMemory (développement)
- Support MongoDB (production)
 
## 🚀 Prérequis
 
- Java 21
- Maven 3.x
- Docker & Docker Compose (optionnel, pour MongoDB)
 
## 📦 Installation
 
### Cloner le projet
```bash
git clone https://github.com/A25-Restalo-equipe-2/A25-Restalo-equipe-2.git
cd A25-Restalo-equipe-2
```
 
### Compilation
```bash
mvn compile
```
 
### Exécution des tests
```bash
mvn test
```
 
## 🏃 Exécution
 
### Option 1: Exécution locale (InMemory)
```bash
mvn exec:java
```
 
L'API sera disponible sur `http://localhost:8080`
 
### Option 2: Exécution avec Docker Compose (MongoDB)
```bash
docker-compose up
```
 
L'API sera disponible sur `http://localhost:8080` avec persistance MongoDB.
 
### Option 3: Utiliser l'image Docker publiée
```bash
docker pull ghcr.io/a25-restalo-equipe-2/a25-restalo-equipe-2:latest
docker run -p 8080:8080 ghcr.io/a25-restalo-equipe-2/a25-restalo-equipe-2:latest
```
 
## 🏗️ Architecture
 
Le projet suit une architecture en couches:
 
```
src/main/java/ca/ulaval/glo2003/
├── restaurants/
│   ├── api/          # Endpoints REST
│   ├── application/  # Logique métier (Services)
│   ├── domain/       # Entités du domaine
│   └── infra/        # Repositories (InMemory, MongoDB)
├── reservations/
│   ├── api/
│   ├── application/
│   ├── domain/
│   └── infra/
├── mongo/            # Documents MongoDB
└── persistence/      # Configuration de la persistance
```
 
## 🧪 Tests
 
Le projet utilise JUnit 5 et inclut:
- Tests unitaires
- Tests d'intégration (Jersey Test Framework)
- Tests de persistance (InMemory et MongoDB)
 
```bash
# Exécuter tous les tests
mvn test
 
# Générer le rapport de couverture
mvn jacoco:report
```
 
## 📚 Documentation API
 
### Endpoints principaux
 
**Restaurants:**
- `POST /restaurants` - Créer un restaurant
- `GET /restaurants/{id}` - Obtenir un restaurant
- `GET /restaurants` - Lister les restaurants d'un propriétaire
- `DELETE /restaurants/{id}` - Supprimer un restaurant
- `PUT /restaurants/{id}/capacity` - Modifier la capacité
- `POST /restaurants/{id}/diets` - Ajouter des régimes alimentaires
- `GET /restaurants/{id}/availabilities` - Rechercher les disponibilités
- `POST /search/restaurants` - Rechercher des restaurants
 
**Réservations:**
- `POST /restaurants/{id}/reservations` - Créer une réservation
- `GET /reservations/{number}` - Obtenir une réservation
- `GET /restaurants/{id}/reservations` - Rechercher des réservations
- `DELETE /reservations/{number}` - Supprimer une réservation
 
**Santé:**
- `GET /health` - Vérifier l'état de l'API
 
## 🤝 Contribution
 
Nous accueillons les contributions! Veuillez consulter notre [guide de contribution](CONTRIBUTING.md) pour plus de détails.
 
Avant de contribuer, veuillez lire:
- [Code de conduite](CODE_OF_CONDUCT.md)
- [Guide de contribution](CONTRIBUTING.md)
- [Licence](LICENSE)
 
## 📄 Licence
 
Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
 
## 👥 Équipe
 
 
## 📞 Support
 
Pour toute question ou problème, veuillez ouvrir une issue sur GitHub.
 
---
 
**Université Laval - IFT-3003- Méthodologies de développement logiciel Automne 2025**
