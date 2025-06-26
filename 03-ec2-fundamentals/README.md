# 🖥️ 03 - EC2 (Elastic Compute Cloud)

EC2 es el servicio de AWS que permite lanzar servidores virtuales bajo demanda. Puedes crear y gestionar máquinas virtuales conocidas como **instancias EC2** para ejecutar aplicaciones, webs, scripts, entornos de desarrollo y más.

---

## 📦 ¿Qué incluye una instancia EC2?

Una instancia EC2 está compuesta por:

- **AMI (Amazon Machine Image)**: Sistema operativo preconfigurado (como Ubuntu, Amazon Linux, etc.).
- **Tamaño de la instancia**: Define la cantidad de CPU y memoria RAM.
- **Almacenamiento**: Disco duro que puede ser EBS (persistente) o instancia store (temporal).
- **Grupos de seguridad**: Firewall que regula el tráfico entrante/saliente.
- **Datos de usuario**: Script opcional que se ejecuta en el primer arranque (User Data).

---

## 🔐 Grupos de seguridad

Son firewalls virtuales adjuntos a cada instancia. Controlan:
- Qué puertos están abiertos (ej: 22 para SSH, 80 para HTTP)
- Qué direcciones IP pueden acceder

---

## ⚙️ Datos de usuario (User Data)

Permiten lanzar un script en el **primer arranque** de una instancia.  
Ejemplo típico: instalar Apache automáticamente al arrancar la máquina.

---

## 👤 Rol de la instancia EC2

Puedes asociar un **rol IAM** a una instancia EC2 para darle permisos sin necesidad de usar claves de acceso.

### Ejemplos de uso:
- Permitir que la instancia EC2 acceda a un bucket S3 sin credenciales.
- Darle acceso a servicios como CloudWatch o bases de datos RDS.
- Ejecutar tareas automatizadas de forma segura (por ejemplo, backups o recolección de logs).

Esto mejora la seguridad y evita incluir claves en el código o en el disco de la instancia.

---

## 💰 Opciones de compra de instancias EC2

| Tipo de instancia           | Descripción                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **On-Demand**               | Pagas por hora. Flexible. Ideal para desarrollo y pruebas.                  |
| **Spot**                    | Precio variable. Muy barato, pero puede ser interrumpido por AWS.           |
| **Reservadas**              | Contrato a 1 o 3 años. Más baratas que On-Demand.                           |
| **Reservadas Convertibles** | Se pueden cambiar por otras instancias.                                    |
| **Reservadas Programadas**  | Se usan en horarios específicos.                                           |
| **Host Dedicado**           | Servidor físico completo reservado para ti.                                |
| **Instancia Dedicada**      | Instancia EC2 aislada pero en hardware compartido.                         |

---

## 📌 Resumen

- **EC2** = Máquina virtual personalizable en la nube.
- Permite control total sobre CPU, RAM, SO, almacenamiento y red.
- Soporta acceso remoto (SSH) y automatización con scripts `User Data`.
- Puedes asociar **roles IAM** a las instancias para que accedan a otros servicios de forma segura.
- Hay múltiples opciones de compra según tu uso y presupuesto: desde On-Demand hasta instancias dedicadas.

---

