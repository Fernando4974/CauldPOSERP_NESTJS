# ClaudPOS ERP · Full Stack Project

Bienvenido al repositorio principal de **ClaudPOS ERP**, una solución completa de Punto de Venta (POS) y planificación de recursos empresariales que articula un backend NestJS con un frontend Angular 18 optimizado para entornos táctiles (Desktop Touch).

## ¿Qué contiene este repositorio?
- **Frontend/** – SPA Angular 18 + Bootstrap 5 diseñada como un emulador de la maquina Casio T-S800 para pantallas táctiles e incorpora escaneo QR desde el navegador.
- **Backend/** – API NestJS con conexión a PostgreSQL 14, documentación Swagger y validaciones activadas (ValidationPipe).

## Tabla de contenidos
1. [Clonar con submódulos](#clonar-con-subm%C3%B3dulos)
2. [Requisitos previos](#requisitos-previos)
3. [Puesta en marcha](#puesta-en-marcha)
   1. [Base de datos](#1-base-de-datos-postgresql)
   2. [Backend](#2-backend-nestjs)
   3. [Frontend](#3-frontend-angular)
4. [Red y CORS](#red-y-cors)
5. [Resumen técnico](#resumen-t%C3%A9cnico)
6. [Comandos útiles](#comandos-%C3%BAtiles)
7. [Autores](#autores)

## Clonar con submódulos
```bash
git clone --recursive https://github.com/Fernando4974/ClaudPOSERP-MAIN.git
```
Si ya clonaste sin submódulos, sincroniza con:
```bash
git submodule update --init --recursive
```

## Requisitos previos
- Node.js LTS 18 o 20 y npm >= 10.
- Angular CLI 18.2.20 (global o mediante `npx ng`).
- Docker y Docker Compose para levantar PostgreSQL 14 localmente (Neon es una alternativa gestionada).

## Puesta en marcha

### 1. Base de datos (PostgreSQL)
```bash
cd Backend
docker-compose up -d
```
La base de datos queda disponible en el puerto 6432, con volumen `./postgres` y nombre `claud_db_erp`.

### 2. Backend (NestJS)
1. Copia `Backend/.env.template` a `.env` y ajusta las variables necesarias.
2. Instala dependencias y arranca el servidor:
   ```bash
   cd Backend
   npm install
   npm run start:dev
   ```
La documentación Swagger se publica en `http://localhost:3001/api`.

### 3. Frontend (Angular)
```bash
cd Frontend
npm install
npm start
```
Accede a `http://localhost:4200` para usar la interfaz táctil con botones y tarjetas grandes.

## Red y CORS
El backend permite peticiones desde:
- `http://localhost:4200` (entorno local)
- `https://clauderp.netlify.app` (despliegue del frontend)

## Resumen técnico
| Módulo | Stack tecnológico | Puerto |
| --- | --- | --- |
| Backend | NestJS, PostgreSQL 14, Swagger, ValidationPipe | 3001 |
| Frontend | Angular 18, Bootstrap 5, RxJS, ZXing (QR) | 4200 |

## Comandos útiles
- `git submodule foreach git pull origin main` — actualiza los submódulos.
- `cd Frontend && npx ng lint` — ejecuta el lint del frontend.
- `cd Backend && npm run test` — corre las pruebas del backend.

## Autores
* Fernando Villarreal · Software Developer
* Oliver Arteaga . Frontend Developer
* Felipe Mena . DB Admin
