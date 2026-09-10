# TFM - REA Bot

Este repositorio contiene el código del proyecto TFM.

## Configuración

El proyecto utiliza variables de entorno para configurar el backend y los servicios asociados. Por motivos de seguridad, las claves y tokens reales no se incluyen en el repositorio.

### 1. Crear el archivo `.env`

Antes de ejecutar Docker Compose, es necesario crear el archivo de variables de entorno a partir de la plantilla incluida en el repositorio.

En la carpeta `backend`, cambia el nombre de:

```text
.env.example
```

a:

```text
.env
```

Por ejemplo, desde la raíz del repositorio:

```bash
cp backend/.env.example backend/.env
```

En Windows también se puede realizar el cambio de nombre directamente desde el explorador de archivos.

### 2. Añadir las nuevas claves y tokens

Abre `backend/.env` y completa las variables que estén vacías con las nuevas credenciales correspondientes:

```env
GEMINI_API_KEY=TU_NUEVA_API_KEY
TUNNEL_TOKEN=TU_NUEVO_TUNNEL_TOKEN
```

No introduzcas estas credenciales en `backend/.env.example` ni las subas al repositorio. El archivo `.env` está incluido en `.gitignore` para evitar que las credenciales se publiquen accidentalmente.

La variable `GEMINI_MODELS` de la plantilla contiene los modelos configurados para el proyecto y puede mantenerse si no es necesario modificarla.

## Ejecución

Una vez creado y configurado `backend/.env`, ejecuta Docker Compose desde la raíz del repositorio:

```bash
docker compose up --build
```

El archivo `docker-compose.yml` utiliza `backend/.env` para proporcionar las variables de entorno necesarias a los servicios correspondientes.

## Importante

El archivo `.env.example` es únicamente una plantilla. **Debe cambiarse su nombre a `.env` antes de ejecutar Docker Compose y deben añadirse las nuevas claves y tokens.**

No se deben subir al repositorio archivos `.env` que contengan credenciales reales.
