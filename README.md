# 📘 INFORME TÉCNICO  
**Despliegue del aplicativo para gestión financiera en multi contenedor con Docker Compose**

---

## 🧾 Datos del alumno
- **Nombre:** Paul Gallegos Aguilar  
- **Asignatura:** SecDevOps y Administración de Redes para Cloud  
- **Fecha:** 24 de octubre de 2025  

---

## 1. Introducción

El presente informe documenta la orquestación y despliegue de una aplicación de gestión financiera utilizando **Docker Compose**.  
La aplicación pertenece al proyecto **FinTech Solutions S.A.**, desarrollado en un entorno **DevOps** con enfoque en la automatización, portabilidad y consistencia de entornos de desarrollo y producción.  

Este trabajo demuestra cómo definir, configurar y ejecutar múltiples contenedores interconectados (base de datos, backend y frontend) dentro de un mismo entorno controlado.

---

## 2. Objetivos

### Objetivo general
Orquestar el despliegue de una aplicación financiera de tres capas utilizando **Docker Compose**, garantizando comunicación entre servicios, persistencia de datos y modularidad.

### Objetivos específicos
1. **Orquestar múltiples contenedores:** definir y gestionar servicios interdependientes (base de datos, backend y frontend) mediante `docker-compose.yml`.  
2. **Automatizar la configuración y el despliegue:** garantizar el arranque coordinado con variables de entorno, dependencias y puertos definidos.  
3. **Gestionar redes y volúmenes persistentes:** emplear una red interna (`devsu-net`) y volúmenes para asegurar la persistencia de los datos de la base de datos.  

---

## 3. Arquitectura general

### 3.1. Descripción
El aplicativo sigue una arquitectura **tres capas (3-tier)** compuesta por:
- **Capa de datos (PostgreSQL):** almacena la información de usuarios, cuentas y transacciones.
- **Capa de negocio (Spring Boot):** gestiona la lógica financiera y las operaciones CRUD.
- **Capa de presentación (Angular + Nginx):** provee una interfaz web para el usuario final.