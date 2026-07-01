# Campuslands Dev MongoDB

Repositorio publico de ejercicios de MongoDB para aprender bases de datos no relacionales con practica progresiva, estructura profesional y flujo Git controlado.

## Objetivo

Que los estudiantes aprendan MongoDB desde fundamentos hasta modelado y consultas avanzadas mediante ejercicios practicos contextualizados en escenarios modernos: videojuegos, deportes, motos, autos, musica, cine, viajes, turismo, diseno 3D y otros casos cercanos a estudiantes de tecnologia.

## Ramas principales

- `main`: produccion. No recibe entregas estudiantiles.
- `dev`: integracion. Todos los Pull Requests de estudiantes deben apuntar aqui.

## Niveles incluidos

- [Facil](./facil): 50 ejercicios.
- [Intermedio](./intermedio): 50 ejercicios.
- [Dificil](./dificil): 50 ejercicios.

## Estructura

```text
campuslands-dev-mongodb/
|-- README.md
|-- CONTRIBUTING.md
|-- FLUJO-DE-ENTREGA.md
|-- GUIA-DE-ENTREGA.md
|-- docs/
|-- facil/
|-- intermedio/
`-- dificil/
```

## Instalacion de MongoDB

Fuentes oficiales recomendadas:

- MongoDB Installation: https://www.mongodb.com/docs/manual/installation/
- MongoDB Community con Docker: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-community-with-docker/

### Windows instalacion directa

1. Entra a https://www.mongodb.com/try/download/community.
2. Selecciona Windows y descarga el instalador MSI de MongoDB Community Server.
3. Ejecuta el instalador como administrador.
4. Deja activada la opcion de instalar MongoDB como servicio.
5. Instala tambien MongoDB Compass si quieres una interfaz grafica.
6. Abre PowerShell y verifica:

```powershell
mongod --version
mongosh --version
```

7. Conecta a MongoDB local:

```powershell
mongosh "mongodb://localhost:27017"
```

### macOS instalacion directa con Homebrew

1. Instala Homebrew si no lo tienes: https://brew.sh.
2. Agrega el tap oficial de MongoDB:

```bash
brew tap mongodb/brew
```

3. Instala MongoDB Community:

```bash
brew install mongodb-community
```

4. Inicia el servicio:

```bash
brew services start mongodb-community
```

5. Conecta con mongosh:

```bash
mongosh "mongodb://localhost:27017"
```

### Linux instalacion directa

MongoDB mantiene instrucciones por distribucion. Usa siempre la guia oficial de tu sistema:

- Ubuntu: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/
- Debian: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-debian/
- Red Hat/RHEL: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-red-hat/

Flujo general:

1. Importar la llave oficial del repositorio MongoDB.
2. Agregar el repositorio de MongoDB para tu distribucion.
3. Instalar `mongodb-org`.
4. Iniciar y habilitar el servicio.
5. Conectar con `mongosh`.

Comandos de verificacion:

```bash
mongod --version
mongosh --version
sudo systemctl status mongod
mongosh "mongodb://localhost:27017"
```

### Instalacion con Docker recomendada para clase

1. Instala Docker Desktop o Docker Engine.
2. Crea un volumen para persistir datos:

```bash
docker volume create campus-mongodb-data
```

3. Ejecuta MongoDB Community:

```bash
docker run -d --name campus-mongodb -p 27017:27017 -v campus-mongodb-data:/data/db mongodb/mongodb-community-server:latest
```

4. Verifica el contenedor:

```bash
docker ps
```

5. Entra a mongosh dentro del contenedor:

```bash
docker exec -it campus-mongodb mongosh
```

6. Detener y volver a iniciar:

```bash
docker stop campus-mongodb
docker start campus-mongodb
```

### Docker Compose opcional

Crea `docker-compose.yml`:

```yaml
services:
  mongodb:
    image: mongodb/mongodb-community-server:latest
    container_name: campus-mongodb
    ports:
      - "27017:27017"
    volumes:
      - campus-mongodb-data:/data/db

volumes:
  campus-mongodb-data:
```

Ejecuta:

```bash
docker compose up -d
docker compose exec mongodb mongosh
```

## Flujo rapido para estudiantes

```bash
git clone https://github.com/anndreloopez012/campuslands-dev-mongodb.git
cd campuslands-dev-mongodb
git switch dev
git pull origin dev
git switch -c alumno/nombre-apellido/ejercicio-001
```

Entrega solo dentro de `resoluciones/nombre-apellido/` y abre PR hacia `dev`.

## Reglas base

- Cada alumno trabaja en su propia rama.
- Las respuestas van dentro de `resoluciones/{usuario-github}/`.
- No se modifican archivos base, README del ejercicio ni respuestas de otros alumnos.
- No se suben credenciales, dumps pesados ni datos privados.
- Todo PR estudiantil apunta a `dev`.
