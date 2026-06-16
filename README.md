# Sistema de Gestión de Citas - Barbería [Nombre del Negocio]

¡Bienvenido al repositorio central del proyecto! Este sistema web está diseñado para automatizar la reserva de citas, optimizar la agenda del barbero y mejorar la retención de clientes mediante recordatorios automatizados.

---

## 📋 Resumen del Proyecto

El cliente necesita una plataforma web donde sus usuarios puedan agendar servicios de barbería de forma autónoma. El sistema debe confirmar la cita, procesar el pago (opcional/obligatorio según se defina) y enviar alertas para reducir el ausentismo.

### 👥 Actores del Sistema
* **Cliente de la Barbería:** Puede ver servicios disponibles, barberos, horarios libres, agendar y pagar.
* **Administrador (Dueño/Barberos):** Puede gestionar su agenda, ver las citas del día, bloquear horarios y revisar ingresos.

---

## 🛠️ Desglose de Requerimientos (Alcance del Proyecto)

Para abordar el desarrollo de manera ordenada, el proyecto se dividirá en los siguientes módulos:

### 1. Interfaz Web (Frontend)
* Catálogo de servicios (Corte de pelo, barba, combos) con precios y duración.
* Selector de fecha y hora disponible en tiempo real.
* Selector de barbero (si hay más de uno).
* Panel de administración simple para el dueño.

### 2. Motor de Reservas y Lógica (Backend)
* Control de disponibilidad (evitar que dos personas reserven a la misma hora).
* Registro de clientes básico (Nombre, Teléfono, Correo).

### 3. Integraciones Clave (Fase Avanzada)
* **Google Calendar API:** Sincronización automática. Cuando un cliente agenda, se crea el evento en el calendario del barbero.
* **Notificaciones:**
  * **Correo:** Confirmación inicial y recordatorio 24 horas antes.
  * **WhatsApp:** Mensaje automatizado de recordatorio (puede evaluarse mediante la API oficial de Cloud API de Meta o servicios de terceros como Twilio).
* **Pasarela de Pagos:** Integración para recibir pagos con tarjetas de débito/crédito.

---

## 🚀 Plan de Trabajo Propuesto (Hitos)

* [ ] **Fase 1:** Diseño de Base de Datos y Maquetación Web (Vistas de reserva).
* [ ] **Fase 2:** Lógica de agendamiento y panel de administración (Funcionalidad base).
* [ ] **Fase 3:** Integración de Google Calendar y correos.
* [ ] **Fase 4:** Integración de Pasarela de Pagos y alertas de WhatsApp.
* [ ] **Fase 5:** Pruebas y Despliegue en producción.