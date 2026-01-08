# Catalog Service

## 📌 Descripción

El **Catalog Service** es el microservicio central del sistema. Gestiona la información académica y administrativa, incluyendo alumnos, docentes, matrículas, módulos, períodos, turnos, secciones y especialidades, además de la generación de reportes en **PDF, Excel y Word**.

---

## 🧩 Responsabilidades

- Gestión de catálogos académicos (**CRUD**)
- Gestión de matrículas y validación de reglas de negocio
- Consultas avanzadas por período, módulo, turno y sección
- Generación de reportes académicos y administrativos
- Exposición de datos para otros microservicios (**Finance**, **AI**)
- Integración con **Eureka** para descubrimiento de servicios
- Uso de caché en memoria para mejorar el rendimiento
- Exposición de métricas y estado de la aplicación

---

## 📚 Endpoints principales

- **Alumnos:** `/api/student`
- **Docentes:** `/api/teacher`
- **Matrículas:** `/api/matricula`
- **Módulos:** `/api/modules`
- **Períodos:** `/api/periods`
- **Turnos:** `/api/turno`
- **Secciones:** `/api/seccion`
- **Especialidades:** `/api/specialty`
- **Información institucional:** `/api/informationcetpro`

---

## 📄 Reportes

Generación de reportes académicos en múltiples formatos.

### Matrículas
- **PDF:** `/api/report/matricula/pdf`
- **Excel:** `/api/report/matricula/excel`
- **Word:** `/api/report/matricula/word`

### Notas
- **PDF:** `/api/report/grades/pdf`
- **Excel:** `/api/report/grades/excel`
- **Word:** `/api/report/grades/word`

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring MVC**
- **Spring Data JPA**
- **PostgreSQL**
- **Spring Cloud Eureka Client**
- **Spring Cloud Config**
- **JasperReports**
- **Apache POI**
- **Caffeine Cache**
- **SpringDoc OpenAPI**
- **Spring Boot Actuator**
- **Prometheus**

---

## 📚 Documentación API

- **Swagger UI**  
  http://localhost:8082/swagger-ui.html

- **OpenAPI JSON**  
  http://localhost:8082/v3/api-docs

---

## 📊 Observabilidad

- **Health Check:**  
  `/actuator/health`

- **Métricas:**  
  `/actuator/metrics`

- **Prometheus:**  
  `/actuator/prometheus`

---

## 🤖 Integración con IA

El servicio expone endpoints específicos para el consumo del **AI Service**, permitiendo análisis como:

- Conteo de estudiantes por semestre
- Métricas históricas de matrículas

---

## 🚀 Rol en la arquitectura

- Fuente única de datos académicos
- Reduce la duplicación de lógica en otros microservicios
- Centraliza reglas de negocio críticas
- Facilita reportes, análisis y toma de decisiones
