# Backend - Agencia de Autos Usados

Este es el backend del Trabajo Práctico Integrador de la materia Backend de Aplicaciones (2025).  
La aplicación simula el sistema interno de una agencia que vende vehículos usados y ofrece pruebas de manejo a sus clientes.

---

## 🧩 Funcionalidad general

- Registro de pruebas de manejo, vinculando cliente, vehículo y empleado.
- Registro y control de la ubicación de vehículos durante las pruebas.
- Generación de notificaciones cuando un vehículo entra en zonas peligrosas o se aleja más de lo permitido.
- Gestión de clientes restringidos (aquellos que incumplen reglas en las pruebas).
- Envío de promociones a teléfonos registrados.
- Reportes de incidentes, historial de pruebas, kilómetros recorridos, etc.

---

## ⚙️ Arquitectura

El sistema está dividido en **microservicios**, organizados por contexto:

- `PruebasService`: manejo de clientes, pruebas, vehículos y empleados.
- `MonitoreoService`: recepción de ubicaciones, validación de límites y disparo de alertas.
- `ApiGateway`: punto de entrada único a todos los servicios.

Cada servicio se conecta a una base SQLite, y se comunica con un servicio externo para obtener la configuración de zonas peligrosas y radio permitido.

---

## 🗃 Base de datos

El modelo relacional fue diseñado desde cero, normalizado, y se compone de las siguientes entidades principales:

- Interesados (clientes)
- Vehículos, modelos y marcas
- Empleados
- Pruebas de manejo
- Posiciones geográficas
- Notificaciones
- Zonas peligrosas
- Clientes restringidos

---

## 🔒 Seguridad

Los endpoints están protegidos por roles:

- **Empleado**: puede registrar pruebas y recibir alertas.
- **Cliente/Vehículo**: puede enviar ubicaciones.
- **Administrador**: accede a reportes y configuraciones.

---

## 🚧 Estado actual

- [x] Modelo relacional diseñado y cargado en SQLite
- [x] Entidades definidas
- [ ] Endpoints iniciales implementados
- [ ] Validaciones de negocio
- [ ] Microservicios separados
- [ ] Seguridad por roles
- [ ] Reportes

---

## 👨‍💻 Tecnologías utilizadas

- Java + Spring Boot
- Spring Data JPA (Hibernate)
- SQLite
- REST APIs
- (opcional) OpenFeign / RestTemplate para consumir servicio externo

---

## ✍️ Autor

Trabajo realizado para la materia **Backend de Aplicaciones - 2024**  
Facultad [especificar facultad o cátedra si querés]

---
