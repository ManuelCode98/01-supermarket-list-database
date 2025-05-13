# Pasos para restaurar la base de datos

### Nota 

    Estar en la ruta de esta carpeta que se llama database

1. Instalar docker si no lo tienes instalado

2. Cambiar el nombre del archivo .env.template a .env y agregar informacion de tu contenedor

3. Ejecuta el comando

    **docker compose up -d**

4. Luego ejecuta este comando para ver si el contenedor de postgres esta corriendo en docker

    **docker ps**

5. Luego este comando que copia y pega el archivo de backup de la base de datos

    **docker cp ./init/backup.dump nombre_del_contenedor:/var/lib/postgresql/data/backup.dump**

6. Luego, restaurar la base de datos, reemplaza estos datos con los tuyos: nombre_del_contenedor, usuario, nombre_base_datos

    **docker exec -i nombre_del_contenedor pg_restore -U usuario -d nombre_base_datos /var/lib/postgresql/data/backup.dump**

