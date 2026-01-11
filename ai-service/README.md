# AI Service

## 📌 Descripción

El **AI Service** es el microservicio encargado de orquestar capacidades de **Inteligencia Artificial** mediante **Ollama** y **Spring AI**, integrándose con los microservicios **Catalog Service** y **Finance Service** para generar respuestas académicas y financieras enriquecidas, claras y controladas.

Opera de forma **reactiva**, **cacheada** y con descubrimiento dinámico de servicios vía **Eureka**.

---

Instala antes ollama:

descargar ollama:
```http
docker exec -it ollama ollama pull llama3
```

verificar:
```http
docker exec -it ollama ollama list
```

## 🧩 Responsabilidades

- Generación de respuestas con IA local (**Ollama – LLaMA3**)
- Chat inteligente con contexto de microservicios
- Consultas académicas asistidas por IA
- Análisis de estudiantes por:
  - Total
  - Semestre
  - DNI
- Análisis de docentes por DNI
- Integración con **Catalog Service** y **Finance Service**
- Caché distribuido con **Redis**
- Exposición de métricas y estado del servicio

---

## 🔗 Integración con microservicios

| Servicio         | Uso                                   |
|------------------|----------------------------------------|
| Catalog Service  | Estudiantes, docentes, matrículas      |
| Finance Service  | Deudas y estado financiero              |

La comunicación se realiza mediante **WebClient + Eureka (LoadBalanced)**, sin URLs fijas.

---

## 📚 Endpoints principales

### 🤖 Inteligencia Artificial

#### Generación simple (prompt directo)
```http
GET http://localhost:8090/api/ai/generate?promptMessage=mensaje
```

#### Chat IA integrado con microservicios
```http
POST http://localhost:8090/api/ai/chat
```
#### Body (JSON)
```json
{
  "message": "mensaje a consultar"
}
```

---

### 🎓 Estudiantes

#### Total de estudiantes
```http
GET http://localhost:8090/api/ai/students/count
```

#### Estudiantes por semestre
```http
GET http://localhost:8090/api/ai/students/count/semester?year=2025&semester=1
```

#### Consulta de estudiante por DNI (vía Chat IA)
```http
POST http://localhost:8090/api/ai/chat
```
#### Body (JSON)
```json
{
  "message": "puedes buscar información del estudiante con DNI 97654321"
}
```

---

### 👨‍🏫 Docentes

#### Consulta de docente por DNI (vía Chat IA)
```http
POST http://localhost:8090/api/ai/chat
```
#### Body (JSON)
```json
{
  "message": "puedes buscar información del profesor con DNI 23456789"
}
```


---

## 🧠 Arquitectura IA

- **Spring AI + Ollama**
- Modelo configurado: **llama3**
- Construcción de prompts controlados (prevención de alucinaciones)
- Separación clara de responsabilidades:
  - Prompt Builder
  - Cache
  - Orquestación
  - Llamadas a IA

---

## ⚡ Caché y rendimiento

- **Redis** como caché distribuido
- Caché aplicada a:
  - Prompts de IA
  - Conteos académicos
  - Consultas por DNI
- Claves cacheadas mediante **hash MD5 del prompt**
- Evita llamadas repetidas a IA y microservicios

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring WebFlux**
- **Spring AI**
- **Ollama (LLaMA3)**
- **Spring Cloud Eureka Client**
- **Spring Cloud Config**
- **Spring Cache + Redis**
- **SpringDoc OpenAPI**
- **Spring Boot Actuator**
- **Prometheus**

---

## 📚 Documentación API

- **Swagger UI**  
  http://localhost:8090/swagger-ui.html

- **OpenAPI JSON**  
  http://localhost:8090/v3/api-docs

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

- Centraliza la lógica de IA aplicada al dominio
- Reduce la carga en microservicios core
- Evita acoplamiento entre IA y lógica de negocio
- Mejora la experiencia del usuario final
- Arquitectura escalable, desacoplada y tolerante a fallos
