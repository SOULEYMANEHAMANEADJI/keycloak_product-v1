# README du Projet ProductApp

## Introduction
**ProductApp** est une application web développée avec **Spring Boot** et **Spring MVC**. Elle permet de gérer une liste de produits en interagissant avec une base de données, tout en intégrant la sécurité via **Keycloak**. Ce projet est un exemple d'application sécurisée utilisant des technologies modernes.

## Informations sur le projet
- **Nom du projet**: ProductApp
- **Groupe**: com.isi.mvc
- **Version**: 0.0.1-SNAPSHOT
- **Description**: Projet 2 sur la sécurité des applications : Keycloak
- **Java Version**: 17

## Prérequis
Avant de commencer, assurez-vous d'avoir installé les outils suivants :
- **Java JDK** (version 17 ou supérieure)
- **Maven** (version 3.6 ou supérieure)
- **IntelliJ IDEA** (ou un autre IDE de votre choix)
- **Serveur de bases de données** (ex. MySQL ou PostgreSQL)
- **Keycloak** pour la gestion de la sécurité

## Installation
1. **Clonez le dépôt du projet :**
   ```bash
  git clone https://votre-repo.git](https://github.com/SOULEYMANEHAMANEADJI/keycloak_product-v1.git
   ```

2. **Ouvrez le projet dans IntelliJ IDEA.**

3. **Construisez le projet :**
   Ouvrez le terminal dans IntelliJ et exécutez :
   ```bash
   mvn clean install
   ```

4. **Configurez la base de données :**
   - Créez une base de données pour l’application.
   - Mettez à jour le fichier `application.properties` ou la configuration de votre connexion JDBC pour pointer vers votre base de données.

## Dépendances
Le projet utilise plusieurs dépendances pour fonctionner correctement :

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
        <version>2.2.3.RELEASE</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-thymeleaf</artifactId>
        <version>2.2.3.RELEASE</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>2.2.3.RELEASE</version>
    </dependency>
    <dependency>
        <groupId>org.keycloak</groupId>
        <artifactId>keycloak-spring-boot-starter</artifactId>
        <version>24.0.4</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-security</artifactId>
        <version>3.0.6</version>
    </dependency>
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.30</version>
    </dependency>
    <dependency>
        <groupId>org.webjars</groupId>
        <artifactId>bootstrap</artifactId>
        <version>5.3.3</version>
    </dependency>
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <optional>true</optional>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

## Configuration de la base de données
La classe `Product` est définie de la manière suivante :
```java
package com.example.model;

public class Product {
    private String ref;
    private String name;

    // Constructeurs, getters et setters
}
```
Assurez-vous de créer une table `Product` dans votre base de données avec les colonnes appropriées.

## Sécurité avec Keycloak
Pour sécuriser l’application à l'aide de Keycloak :
1. **Installez Keycloak** et démarrez le serveur.
2. **Créez un nouveau Realm** et un client pour votre application.
3. Ajoutez des rôles nécessaires pour gérer les accès.
4. Configurez le fichier `application.properties` pour inclure les détails de Keycloak, tels que l'URL du serveur, le Realm et le client.

Exemple de configuration dans `application.properties` :
```properties
keycloak.auth-server-url=http://localhost:8080/auth
keycloak.realm=VotreRealm
keycloak.resource=VotreClient
keycloak.public-client=true
```

## Démarrage de l'application
Pour démarrer l'application, exécutez :
```bash
mvn spring-boot:run
```
Ou déployez sur votre serveur d'application pris en charge.

## Utilisation
- Accédez à l'application via `http://localhost:8080/ProductApp`.
- Ajoutez des produits via le formulaire prévu à cet effet.
- Visualisez la liste des produits ajoutés.

## Conclusion
Cette application constitue une introduction à la gestion des produits avec Spring MVC et à l’intégration de Keycloak pour la sécurité. Vous pouvez l'étendre en ajoutant d'autres fonctionnalités comme la mise à jour et la suppression de produits, ainsi que des tests automatisés.

## Auteurs
- SHA
