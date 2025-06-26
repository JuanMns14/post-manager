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

  Inicia tu aplicación Strapi con autoReload habilitado. [Aprende más](https://docs.strapi.io/dev-docs/cli#strapi-develop)

  ```bash
  npm run develop
  # or
  yarn develop
  ```

- `start`

  Inicia tu aplicación Strapi con autoReload deshabilitado. [Aprende más](https://docs.strapi.io/dev-docs/cli#strapi-start)

  ```bash
  npm run start
  # or
  yarn start
  ```

- `build`

  Construye tu panel de administración. [Aprende más](https://docs.strapi.io/dev-docs/cli#strapi-build)

  ```bash
  npm run build
  # or
  yarn build
  ```