# Sistema de Gestión de Citas - Barbería [Nombre del Negocio]

¡Bienvenido al repositorio central del proyecto! Este sistema web está diseñado para automatizar la reserva de citas, optimizar la agenda de los barberos y mejorar la retención de clientes mediante recordatorios automatizados.

---

## 📋 Resumen del Proyecto

El cliente necesita una plataforma web donde sus usuarios puedan consultar el catálogo de servicios, conocer las redes sociales del negocio y agendar citas de forma autónoma con el barbero de su elección. El sistema debe controlar estrictamente la disponibilidad y la identidad de los usuarios para evitar duplicidades en la agenda.

### 👥 Actores del Sistema
* **Cliente de la Barbería:** Puede explorar la web, ver servicios, seleccionar su barbero preferido, registrarse/identificarse y agendar de forma única.
* **Administrador (Dueño / 5 Barberos):** Cada uno de los 5 barberos (o el administrador general) debe poder visualizar y gestionar su propia agenda de citas del día.

---

## 🛠️ Desglose de Requerimientos (Alcance del Proyecto)

Para abordar el desarrollo de manera ordenada, el proyecto se dividirá en los siguientes módulos:

### 1. Interfaz Web (Frontend - Página Web y Catálogo)
* **Página de Inicio (Landing Page):** Presentación de la barbería, enlaces directos a sus redes sociales oficiales e información de contacto.
* **Catálogo de Servicios:** Módulo dinámico que muestra los servicios disponibles (Cortes, barba, combos) con su respectivo precio y duración estimada.
* **Módulo de Agendamiento:** Flujo intuitivo para seleccionar servicio -> seleccionar 1 de los 5 barberos -> seleccionar fecha y hora disponible.

### 2. Motor de Reservas y Reglas de Negocio (Backend)
* **Validación de Identidad Única:** El sistema obligará al cliente a registrarse/ingresar con su correo electrónico y número de celular. El backend validará que el correo sea único en la base de datos para evitar usuarios duplicados.
* **Control de Citas en Tiempo Real:** Bloqueo inmediato de horarios por barbero para evitar duplicidades.
* **Margen de Reserva en el Mismo Día:** Se permiten reservas para la fecha en curso siempre y cuando existan al menos **2 horas de anticipación** entre la hora actual y la hora del servicio solicitado.

### 3. Integraciones Clave (Fase Avanzada)
* **Google Calendar API:** Sincronización automática con los calendarios de los barberos al confirmar una cita.
* **Notificaciones Automatizadas:**
  * **Correo:** Confirmación de registro/cita y recordatorio.
  * **WhatsApp:** Recordatorio automatizado al número celular registrado para mitigar el ausentismo.
  * **Recordatorios de Control:** Alertas automatizadas enviadas con un tiempo prudente antes de la cita (ej. 24 horas para citas agendadas con días de anticipación, o confirmación exprés si se agenda para el mismo día).
* **Pasarela de Pagos:** Integración para habilitar el pago de la reserva o servicio en línea.

---

## 🚀 Plan de Trabajo Propuesto (Hitos)

* [ ] **Fase 1:** Maquetación Web (Landing page, catálogo de servicios, enlaces a redes sociales y flujos de reserva).
* [ ] **Fase 2:** Diseño de Base de Datos y Backend (Modelado de Barberos, Servicios, Clientes con restricción de correo único, y lógica de disponibilidad en tiempo real).
* [ ] **Fase 3:** Integración de Google Calendar y correos de confirmación.
* [ ] **Fase 4:** Integración de Pasarela de Pagos y alertas automatizadas de WhatsApp.
* [ ] **Fase 5:** Pruebas de concurrencia (asegurar que no se dupliquen citas) y Despliegue.