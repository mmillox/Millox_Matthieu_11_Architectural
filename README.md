# Millox_Matthieu_11_Architectural

Il s'agit du repository contentant les documents d'architecture concernant le projet 11.

## Table des matières

* [Données de référence sur les spécialités NHS](https://github.com/mmillox/Millox_Matthieu_11_Architectural/blob/main/Donn%C3%A9es%20de%20r%C3%A9f%C3%A9rence%20sur%20les%20sp%C3%A9cialit%C3%A9s%20NHS.pdf)
* [Document de définition de l'architecture](https://github.com/mmillox/Millox_Matthieu_11_Architectural/blob/main/Document%20de%20d%C3%A9finition%20de%20l_architecture.pdf)
* [Déclaration des travaux d’architecture.pdf](https://github.com/mmillox/Millox_Matthieu_11_Architectural/blob/main/D%C3%A9claration%20des%20travaux%20d%E2%80%99architecture.pdf)
* [Exigences pour le développement de la POC.pdf](https://github.com/mmillox/Millox_Matthieu_11_Architectural/blob/main/Exigences%20pour%20le%20de%CC%81veloppement%20de%20la%20PoC.pdf)
* [Principes de l'architecture](https://github.com/mmillox/Millox_Matthieu_11_Architectural/blob/main/Principes%20de%20l_architecture.pdf)

# Constat
## Fonctionnalités
Ce POC permet aux utilisateurs, après s'être connectés via une interface de login ou d'inscription, de rechercher les hôpitaux les plus proches en fonction de leur adresse et de la spécialité médicale recherchée (comme cardiologie, etc.). La liste des hôpitaux est générée à partir des données fournies par le NHS via un fichier CSV, avec les spécialités simulées pour l'exemple. Les données réelles pourront être intégrées ultérieurement à partir d'un service externe.

## Choix techniques
L'API backend est développée en suivant les principes REST et SOLID, utilisant une pile technologique Java avec Spring Boot pour la gestion des microservices. L'interface utilisateur est construite avec React et interagit directement avec nos API backend. Le code source est versionné avec Git, en suivant un workflow défini. L'application est conteneurisée avec Docker, où chaque service (deux services backend : auth et road, un service frontend, et un pour MongoDB) génère ses propres images et conteneurs Docker.

## Performance
Pour une charge de 800 utilisateurs sur une seule instance, les temps de réponse par requête varient entre 4000 ms et 40000 ms. Les tests de performance et de montée en charge sont réalisés avec JMETER.

## Protection des données
L'API proposée dans ce POC n'utilise pas de données patient. L'accès à l'application est sécurisé par une authentification de type Basic Auth, fournie par Spring Security.

## CI/CD
Un système de CI/CD a été mis en place pour automatiser l'exécution des tests et le déploiement des artefacts de production. Les standards pour l'utilisation de la CI sont documentés dans le repository.
