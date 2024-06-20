# Post Manager
## Instalacion
Verifica la guía oficial de instalación de Strapi para conocer los requisitos antes de comenzar. 

Clona el repositorio
```bash
git clone https://github.com/JuanMns14/post-manager.git
```
Cambia al directorio del repositorio
```bash
cd post-manager
```
Instala todas las dependencias usando `npm`
```bash
npm install
```
Copia el archivo de entorno de ejemplo y realiza los cambios de configuración necesarios en el archivo `.env`
```bash
cp .env.example .env
```

Inicia el servidor

- `develop`

  Start your Strapi application with autoReload enabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-develop)

  ```bash
  npm run develop
  # or
  yarn develop
  ```

- `start`

  Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-start)

  ```bash
  npm run start
  # or
  yarn start
  ```

- `build`

  Build your admin panel. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-build)

  ```bash
  npm run build
  # or
  yarn build
  ```

#  Prueba de Programación para Desarrollador - Strapi
## 10. Explica los pasos para configurar un nuevo proyecto en Strapi.
1. Instalación de Strapi:

    El principal requisito es tener `Node.js` instalado en tu sistema. 

    Para verificar la versión instalada ejecuta el comando `node -v` en tu terminal.

2. Creación del proyecto:

    Abre una terminal y navega hasta el directorio donde deseas crear tu proyecto Strapi. Luego, ejecuta el siguiente comando:
    ```bash
    npx create-strapi-app@latest my-strapi-project --quickstart
    ```
    Reemplaza `my-strapi-project` con el nombre que deseas darle a tu proyecto. El flag `--quickstart` indicará a Strapi que use una configuración rápida con una base de datos SQLite.


3. Inicio del proyecto:
    
    Una vez que se haya creado el proyecto, navega hasta el directorio del proyecto y ejecuta el siguiente comando:
    ```bash
    npm run develop
    ```
    Esto iniciará el servidor de desarrollo de Strapi.

4. Acceso al panel de administración:

    Abre tu navegador web y dirígete a la siguiente URL:
    ```bash
    http://localhost:1337/admin
    ```
5. Registro de usuario administrador:

    Crea un usuario administrador para acceder al panel de administración. Ingresa tu nombre de usuario, contraseña y dirección de correo electrónico.

6. Empieza a usar Strapi

    Ya puedes empezar a crear tu API definiendo modelos de datos, relaciones entre modelos y campos personalizados. Strapi te proporciona una interfaz gráfica intuitiva para gestionar tu API y generar código automáticamente.

## 11. ¿Cómo consumirías datos desde Strapi en otro proyecto de NodeJs?
Para consumir datos desde Strapi en otro proyecto de Node.js, puedes seguir estos pasos:

1. Instalar la biblioteca de cliente de Strapi:
    
    Comienza instalando la biblioteca de cliente oficial de Strapi en tu proyecto Node.js:
    ```bash
    npm install @strapi/strapi-client
    ```

2. Obtener la URL de la API de Strapi:

    Para consumir los datos, necesitarás la URL de la API de tu servidor Strapi. Puedes encontrarla en la configuración de Strapi o usando una herramienta como Postman. La URL generalmente tendrá el siguiente formato:
    ```bash
    http://localhost:1337/api/<nombre-de-la-colección>
    ```

3. Crear una instancia del cliente de Strapi:
    ```js
    const { Strapi } = require('@strapi/strapi-client');

    const strapi = new Strapi({
        url: 'http://localhost:1337',
        headers: {
            Authorization: `Bearer ${YOUR_STRAPI_API_KEY}`,
        },
    });
    ```

4. Realizar solicitudes a la API de Strapi:

    El cliente de Strapi te permite realizar diferentes tipos de solicitudes a la API, como obtener, crear, actualizar y eliminar datos. Por ejemplo, para obtener una lista de todos los elementos en una colección, puedes usar el siguiente código:
    ```js
    strapi.api.get('posts')
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error(error);
    });
    ```
5. Manejar los errores:

    Es importante manejar los errores que puedan ocurrir al realizar solicitudes a la API. El cliente de Strapi te permite usar el método `catch()` para capturar errores y manejarlos adecuadamente.

Ejemplo completo:
```js
const { Strapi } = require('@strapi/strapi-client');

const strapi = new Strapi({
    url: 'http://localhost:1337',
    headers: {
        Authorization: `Bearer ${YOUR_STRAPI_API_KEY}`,
    },
});

strapi.api.get('posts')
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error(error);
    });
```
