# Proyecto Docker - Redes, Volúmenes y Orquestación

Este proyecto corresponde a la práctica de Docker, donde se aplican redes, volúmenes, contenedores y orquestación de servicios usando Dockerfile y Docker Compose.

---

## Usuario Docker Hub
dracko23

---

## Imágenes publicadas
- dracko23/nginx-tarea
- dracko23/postgres-tarea

---

## Red y Volumen Docker
- Red utilizada: `redtarea` (tipo bridge), permite la comunicación entre los contenedores.  
- Volumen utilizado: `volumentarea`, para asegurar persistencia de datos incluso si los contenedores se detienen o eliminan.  

---

## Contenedores y servicios

### Base de datos (PostgreSQL)
- Se construyó desde Dockerfile.
- Persistencia en `/var/lib/postgresql/data`.
- Conectada a la red `redtarea`.
- Imagen publicada como `dracko23/postgres-tarea`.

### Servicio web (Nginx)
- Se construyó desde Dockerfile copiando `index.html`.
- Publicado en el puerto 80.
- Conectado a la red `redtarea`.
- Utiliza el volumen `volumentarea` en `/usr/share/nginx/html`.
- Imagen publicada como `dracko23/nginx-tarea`.

---

## Ejecución con Dockerfile
```bash
cd compose-dockerfile
docker compose up -d --build

