# pperformance-docker

### Estructura de directorio

```
pperformance
    .docker
    backend
    frontend
```

- Git Clone para crear la carpeta `.docker`
    ```sh
    git clone git@github.com:alexpereap/pperformance-docker.git .docker
    ```
 - Git Clone para crear la carpeta `source`
    ```sh
    git clone git@github.com:alexpereap/pperformance-backend.git backend
    ```
### Compilación
 - Preparativos:
     - Haber creado un alias en el archivo hosts para redireccionar `pperfornabce.local` a `127.0.0.1`.
     - Docker ejecutandose en el sistema.

- Ejecutar:

    ```sh
    # En el folder .docker
    cd .docker
    
    # correr imagen
    docker-compose up --build
    
    ```
- Instalar librerias composer código fuente
    ```sh
    docker exec -it perea_performance_dev-backend-1 sh
    composer install
    ``` 
### Troubleshooting
Ejecutando dentro del folder .docker
  - Reconstruir imagen
    ```sh
    docker-compose-up --build --force-recreate
    ``` 
  - Reinstalar imagen (probablemente solución a la mayoria de problemas)
     ```sh
    docker-compose down --rmi all
    docker-compose up --build
    ``` 
  - Problemas descargando librerias: En caso de errores de red descargando las librerias usar los DNS de google en la configuración de red del sistema:
    ```
    8.8.8.8
    8.8.4.4
    ``` 
