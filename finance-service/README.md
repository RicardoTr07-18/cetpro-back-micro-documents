# Finance Service

## 📌 Descripción

El **Finance Service** es el microservicio responsable de la gestión financiera del sistema, incluyendo deudas, pagos y consultas financieras. Se integra con el **Catalog Service** para obtener información académica (estudiantes, matrículas y períodos), aplicando caché distribuida, tolerancia a fallos y control transaccional.

---

## 🧩 Responsabilidades

- Gestión de deudas y pagos
- Creación de deudas a partir de matrículas
- Consultas financieras por **DNI**, período y código
- Integración con **Catalog Service** mediante **OpenFeign**
- Uso de **Redis** para caché distribuida
- Tolerancia a fallos con **Resilience4j** (Circuit Breaker)
- Exposición de métricas y estado del servicio

---

## 🔗 Integración con otros servicios

### Catalog Service
- Estudiantes
- Matrículas
- Períodos académicos

La comunicación se realiza mediante **Feign Client + Circuit Breaker**, con fallbacks controlados.

---

## 📚 Endpoints principales

### Finanzas

- **Deudas por DNI**
```http  
GET /api/finance/debt/dni/{dni}`
```

- **Deudas por período**
```http  
GET /api/finance/debt/period/{periodCode}`
```

- **Pagos por deuda**
```http  
GET /api/finance/payment/debt/{idDebt}`
```

- **Crear deuda desde matrícula**  
```http
POST /api/finance/debt/matricula/{idMatricula}?amount=`
```

- **Registrar pago por ID**  
```http
POST /api/finance/payment/{idDebt}?amount=`
```

- **Registrar pago por código**  
```http
POST /api/finance/payment/code/{code}?amount=`
```

### Matrículas (Proxy financiero)

- **Historial por DNI**  
```http
GET /api/finance/matricula/historial/{dni}`
```

- **Por período**  
```http
GET /api/finance/matricula/periodo/{period}`
```
---

## ⚡ Caché y rendimiento

- **Redis** como caché distribuida
- Caché aplicada a:
  - Deudas por DNI
  - Períodos académicos
  - Matrículas por DNI y período
- Evicción automática al registrar pagos o crear deudas

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring MVC**
- **Spring Data JPA**
- **PostgreSQL**
- **Spring Cache + Redis**
- **Spring Cloud OpenFeign**
- **Resilience4j (Circuit Breaker)**
- **Spring AOP**
- **Spring Cloud Eureka Client**
- **Spring Cloud Config**
- **SpringDoc OpenAPI**
- **Spring Boot Actuator**
- **Prometheus**

---

## 📚 Documentación API

- **Swagger UI**  
  http://localhost:8084/swagger-ui.html

- **OpenAPI JSON**  
  http://localhost:8084/v3/api-docs

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

- Centraliza la lógica financiera del sistema
- Evita el acoplamiento directo con el catálogo académico
- Mejora el rendimiento mediante caché distribuida
- Garantiza resiliencia ante fallos de servicios externos
- Facilita auditoría, trazabilidad y monitoreo financiero
