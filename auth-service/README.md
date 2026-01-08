# Auth Service

## 📌 Descripción

El **Auth Service** es el microservicio responsable de la autenticación y autorización del sistema. Gestiona usuarios, credenciales, roles y la emisión y validación de tokens JWT, proporcionando seguridad centralizada para la plataforma de microservicios.

---

## 🧩 Responsabilidades

- Autenticación de usuarios mediante credenciales (email y contraseña)
- Emisión de **JWT** con información de rol
- Validación y filtrado de tokens JWT
- Autorización basada en roles (cliente, administrador)
- Gestión de usuarios (**CRUD**)
- Migración automática de contraseñas en texto plano a **BCrypt**
- Exposición de métricas y endpoints de monitoreo

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring Security**
- **JWT (jjwt)**
- **Spring Data JPA**
- **PostgreSQL**
- **Spring Cloud Eureka Client**
- **SpringDoc OpenAPI**
- **Spring Boot Actuator**
- **Prometheus**

---

## 🔐 Seguridad

- Autenticación basada en **Bearer Token (JWT)**
- Seguridad **stateless** (sin sesiones)
- Filtro JWT integrado en la cadena de seguridad (`OncePerRequestFilter`)

---

## 🔑 Flujo de Autenticación

1. El cliente envía credenciales a `/auth/login`
2. Las credenciales se validan contra la base de datos
3. Se genera un **JWT** con el rol del usuario
4. El cliente utiliza el token en el header:
5. El token es validado en cada request protegida

---

## 📚 Documentación API

- **Swagger UI**  
http://localhost:8083/swagger-ui.html

- **OpenAPI JSON**  
http://localhost:8083/v3/api-docs

---

## 📊 Observabilidad

- **Health Check:**  
`/actuator/health`

- **Métricas:**  
`/actuator/metrics`

- **Prometheus:**  
`/actuator/prometheus`

---

## 🚀 Rol en la arquitectura

- Centraliza la autenticación y autorización del sistema
- Simplifica la seguridad de los microservicios
- Permite escalabilidad y desacoplamiento
- Garantiza consistencia en el control de acceso
