Markdown
# 📁 Módulo 01: Estructura de Directorios y Permisos Corporativos

## Caso de Estudio: "Zona Compartida Segura para el Departamento de Cobros"

### 🚨 1. Requerimiento del Negocio
La dirección de la empresa solicitó la creación de un directorio compartido en el servidor Linux para el equipo de **Cobros**. 

* **Restricción crítica:** Solo los miembros de ese departamento deben tener acceso para leer, escribir o ejecutar archivos. Cualquier otro usuario del sistema (incluyendo otros departamentos) debe tener el acceso completamente denegado para evitar la fuga o manipulación de datos financieros sensibles.

---

### 🔍 2. Implementación Técnica (Paso a Paso)

#### A. Creación de la Estructura Operativa
Se procedió a dar de alta el grupo de seguridad corporativo y el directorio centralizado en la raíz del sistema operativo.

```bash
# Creación del grupo corporativo exclusivo para el personal de cobros
sudo groupadd cobros

# Creación del directorio raíz que albergará la información financiera
sudo mkdir /sistema_cobros
B. Asignación de Propiedad y Permisos Restrictivos
Se modificó el esquema de seguridad estándar de Linux para aplicar de forma estricta el Principio de Menor Privilegio.

Bash
# Cambiar el grupo propietario del directorio al grupo "cobros" recién creado
sudo chown :cobros /sistema_cobros

# Aplicar permisos absolutos: Control total para Dueño y Grupo; bloqueo total para Otros
sudo chmod 770 /sistema_cobros
🛡️ 3. Auditoría de Seguridad (Validación)
Para garantizar que el aislamiento del directorio funcione correctamente y que ningún usuario no autorizado pueda infiltrarse, se ejecutó un comando de verificación de atributos extendidos:

Bash
ls -ld /sistema_cobros
💻 Salida real obtenida en la terminal:

Plaintext
drwxrwx--- 2 root cobros 4096 Jun 11 12:00 /sistema_cobros
📊 Desglose detallado del Escudo de Permisos:
d: Identifica que el elemento es un directorio.

rwx (Primer bloque - Dueño): El usuario Administrador (root) conserva el control total del directorio.

rwx (Segundo bloque - Grupo): Todos los usuarios asignados al grupo cobros pueden crear, editar, leer y ejecutar archivos dentro de la carpeta.

--- (Tercer bloque - Otros): Seguridad y Bloqueo Absoluto. Cualquier otra cuenta de usuario en el servidor (ej. operadores, visitas, servicios web) tiene el acceso 100% denegado. No pueden listar, escribir ni entrar.

📝 4. Conclusiones de Hardening
La configuración implementada cumple rigurosamente con los estándares corporativos de cumplimiento y protección de datos financieros. Al eliminar por completo los permisos para el segmento "Otros" (---), se mitiga el riesgo de escalada de privilegios lateral dentro del sistema operativo.
