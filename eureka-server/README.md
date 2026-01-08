# Eureka Server

## 📌 Descripción

El **Eureka Server** es el servidor de descubrimiento de servicios del ecosistema de microservicios. Permite que los servicios se registren dinámicamente, se descubran entre sí y se comuniquen sin depender de direcciones IP o puertos fijos.

Es un componente **core de infraestructura** y no expone lógica de negocio.

---

## 🧩 Responsabilidades

- Registro dinámico de microservicios
- Descubrimiento de servicios en tiempo de ejecución
- Monitoreo del estado de instancias
- Alta disponibilidad y desacoplamiento
- Punto central de observabilidad de servicios registrados

---

## 🛠️ Tecnologías

- **Spring Boot**
- **Spring Cloud Netflix Eureka Server**
- **Spring Cloud Config**
- **Spring Boot Actuator**
- **Micrometer**
- **Prometheus**
- **Caffeine Cache**

---

## 🌐 Consola Eureka

### Dashboard
http://localhost:8761

Desde la consola se puede:

- Ver servicios registrados
- Ver instancias activas e inactivas
- Ver metadata de cada servicio

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

- Habilita **Service Discovery**
- Elimina dependencias de red estáticas
- Permite escalado horizontal de microservicios
- Facilita resiliencia y balanceo de carga

### Componente obligatorio para

- API Gateway
- Catalog Service
- Finance Service
- AI Service
