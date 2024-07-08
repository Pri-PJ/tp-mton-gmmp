<h1>Estrategias de Persistencia - TP 2024</h1>

<h3><ins>Instalar y ejecutar la API:</ins></h3>

Utilice el comando ```npm install``` para instalar todas las dependencias de la API. Nótese que debe tener instalado Docker y NodeJS previamente.

Luego, utilice los comandos ```npm run start``` para iniciar la aplicación en modo normal, o ```npm run dev``` para iniciar la aplicación en modo desarrollo.

<h3><ins>Uso con distintas bases de datos:</ins></h3>

La API está configurada para su uso con SQLite por defecto. Si quisiera utilizarse con MySQL, en el archivo ```config.js```, copie y pegue lo siguiente:

```
module.exports = {
development: {
    username: "root",
    password: "123456",
    database: "universidad_db",
    host: "127.0.0.1",
    port: 3307,
    dialect: "mysql",
    pool: {
      max: 5,
      min: 0,
      acquire: 30000,
      idle: 10000,
    },
  },
};
```
Si desea utilizar una base de datos no incluída en el proyecto, modifique el archivo ```docker-compose.yml```, añada las variables de entorno necesarias y cambie el ```dialect``` en ```config.js``` al que corresponda.

<h3><ins>Diagrama DER:</ins></h3>

<img src="assets/diagramaDER.png"></img>



<h4><ins>Notas adicionales:</ins></h4>

Para probar el método de asociación de profesor a curso, en Postman, utilícese el siguiente formato en el raw.
```
{
    "profesores": [
    {
        "id": 1,
    },
    {
        "id": 2,
    }
]
}
```
