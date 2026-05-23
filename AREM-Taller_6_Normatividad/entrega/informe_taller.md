# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 6 - Normatividad

## 👥 Integrantes del equipo
- Felipe Ballesteros
- Andres Beltran
- Tomas Ariza Rodriguez

## 🧠 Descripción general del trabajo
El objetivo del taller fue evaluar el cumplimiento normativo del sistema del cliente mediante un checklist basado en regulaciones de protección de datos y seguridad de la información. En este caso, se analizó la plataforma BO-TECH Tracking, la cual gestiona información sensible como datos personales, ubicación en tiempo real y rutas de transporte escolar.

Durante el desarrollo del taller se aplicó un checklist enfocado en normativas como la Ley 1581 de 2012 (Habeas Data en Colombia) y buenas prácticas de seguridad alineadas con ISO/IEC 27001. A partir de esta evaluación se identificaron aspectos que cumplen con la normativa, posibles brechas y oportunidades de mejora en el manejo de la información.

## 🔧 Proceso de desarrollo
El equipo inició identificando los tipos de datos que maneja el sistema, incluyendo datos personales (nombres, contactos), datos sensibles (ubicación en tiempo real de estudiantes) y datos operativos (rutas, conductores, horarios).

Posteriormente se aplicó el checklist normativo dividido en categorías como:

*Consentimiento del usuario
*Seguridad de la información
*Control de acceso
*Retención de datos
*Auditoría y trazabilidad

Se evaluó cada punto del checklist con base en el funcionamiento esperado del sistema, identificando si cumple, presenta brechas o no aplica. Finalmente, se documentaron los hallazgos más relevantes y se propusieron recomendaciones para mejorar el cumplimiento normativo.

## 🧩 Análisis del modelo propuesto
El análisis se estructura en cinco dimensiones principales de cumplimiento:

Consentimiento y tratamiento de datos: evaluación de cómo se recolecta y autoriza el uso de datos personales.
Seguridad de la información: medidas de protección como cifrado, autenticación y almacenamiento seguro.
Control de acceso: gestión de roles (acudiente, conductor, administrador) y permisos.
Retención de datos: políticas de almacenamiento y eliminación de información.
Auditoría y trazabilidad: registro de actividades y seguimiento de eventos dentro del sistema.

Representación de las necesidades del cliente:

El modelo refleja adecuadamente las necesidades de BO-TECH Tracking, ya que el sistema depende del manejo seguro de información crítica como la ubicación de estudiantes y datos personales de usuarios.

El cumplimiento normativo es clave para:

Garantizar la confianza de los usuarios (acudientes y operadores)
Evitar sanciones legales
Proteger la información sensible del sistema

Además, el análisis permite identificar riesgos asociados a la privacidad y seguridad que pueden impactar directamente la operación del servicio.

Supuestos del modelo:

Dado que no se cuenta con acceso directo a la implementación real del sistema, se establecieron los siguientes supuestos:

El sistema almacena datos personales en una base de datos centralizada.
La autenticación se realiza mediante usuario y contraseña.
No todos los procesos cuentan con auditoría completa.
Existen controles básicos de acceso pero no necesariamente avanzados (como MFA).

Estos supuestos permiten realizar una evaluación realista del cumplimiento normativo en un escenario típico.
## 📈 Diagrama final entregado
| Categoría        | Control / Requisito                                      | ¿Cumple? | Justificación                                                                 | Riesgo / Brecha                                         | Recomendación                                               |
|------------------|----------------------------------------------------------|----------|--------------------------------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------|
| Consentimiento   | Solicita autorización para tratamiento de datos personales | Parcial  | Se asume registro de usuarios, pero no evidencia explícita de consentimiento  | Riesgo legal por incumplimiento Ley 1581                 | Implementar checkbox de consentimiento explícito            |
| Consentimiento   | Permite consultar, actualizar o eliminar datos            | No       | No hay evidencia de módulo de gestión de datos personales                     | Incumplimiento de derechos del titular                   | Crear módulo de gestión de datos (Habeas Data)              |
| Seguridad        | Uso de cifrado en transmisión (HTTPS)                    | Parcial  | Probablemente implementado pero no validado completamente                     | Intercepción de datos                                     | Asegurar uso obligatorio de HTTPS/TLS                      |
| Seguridad        | Cifrado de datos sensibles en base de datos              | No       | No se evidencia cifrado de ubicación o datos personales                       | Fuga de información sensible                             | Implementar cifrado en reposo (AES)                        |
| Acceso           | Uso de roles (admin, conductor, acudiente)               | Sí       | El sistema maneja distintos tipos de usuario                                  | Bajo                                                     | Mantener estructura de roles                               |
| Acceso           | Autenticación segura (tokens, MFA)                       | Parcial  | Posible login básico sin autenticación fuerte                                 | Suplantación de usuarios                                 | Implementar JWT + MFA                                      |
| Retención        | Política de almacenamiento de datos                      | No       | No se define cuánto tiempo se guardan datos de ubicación                      | Acumulación innecesaria de datos sensibles               | Definir política de retención                              |
| Retención        | Eliminación segura de datos                              | No       | No se evidencia mecanismo de eliminación                                      | Riesgo legal                                             | Implementar eliminación segura (data lifecycle)            |
| Auditoría        | Registro de logs de actividad                            | Parcial  | Probable logging básico                                                       | Falta de trazabilidad completa                           | Implementar logs detallados                                |
| Auditoría        | Auditoría de accesos y cambios                           | No       | No se evidencia control de auditoría formal                                   | Dificultad en investigación de incidentes                | Implementar auditoría completa                             |
| Datos sensibles  | Protección de datos de ubicación                         | Parcial  | Datos GPS manejados sin evidencia de protección avanzada                      | Riesgo de seguridad física                               | Cifrado + control de acceso estricto                       |
| Datos sensibles  | Minimización de datos                                    | No       | Se podrían almacenar más datos de los necesarios                              | Riesgo legal y de privacidad                             | Aplicar principio de minimización                          |

# 👶 Protección de menores de edad

| Categoría       | Control / Requisito                              | ¿Cumple? | Justificación                                                      | Riesgo / Brecha                        | Recomendación                                |
| --------------- | ------------------------------------------------ | -------- | ------------------------------------------------------------------ | -------------------------------------- | -------------------------------------------- |
| Menores de edad | Consentimiento explícito de acudientes           | Parcial  | No se evidencia autorización formal verificable                    | Riesgo legal y protección infantil     | Implementar autorización digital verificable |
| Menores de edad | Restricción de acceso a ubicación de estudiantes | Parcial  | El sistema maneja tracking pero no evidencia segmentación avanzada | Exposición de ubicación de menores     | Aplicar control RBAC y permisos estrictos    |
| Menores de edad | Protección de históricos de recorrido            | No       | No se evidencia política clara de retención                        | Riesgo de fuga de información sensible | Limitar almacenamiento histórico             |
| Menores de edad | Trazabilidad de accesos a información infantil   | No       | No se evidencia auditoría completa                                 | Uso indebido de información            | Implementar logs y monitoreo de accesos      |
| Menores de edad | Minimización de datos sensibles                  | Parcial  | Se podrían almacenar más datos de los necesarios                   | Riesgo de privacidad                   | Aplicar principio de minimización            |


## 🔍 Investigación complementaria
### Tema investigado:
Cumplimiento de protección de datos personales en Colombia (Ley 1581 de 2012) y buenas prácticas de seguridad (ISO/IEC 27001).

### Resumen:
BO-TECH Tracking maneja información sensible relacionada con rutas escolares y monitoreo de ubicación en tiempo real de estudiantes, lo que implica responsabilidades adicionales frente al tratamiento de datos personales de menores de edad. En Colombia, la Ley 1581 de 2012 y las directrices de la Superintendencia de Industria y Comercio (SIC) establecen que el tratamiento de datos de niños, niñas y adolescentes requiere protección reforzada y autorización explícita de los representantes legales.

Dentro del sistema, datos como ubicación GPS, horarios de recorrido, identificación de estudiantes y rutas asignadas pueden representar riesgos importantes si no existen controles adecuados de acceso y seguridad. Por esta razón, se recomienda implementar mecanismos de autenticación robusta, cifrado de información sensible y segmentación de permisos para garantizar que únicamente acudientes autorizados y administradores validados puedan consultar información relacionada con menores.

Adicionalmente, las buenas prácticas de seguridad indican que los sistemas que manejan geolocalización infantil deben aplicar principios de minimización de datos, retención limitada de históricos y monitoreo de accesos sospechosos. Estas medidas permiten reducir riesgos relacionados con fuga de información, rastreo indebido o uso no autorizado de datos sensibles.

## 📚 Referencias
- [1] Congreso de Colombia. Ley 1581 de 2012 – Protección de Datos Personales.
- [2] ISO/IEC. ISO/IEC 27001 Information Security Management.
- [3] Superintendencia de Industria y Comercio (SIC). Guía de protección de datos personales en Colombia.

---

_Este documento hace parte de la entrega del taller 6 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
