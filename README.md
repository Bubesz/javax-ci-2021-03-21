# CI/CD oktatás

Build

```
gradlew build
gradlew -q dependencies 
gradlew dependencyUpdates
```

Spring Boot alkalmazás

```
gradlew bootRun
```

Elérhető:

http://localhost:8080/swagger-ui.html

```
gradlew test
```

Integrációs tesztek után:

```
gradlew test assemble
gradlew -i test assemble
gradlew integrationTest
```

MariaDB indítása:

```
docker run -d   
    -e MYSQL_DATABASE=employees    
    -e MYSQL_USER=employees    
    -e MYSQL_PASSWORD=employees    
    -e MYSQL_ALLOW_EMPTY_PASSWORD=yes   
    -p 3306:3306      
    --name employees-mariadb
    mariadb
```

Integrációs tesztek futtatása MariaDB-n:

```
gradlew clean -i 
    -Pspring.datasource.url=jdbc:mariadb://localhost/employees 
    -Pspring.datasource.username=employees 
    -Pspring.datasource.password=employees  integrationTest
```