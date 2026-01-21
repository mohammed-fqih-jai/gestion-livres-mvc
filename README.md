# Gestion de Livres - Application MVC avec Servlets et JSP

## Description
Application CRUD de gestion de livres développée en Java utilisant l'architecture MVC avec Servlets, JSP, Filtres et MySQL.

## Fonctionnalités
- **Authentification** : Système de login avec deux rôles (Admin et Visiteur)
- **Gestion des livres** : Création, lecture, modification et suppression des livres
- **Gestion des auteurs** : Association des livres aux auteurs
- **Recherche** : Recherche de livres par titre, auteur ou éditeur
- **Contrôle d'accès** : Filtres pour vérifier l'authentification et les permissions
- **Interface responsive** : Interface utilisateur moderne et intuitive

## Architecture
- **Modèle (Model)** : Classes Livre, Auteur, Utilisateur et leurs DAOs
- **Vue (View)** : Pages JSP pour l'affichage
- **Contrôleur (Controller)** : Servlets pour traiter les requêtes
- **Filtres** : FrontFilter et AuthenticationFilter pour la gestion centralisée

## Prérequis
- JDK 17 ou supérieur
- MySQL 8.x
- Maven 3.6+
- Serveur d'application (Tomcat 10+, WildFly 26+, etc.)

## Installation

### 1. Configuration de la base de données
```sql
-- Exécuter le script schema.sql
mysql -u root < schema.sql
```

### 2. Configuration du projet
Modifier les paramètres de connexion dans `DatabaseConnection.java` si nécessaire :
```java
private static final String URL = "jdbc:mysql://localhost:3306/gr1Tp1Db";
private static final String USER = "root";
private static final String PASSWORD = "";
```

### 3. Compilation et packaging
```bash
mvn clean package
```

### 4. Déploiement
Copier le fichier `gr1Tp1.war` généré dans le répertoire `target/` vers le dossier `webapps/` du serveur d'application.

## Utilisation

### Comptes de démonstration
- **Admin** : login: `admin` / mot de passe: `admin123`
- **Visiteur** : login: `visiteur` / mot de passe: `visiteur123`

### Accès à l'application
```
http://localhost:8080/gr1Tp1
```

## Structure du projet
```
src/main/java/com/isga/gestion/
├── model/
│   ├── Auteur.java
│   ├── AuteurDAO.java
│   ├── Livre.java
│   ├── LivreDAO.java
│   ├── Utilisateur.java
│   └── UtilisateurDAO.java
├── servlet/
│   ├── LoginServlet.java
│   ├── LogoutServlet.java
│   ├── LivreListServlet.java
│   ├── LivreFormServlet.java
│   └── LivreDeleteServlet.java
├── filter/
│   ├── FrontFilter.java
│   └── AuthenticationFilter.java
└── util/
    └── DatabaseConnection.java

src/main/webapp/
├── WEB-INF/
│   ├── views/
│   │   ├── login.jsp
│   │   ├── livre-list.jsp
│   │   └── livre-form.jsp
│   └── web.xml
```

## Permissions par rôle

| Fonctionnalité | Admin | Visiteur |
|---|---|---|
| Consulter la liste des livres | ✓ | ✓ |
| Rechercher des livres | ✓ | ✓ |
| Ajouter un livre | ✓ | ✗ |
| Modifier un livre | ✓ | ✗ |
| Supprimer un livre | ✓ | ✗ |
## screen 

<img width="1915" height="966" alt="image" src="https://github.com/user-attachments/assets/423db417-619f-48a3-b57e-85d53424e4f4" />

<img width="1913" height="817" alt="image" src="https://github.com/user-attachments/assets/e2d32f7c-6b0f-4023-91b2-ab441d7e66f5" />



## Technologies utilisées
- Java 17
- Jakarta Servlet 6.0
- Jakarta JSP 3.1
- JSTL 3.0
- MySQL 8.0
- Maven 3.6+

## Notes
- L'application utilise PreparedStatements pour prévenir les injections SQL
- Les sessions sont utilisées pour gérer l'authentification
- Les filtres assurent la sécurité et la gestion centralisée des requêtes
- L'interface est responsive et compatible avec les navigateurs modernes

## Auteur
Projet d'examen - Architecture JEE - ISGA Casablanca
