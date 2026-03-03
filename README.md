# Sobre el Proyecto 
TiendaSol permite a los vendedores crear y administrar sus tiendas, gestionar productos y hacer seguimiento de pedidos. Los clientes pueden realizar compras en cada tienda de forma independiente.

## Demo
🔗 Frontend: https://tiendasol10.netlify.app/  
🔗 Backend API: https://tienda-sol-backend-v1-0.onrender.com/  
🔗 Documentación Swagger: https://tienda-sol-backend-v1-0.onrender.com/docs/

## Trabajo en equipo

Proyecto desarrollado en equipo de 4 integrantes como parte de la materia Desarrollo de Software de UTN FRBA.

Mi rol en el proyecto:
- Diseño del backend
- Implementación de endpoints de productos, pedidos y notificaciones
- Diseño e implementación del frontend con múltiples vistas y manejo de estado.
- Implementación de sistema de autenticación basado en sesiones para gestión de usuarios.
- Integración con MongoDB Atlas
- Configuración de Docker y despliegue en Render del backend
- Configuración de Docker y despliegue del frontend en Netlify

## 🛠 Tecnologías utilizadas

Frontend:
- React
- Vite
- JavaScript

Backend:
- Node.js
- Express
- MongoDB
- Swagger


Infraestructura:
- Docker
- MongoDB Atlas
- Render
- Netlify
  
# Documentación
## Guía de Despliege 
### Base de Datos - MongoDB Atlas

1. Crear un cluster  
Name: tienda_sol_db  
Provider: AWS  
Región: Sao Paulo (sa-east-1)

2. Crear un usuario con username y password

3. Seleccionar My Local Environment

4. Añadir todas las IPs de Render a la IP Access List de MongoDB (se pueden obtener las IPs de render al presionar connect)

5. Luego de crear el cluster, presionar:  
connect -> compass -> copiar la url  
Esa será la MONGODB_PROD

### Backend - Render

1. Ir a new Web Service

2. En el código fuente usar una imagen existente de docker (una subida en docker hub usando los siguientes comandos:  
docker build  
docker push  
)

3. En el health check poner el path /health-check

4. Servicio: 2025-2c-grupo-10 (Región Oregon – Free).

    a. Variables de entorno (Render):  
    MONGODB_PROD = <connection_string>
### Frontend - Netlify

1. Conectar Netlify con GitHub

2. Hacer fork del repositorio en caso de no contar con permisos para Netlify

3. Sitio público tiendasol10.netlify.app

4. Repositorio conectado: Github  
Directorio base: /tienda-sol-frontend  
Build: npm install && npm run build  
Publish: /tienda-sol-frontend/dist  
Funciones: /tienda-sol-frontend/netlify/functions/

5. Variable de entorno:  
VITE_API_URL= https://tienda-sol-backend-v1-0.onrender.com

### Conexión y Verificación

El frontend usa VITE_API_URL para comunicarse con la API de render.

El backend debe permitir el dominio del frontend mediante la variable VITE_API_URL



