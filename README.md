# Backend Microservices Platform

## 📌 Descripción

Plataforma **backend** basada en una arquitectura de **microservicios**, orientada a la gestión **académica**, **financiera** y a la **asistencia con IA**.  
Está diseñada para ser **escalable**, **resiliente** y **observable**.

---

## 🧩 Servicios y Documentación

Documentación individual por microservicio:

| Servicio        | Descripción                     | README |
|-----------------|----------------------------------|--------|
| AI Service      | IA con Spring AI + Ollama        | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/ai-service/README.md |
| API Gateway     | Punto de entrada único           | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/api-gateway/README.md |
| Auth Service    | Autenticación y JWT              | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/auth-service/README.md |
| Catalog Service | Gestión académica                | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/catalog-service/README.md |
| Cloud Config    | Configuración centralizada       | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/cloud-config/README.md |
| Eureka Server   | Descubrimiento de servicios      | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/eureka-server/README.md |
| Finance Service | Gestión financiera               | https://github.com/RicardoTr07-18/cetpro-back-micro-documents/blob/main/finance-service/README.md |

---

## 🛠️ Stack Tecnológico

- **Spring Boot · Spring Cloud · Spring Security**
- **Spring Web / WebFlux · Spring AI (Ollama)**
- **PostgreSQL · Redis · JWT**
- **Eureka · Config Server · Resilience4j**
- **Prometheus · Actuator · OpenAPI**

---

## 🔐 Seguridad

- Autenticación basada en **JWT**
- Arquitectura **stateless**
- Control de acceso por **roles**

---

## 📊 Observabilidad

- **Health checks:** `/actuator/health`
- **Métricas:** `/actuator/prometheus`

---

## 🚀 Orden de arranque recomendado

1. Cloud Config
2. Eureka Server
3. API Gateway
4. Auth Service
5. Catalog Service
6. Finance Service
7. AI Service

---

## 📊 Grafana, Prometheus, Ollama y Redis

Este proyecto utiliza **Docker** y **Docker Compose** para facilitar la ejecución del entorno.

### 🚀 Levantar los servicios
Ejecuta el siguiente comando para iniciar los contenedores en segundo plano:

```bash
docker compose up -d
```

## 📄 Licencia

**Privado.**  
Uso interno, académico o demostrativo. No autorizado para distribución pública.
