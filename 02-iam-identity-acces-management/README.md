# 🔐 02 - IAM (Identity and Access Management)

## 📘 ¿Qué es IAM?

IAM es el servicio global de AWS que permite **gestionar de forma segura el acceso** a los servicios y recursos de AWS. Con IAM puedes:

- Crear y administrar usuarios y grupos.
- Establecer permisos mediante políticas.
- Controlar el acceso con prácticas seguras como MFA.

---

## 👥 Elementos clave de IAM

| Elemento     | Descripción |
|--------------|-------------|
| **Usuario**  | Representa a una persona o app. Tiene credenciales únicas. |
| **Grupo**    | Colección de usuarios con permisos comunes. |
| **Rol**      | Identidad asumible con permisos temporales, ideal para servicios. |
| **Política** | Documento JSON que define qué acciones están permitidas o denegadas. |

---

## 🧱 Principio de menor privilegio

> Dar siempre **el mínimo acceso necesario** para hacer el trabajo. Nunca más.

---

## 🔑 Política de contraseñas

Puedes configurar:
- Longitud mínima
- Inclusión de mayúsculas, minúsculas, números, símbolos
- Duración máxima de la contraseña
- Cambio forzoso tras un número de días
- Permitir que el usuario cambie su propia contraseña

---

## 🔐 MFA (Autenticación multifactor)

IAM permite configurar MFA (2 pasos) para mayor seguridad.  
Opciones disponibles:
- App Authenticator (como Google Authenticator)
- Mensaje SMS

---

## 🧾 Políticas IAM

Son archivos JSON que definen los permisos de usuarios, grupos y roles.  
Contienen:
- **Effect**: Allow / Deny
- **Action**: Qué se permite hacer
- **Resource**: Dónde se permite hacerlo

### 🧪 Ejemplo simple:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PermitirTodoS3",
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "*"
    }
  ]
}
