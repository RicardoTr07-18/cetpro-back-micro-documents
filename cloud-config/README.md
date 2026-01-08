# Cloud Config Server

## 📌 Descripción

El **Cloud Config Server** centraliza la configuración externa de todos los microservicios del sistema. Permite administrar propiedades por entorno y por servicio desde un repositorio **Git**, evitando configuraciones embebidas en el código y facilitando cambios sin necesidad de recompilación.

---

## 🧩 Responsabilidades

- Centralización de configuraciones de microservicios
- Gestión de configuraciones por servicio y entorno
- Lectura de propiedades desde repositorio **Git**
- Versionado y trazabilidad de configuración
- Soporte para recarga dinámica de configuración
- Exposición de métricas y estado del servicio

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring Cloud Config Server**
- **Spring Web**
- **Spring Boot Actuator**
- **Micrometer**
- **Prometheus**

---

## 🌐 Endpoints principales

### Configuración por servicio
http://localhost:8888/{application}/{profile}

### Ejemplo
http://localhost:8888/catalog-service/dev


---

## 📊 Observabilidad

- **Health Check:**  
  `/actuator/health`

- **Prometheus:**  
  `/actuator/prometheus`

- **Info:**  
  `/actuator/info`

---

## 🚀 Rol en la arquitectura

- Fuente única de configuración del sistema
- Reduce la duplicación de propiedades
- Permite cambios de configuración sin **redeploy**
- Facilita despliegues por entorno

### Componente base para

- API Gateway
- Catalog Service
- Finance Service
- AI Service
- Eureka Server
