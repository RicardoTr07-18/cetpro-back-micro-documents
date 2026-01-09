## 🧠 Paradigmas de Programación Utilizados

La plataforma backend está diseñada bajo un **enfoque híbrido de paradigmas de programación**, seleccionando cada uno según el propósito y las necesidades técnicas de cada microservicio. Esta combinación permite mantener un equilibrio entre **claridad**, **rendimiento**, **escalabilidad** y **mantenibilidad**.

---

### 🧱 Programación Orientada a Objetos (POO)

La **Programación Orientada a Objetos** constituye la base estructural del sistema. Se utiliza para modelar el dominio del negocio y organizar el código de forma clara y modular.

En la plataforma, la POO se aplica en:

- Definición de **entidades de dominio** (Student, Teacher, Matricula, Debt, etc.)
- Implementación de **servicios de negocio** (`@Service`)
- Controladores REST (`@RestController`)
- Repositorios de acceso a datos (`@Repository`)
- Uso de principios como **encapsulación**, **responsabilidad única** y **separación de capas**

Este enfoque facilita la comprensión del sistema, promueve la reutilización de código y permite una evolución controlada de las reglas de negocio.

---

### 🧭 Programación Imperativa

La **programación imperativa** está presente en la lógica tradicional del sistema, donde se define explícitamente **cómo** se debe ejecutar cada operación paso a paso.

Se utiliza principalmente en:

- Microservicios basados en **Spring MVC**
- Lógica transaccional y validaciones de negocio
- Persistencia de datos mediante **Spring Data JPA**
- Configuraciones de seguridad, caché y monitoreo

Ejemplos típicos incluyen operaciones CRUD, control de flujo (`if`, `for`, `try-catch`) y manejo explícito de transacciones.

Este paradigma es ideal para procesos determinísticos, reglas de negocio claras y operaciones sin alta concurrencia.

---

### ⚡ Programación Reactiva

La **programación reactiva** se adopta en los microservicios que requieren **alta concurrencia**, **no bloqueo de hilos** y **comunicación asíncrona**, especialmente en el servicio de Inteligencia Artificial.

Se implementa mediante:

- **Spring WebFlux**
- Tipos reactivos `Mono` y `Flux`
- Comunicación no bloqueante entre microservicios
- Integración eficiente con servicios externos como **Ollama**

Este paradigma permite al sistema manejar múltiples solicitudes concurrentes con menor consumo de recursos, mejorando la escalabilidad y la capacidad de respuesta bajo carga.

---

### 🔁 Conceptos de Programación Funcional

Aunque el sistema no es puramente funcional, incorpora **conceptos clave de programación funcional** para mejorar la legibilidad, expresividad y manejo de flujos de datos.

Estos conceptos se aplican mediante:

- Uso de **expresiones lambda** (`->`)
- Operadores funcionales como `map`, `flatMap`, `filter`
- Composición de flujos reactivos
- Manejo funcional de errores (`onErrorResume`, `onErrorReturn`)
- Inmutabilidad lógica en flujos de datos

Este enfoque reduce el código imperativo repetitivo y favorece una programación más declarativa, especialmente en contextos reactivos.

---

### 🧩 Enfoque Híbrido

La combinación de estos paradigmas permite:

- Utilizar **POO e imperativo** donde la claridad y simplicidad son prioritarias
- Aplicar **reactivo y funcional** donde se requiere escalabilidad y eficiencia
- Adaptar cada microservicio a su carga y responsabilidad específica

Como resultado, la plataforma logra ser **modular**, **escalable**, **resiliente** y **preparada para escenarios de alta demanda**, manteniendo al mismo tiempo un código mantenible y comprensible.

---
