# Api-Employee

API REST pour la gestion des employés, développée avec **Spring Boot**.

## Fonctionnalités principales

- CRUD sur les employés (`GET`, `POST`, `PUT`, `DELETE`)
- Gestion des départements et des postes
- Recherche et filtrage

## Prérequis

- **Java 17**+
- **Maven** ou **Gradle**
- Base de données (ex : MySQL, PostgreSQL)

## Installation

Clone le projet :
```bash
git clone https://github.com/Berlin-40/Api-Employee.git
cd Api-Employee
```
Il faudra une bd mysql avec un Table employees
Configure les paramètres de la base de données dans le fichier `src/main/resources/application.properties` :
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/nom_de_la_bdd
spring.datasource.username=utilisateur
spring.datasource.password=motdepasse
spring.jpa.hibernate.ddl-auto=update
```

Compile et lance l'application :
```bash
./mvnw spring-boot:run
```
ou
```bash
gradle bootRun
```

L’API sera dispo sur [http://localhost:9080](http://localhost:9080).

## Endpoints principaux

| Méthode | Endpoint              | Description                       |
| ------- | --------------------- | --------------------------------- |
| GET     | `/employees`          | Liste tous les employés           |
| GET     | `/employees/{id}`     | Détails d’un employé              |
| POST    | `/employees`          | Créer un nouvel employé           |
| PUT     | `/employees/{id}`     | Met à jour un employé existant    |
| DELETE  | `/employees/{id}`     | Supprimer un employé              |

## Exemple de requête

```bash
curl -X POST http://localhost:9080/employees \
  -H 'Content-Type: application/json' \
  -d '{"nom": "Jean Dupont", "poste": "Développeur", "departement": "IT"}'
```

## Documentation Swagger

Si Swagger est intégré, accède à la documentation interactive ici :
[http://localhost:9080/swagger-ui.html](http://localhost:9080/swagger-ui.html)

---

© 2025 Berlin-40
