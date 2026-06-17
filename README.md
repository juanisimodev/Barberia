# Sistema de Agendamiento de Citas Automatizado - Barbería

Este repositorio contiene el código fuente de la aplicación web dedicada exclusivamente a la gestión, reserva y administración de citas en tiempo real para la barbería. El sistema opera de forma independiente a través de un enlace directo, gestionando la disponibilidad de manera interna y notificando a los usuarios mediante correo electrónico.

---

## 📋 Arquitectura de Vistas (Perfiles de Acceso)

La aplicación está dividida estructuralmente en tres entornos independientes basados en el rol del usuario autenticado:

### 1. Vista del Cliente (Acceso Público / Registro)
* **Módulo de Autenticación:** Registro e inicio de sesión para clientes mediante correo electrónico y contraseña.
* **Formulario de Reserva Integrado:** Pantalla centralizada donde el usuario realiza el flujo completo en un solo lugar:
  * Selección del servicio requerido (Corte, Barba, Combos, etc.) con su respectivo precio y duración visible.
  * Selección de 1 de los 5 barberos disponibles.
  * Selector de fecha y hora disponible en tiempo real.
* **Historial de Citas:** Espacio personal donde el cliente puede visualizar el estado de sus reservas pasadas y futuras.

### 2. Vista del Barbero
* **Agenda Individual:** Panel privado para cada uno de los 5 barberos, donde visualizan únicamente su bloque de citas asignadas para el día o la semana.
* **Control de Disponibilidad:** Opción para bloquear bloques de horas específicos por motivos de fuerza mayor.

### 3. Vista del Administrador (Dashboard Completo)
* **Panel de Control Global:** Consola centralizada con acceso a las métricas del negocio (total de citas del mes, ingresos proyectados, barbero con mayor demanda).
* **Gestión de Barberos y Servicios:** Alta, baja y modificación de los perfiles de los barberos, horarios base de trabajo y catálogo de servicios con sus precios.
* **Control Total de la Agenda:** Capacidad de reajustar, cancelar o mover cualquier cita del sistema en caso de ser necesario.

---

## 🛠️ Reglas de Negocio y Lógica de Backend (Go + PostgreSQL)

* **Autenticación Segura:** El backend en Go gestionará el cifrado de contraseñas y la emisión de tokens para mantener las sesiones activas según el rol del usuario.
* **Control de Disponibilidad Local:** El motor de reservas calcula los bloques libres basándose exclusivamente en los datos registrados en la base de datos PostgreSQL, eliminando cualquier dependencia o integración con Google Calendar.
* **Validación Anti-Duplicidad:** El backend bloquea de forma atómica el bloque de tiempo seleccionado para evitar que dos clientes agenden al mismo barbero a la misma hora.
* **Restricción de Tiempo:** Solo se permiten reservas para el mismo día si existe un margen mínimo de **2 horas de anticipación** respecto a la hora actual.
* **Notificaciones Transaccionales:** Confirmación automatizada mediante el envío inmediato de un correo electrónico (vía API de Resend o SendGrid) al email registrado del cliente con los datos exactos de su cita.

---