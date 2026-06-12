# 📁 Portafolio de Administración de Sistemas y Seguridad en Linux

¡Bienvenido a mi repositorio de laboratorios prácticos! En este espacio documento de forma técnica y detallada la resolución de incidentes, gestión de infraestructura y hardening de servidores Linux, estructurado en un programa intensivo de 4 meses.

## 🛠️ Tecnologías y Herramientas Utilizadas
- **Sistema Operativo:** Ubuntu Server / Debian Linux
- **Auditoría y Monitoreo:** Logs del Sistema (`/var/log/auth.log`, `grep`, `tail`)
- **Gestión de Memoria:** Control de procesos (`ps`, `top`, señales `kill`)
- **Seguridad:** Gestión avanzada de permisos corporativos (ACLs, Chmod, Chown, Grupos)

---

## 🚀 Índice de Módulos y Misiones

### 📁 [Módulo 01: Estructura de Directorios y Permisos Corporativos](./Modulo-01-Estructura-y-Permisos/)
- **Caso Práctico:** Configuración de una zona compartida aislada para el departamento de Cobros.
- **Competencias:** Creación de usuarios/grupos, asignación de permisos restrictivos (`drwxrwx---`) y validación de herencia de archivos.

### 📁 [Módulo 02: Auditoría de Logs y Gestión de Procesos](./Modulo-02-Auditoria-y-Procesos/)
- **Caso Práctico:** *Operación Rescate* — Mitigación de intrusión y persistencia en la cuenta de un operador.
- **Competencias:** Detección de ataques de fuerza bruta en registros de autenticación, rastreo de PIDs en segundo plano y contención crítica mediante señales de Kernel (`SIGKILL -9`).

---
🔒 *Garantizando la integridad, disponibilidad y confidencialidad de la infraestructura.*
