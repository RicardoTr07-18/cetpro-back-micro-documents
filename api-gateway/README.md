API Gateway
📌 Descripción

El API Gateway actúa como el punto de entrada único a la plataforma de microservicios. Es responsable del enrutamiento de solicitudes, la seguridad centralizada, la validación de tokens JWT, y el control de acceso basado en roles, garantizando una comunicación segura y controlada entre clientes y servicios internos.

🧩 Responsabilidades

Enrutamiento dinámico hacia microservicios registrados en Eureka

Autenticación y validación de JWT

Autorización por roles (cliente, administrador)

Gestión centralizada de CORS

Propagación de contexto de seguridad hacia los servicios backend

Exposición de métricas y endpoints de monitoreo

🛠️ Tecnologías

Spring Boot

Spring Cloud Gateway (WebFlux)

Spring Security (WebFlux)

JWT (jjwt)

Spring Cloud Eureka Client

SpringDoc OpenAPI

Actuator

Prometheus

🔐 Seguridad

Autenticación basada en Bearer Token (JWT)

Rutas públicas:
/auth/**

Rutas protegidas por rol

Headers inyectados a los microservicios:

X-User-Email

X-User-Role

Authorization

📚 Documentación API

Swagger UI
http://localhost:8090/swagger-ui.html

OpenAPI JSON
http://localhost:8090/v3/api-docs

Nota: El API Gateway documenta únicamente su configuración y filtros.
Los endpoints de negocio se documentan en cada microservicio.

📊 Observabilidad

Health Check: /actuator/health

Métricas: /actuator/metrics

Prometheus: /actuator/prometheus

🚀 Rol en la arquitectura

Reduce acoplamiento entre clientes y microservicios

Centraliza políticas de seguridad

Simplifica la evolución del sistema

Mejora la trazabilidad y el monitoreo