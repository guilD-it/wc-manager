# WC Manager

Application de suivi de la Coupe du monde de football 2026, developpee dans le cadre d'un mini-projet de formation en conception et developpement d'applications informatiques.

## Presentation

Ce projet a pour objectif de placer les apprenants dans une situation proche d'un projet reel, avec des contraintes de temps, d'organisation, de qualite et de maintenabilite.

L'application devra permettre de suivre l'ensemble de la Coupe du monde 2026, depuis la phase de groupes jusqu'a la finale, avec une experience comparable aux solutions proposees par Google, les sites sportifs ou les applications mobiles specialisees.

Le projet couvre les phases suivantes :

- Phase de groupes
- Seiziemes de finale
- Huitiemes de finale
- Quarts de finale
- Demi-finales
- Petite finale
- Finale

## Objectifs

L'application devra permettre a un utilisateur de :

- Consulter les matchs de la Coupe du monde 2026
- Visualiser les resultats, les scores et les informations associees
- Suivre l'evolution de la competition en temps reel
- Parcourir les differents tours de la competition
- Consulter les classements des groupes
- Suivre les equipes qualifiees pour les phases finales
- Acceder aux details d'un match : equipes, date, heure, stade, score, statut et evenement important

Les donnees affichees devront etre dynamiques et pouvoir se mettre a jour automatiquement afin de simuler ou d'assurer un suivi en temps reel de la competition.

## Technologies principales

Le projet sera construit autour de deux technologies principales :

### Backend

- **Spring Boot** : developpement de l'API REST
- **Spring Web** : exposition des endpoints HTTP
- **Spring Data JPA** : acces aux donnees
- **Base de donnees relationnelle** : stockage des equipes, matchs, groupes, scores et phases
- **Validation** : controle des donnees recues par l'API

### Frontend

- **Next.js** : interface utilisateur moderne basee sur React
- **React** : construction des composants d'interface
- **TypeScript** : typage du code frontend
- **CSS / Tailwind CSS** : mise en forme de l'application
- **Fetch API ou Axios** : communication avec le backend

## Fonctionnalites prevues

### Consultation des matchs

- Liste complete des matchs de la competition
- Filtrage par phase : groupes, seiziemes, huitiemes, quarts, demi-finales, petite finale, finale
- Filtrage par equipe
- Filtrage par date
- Affichage du statut du match : a venir, en cours, termine

### Details d'un match

- Equipes participantes
- Date et heure du match
- Stade
- Phase de la competition
- Score en direct ou score final
- Statut du match
- Informations complementaires : prolongation, tirs au but, cartons, buteurs ou evenements importants selon l'avancement du projet

### Resultats et scores

- Mise a jour des scores
- Affichage des resultats finaux
- Gestion des scores de prolongation
- Gestion des tirs au but pour les matchs a elimination directe

### Phase de groupes

- Affichage des groupes
- Classement des equipes par groupe
- Points, victoires, nuls, defaites
- Buts marques, buts encaisses, difference de buts
- Qualification vers la phase finale

### Phase finale

- Tableau des matchs a elimination directe
- Progression des equipes qualifiees
- Affichage des vainqueurs de chaque tour
- Gestion de la petite finale et de la finale

### Suivi en temps reel

- Actualisation automatique des donnees
- Recuperation periodique des matchs et scores
- Possibilite d'afficher les matchs en cours
- Interface adaptee au suivi rapide de la competition

### Administration des donnees

Selon le niveau attendu du projet, une partie administration pourra etre ajoutee pour :

- Gerer les equipes
- Gerer les groupes
- Creer ou modifier les matchs
- Mettre a jour les scores
- Changer le statut d'un match
- Renseigner les informations detaillees d'une rencontre

## Structure cible du projet

Le projet pourra etre organise sous forme de monorepo contenant une application backend et une application frontend.

```text
wc-manager/
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── .../
│   │   │   │       ├── controller/
│   │   │   │       ├── service/
│   │   │   │       ├── repository/
│   │   │   │       ├── model/
│   │   │   │       ├── dto/
│   │   │   │       └── config/
│   │   │   └── resources/
│   │   │       ├── application.properties
│   │   │       └── data.sql
│   │   └── test/
│   └── pom.xml
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── lib/
│   ├── types/
│   ├── public/
│   ├── package.json
│   └── next.config.js
│
└── README.md
```

## Architecture applicative

### Backend Spring Boot

Le backend sera responsable de :

- Exposer les donnees via une API REST
- Gerer les entites metier : equipes, groupes, matchs, scores, phases
- Calculer les classements des groupes
- Determiner les qualifications
- Fournir les donnees necessaires au frontend
- Valider et securiser les operations de mise a jour

Exemples d'endpoints possibles :

```text
GET    /api/teams
GET    /api/groups
GET    /api/groups/{id}/standings
GET    /api/matches
GET    /api/matches/{id}
GET    /api/matches?phase=GROUP_STAGE
PATCH  /api/matches/{id}/score
PATCH  /api/matches/{id}/status
```

### Frontend Next.js

Le frontend sera responsable de :

- Afficher les matchs et resultats
- Proposer une navigation claire entre les phases
- Afficher les classements et tableaux de qualification
- Consommer l'API Spring Boot
- Mettre a jour automatiquement les donnees visibles
- Fournir une interface responsive utilisable sur ordinateur, tablette et mobile

Pages possibles :

```text
/
/matches
/matches/[id]
/groups
/groups/[id]
/knockout
/teams
/admin
```

## Modele de donnees previsionnel

Entites principales envisagees :

- **Team** : represente une equipe nationale
- **Group** : represente un groupe de la phase de groupes
- **Match** : represente une rencontre
- **Stadium** : represente un stade
- **Score** : represente le score d'un match
- **Standing** : represente une ligne de classement
- **Phase** : represente une phase de competition
- **MatchEvent** : represente un evenement de match, comme un but ou un carton

## Qualite attendue

Le projet devra respecter plusieurs principes de qualite :

- Code lisible et organise
- Separation claire entre frontend et backend
- API REST documentee et coherente
- Gestion correcte des erreurs
- Donnees dynamiques
- Interface simple, claire et responsive
- Tests unitaires ou tests d'integration selon l'avancement
- README complet permettant de comprendre et lancer le projet

## Lancement du projet

Les commandes de lancement seront completees lorsque les applications backend et frontend seront creees.

Exemple attendu :

```bash
# Backend
cd backend
./mvnw spring-boot:run

# Frontend
cd frontend
npm install
npm run dev
```

## Etat du projet

Le projet est en phase de conception initiale. Le README sert de base de cadrage pour presenter le besoin, les choix techniques, l'architecture cible et les fonctionnalites attendues.
