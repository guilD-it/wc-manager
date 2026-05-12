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

## Processus Git et approche DevOps

Le projet utilisera une organisation Git simple avec trois branches principales :

- **dev** : branche de developpement principale
- **test** : branche de validation avant livraison
- **main** : branche stable, correspondant a la version livrable

### Role des branches

#### Branche `dev`

La branche `dev` est la seule branche sur laquelle les developpeurs peuvent pousser directement du code.

Elle sert a integrer les nouvelles fonctionnalites, les corrections et les evolutions en cours de developpement.

Exemples :

```bash
git checkout dev
git pull origin dev
git add .
git commit -m "feat: add match listing"
git push origin dev
```

#### Branche `test`

La branche `test` sert a valider une version candidate avant la livraison finale.

Les changements arrivent sur `test` uniquement via une Pull Request depuis `dev`.

Objectifs de cette branche :

- Executer la CI dans un contexte de validation
- Tester les fonctionnalites integrees
- Verifier que le backend et le frontend fonctionnent ensemble
- Corriger les anomalies avant passage en production

#### Branche `main`

La branche `main` contient uniquement le code stable et livre.

Aucun commit direct ne doit etre fait sur `main`. Les changements arrivent uniquement via une Pull Request depuis `test`, apres validation.

### Flux de travail recommande

Le flux Git recommande est le suivant :

```text
dev  ->  test  ->  main
```

1. Les developpeurs travaillent sur `dev`.
2. La CI s'execute automatiquement sur `dev`.
3. Quand une version est prete, une Pull Request est creee de `dev` vers `test`.
4. La CI s'execute sur la Pull Request et sur la branche `test`.
5. Apres validation, une Pull Request est creee de `test` vers `main`.
6. La CI s'execute sur la Pull Request et sur la branche `main`.
7. La branche `main` represente la version stable du projet.

### Regles de protection GitHub recommandees

Dans GitHub, il est recommande de configurer les regles suivantes dans :

```text
Settings > Branches > Branch protection rules
```

#### Protection de `main`

- Interdire les commits directs
- Exiger une Pull Request avant merge
- Exiger que la CI soit en succes avant merge
- Exiger au moins une validation de Pull Request
- Interdire le force push
- Interdire la suppression de la branche

#### Protection de `test`

- Interdire les commits directs
- Exiger une Pull Request depuis `dev`
- Exiger que la CI soit en succes avant merge
- Interdire le force push
- Interdire la suppression de la branche

#### Branche `dev`

- Autoriser les commits directs des membres de l'equipe
- Executer la CI a chaque push
- Interdire le force push si possible

### Integration continue

La CI devra s'executer automatiquement sur les trois branches :

- `dev`
- `test`
- `main`

Evenements recommandes :

- A chaque `push` sur `dev`, `test` ou `main`
- A chaque Pull Request vers `test` ou `main`

Le pipeline CI pourra contenir les etapes suivantes :

- Recuperation du code
- Installation des dependances frontend
- Verification du build Next.js
- Execution des tests frontend
- Installation des dependances backend
- Execution des tests Spring Boot
- Verification du build backend

Exemple de workflow GitHub Actions cible :

```yaml
name: CI

on:
  push:
    branches:
      - dev
      - test
      - main
  pull_request:
    branches:
      - test
      - main

jobs:
  backend:
    name: Backend CI
    runs-on: ubuntu-latest
    if: ${{ hashFiles('backend/pom.xml') != '' }}

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Java
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '21'

      - name: Run backend tests
        working-directory: backend
        run: ./mvnw test

  frontend:
    name: Frontend CI
    runs-on: ubuntu-latest
    if: ${{ hashFiles('frontend/package.json') != '' }}

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: npm
          cache-dependency-path: frontend/package-lock.json

      - name: Install dependencies
        working-directory: frontend
        run: npm ci

      - name: Run frontend tests
        working-directory: frontend
        run: npm test

      - name: Build frontend
        working-directory: frontend
        run: npm run build
```

Ce workflow pourra etre place dans :

```text
.github/workflows/ci.yml
```

### Convention de commits

Pour garder un historique clair, le projet peut utiliser une convention de commits inspiree de Conventional Commits :

```text
feat: ajouter la liste des matchs
fix: corriger le calcul du classement
docs: mettre a jour le README
test: ajouter les tests des services
refactor: simplifier la gestion des scores
ci: ajouter le workflow GitHub Actions
```

### Resume du processus

```text
Developpement quotidien : dev
Validation fonctionnelle : test
Version stable : main
CI automatique : dev, test, main
Commits directs : uniquement sur dev
Pull Requests obligatoires : dev -> test, test -> main
```

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
