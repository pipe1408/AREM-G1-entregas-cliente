# 📄 Informe Técnico del Taller
## 🔖 Nombre del Taller

Taller 7 – Integración de Vistas de Arquitectura

## 👥 Integrantes del equipo
Tomas Ariza
Nombre integrante 2
Nombre integrante 3
## 🧠 Descripción general del trabajo

El objetivo del taller fue integrar todas las vistas arquitectónicas desarrolladas durante el curso en una única visión coherente del sistema de BO-TECH Tracking. Para ello, se relacionaron las vistas de negocio, información, aplicaciones, infraestructura y seguridad, permitiendo entender cómo cada componente soporta las necesidades operativas del cliente.

La actividad consistió en consolidar los entregables realizados previamente, incluyendo diagramas BPMN, modelos entidad-relación (ERD), arquitectura de infraestructura y análisis de seguridad STRIDE. Posteriormente se construyó un tablero integrado que muestra la conexión entre procesos operativos, manejo de información, componentes tecnológicos y controles de seguridad.

## 🔧 Proceso de desarrollo

El equipo inició identificando las vistas desarrolladas en talleres anteriores y organizándolas por capas arquitectónicas:

- Negocio
- Información
- Aplicaciones
- Infraestructura
- Seguridad

A partir de esto, se definieron las relaciones entre cada capa. Por ejemplo:

- Los procesos de negocio dependen de aplicaciones móviles y APIs de rastreo.
- Las aplicaciones utilizan bases de datos y servicios backend desplegados en infraestructura cloud.
- Los componentes críticos se protegen mediante mecanismos de autenticación y controles STRIDE.

Para el modelado visual se utilizó draw.io, permitiendo organizar las vistas de manera jerárquica y conectada. Durante el proceso se realizaron ajustes para evitar redundancia y mejorar la claridad del modelo integrado.

## 🧩 Análisis del modelo propuesto
Cómo se estructura el modelo entregado

El modelo integrado se divide en cinco capas principales:

1. Vista de Negocio

Representa los procesos operativos relacionados con:

- Monitoreo de rutas
- Gestión de recorridos
- Validación de paradas
- Seguimiento en tiempo real
2. Vista de Información

Incluye las entidades principales del sistema:

- Ruta
- Vehículo
- Conductor
- Estudiante
- Historial de recorrido
- Usuario administrador
3. Vista de Aplicaciones

Describe los componentes de software involucrados:

- Aplicación móvil del conductor
- Panel administrativo web
- API de tracking
- Sistema de notificaciones
- Base de datos centralizada
4. Vista de Infraestructura

Representa los elementos tecnológicos necesarios para soportar la operación:

- Servidor backend
- API Gateway
- Base de datos
- Servicios cloud
- Balanceador de carga
- Servicios de monitoreo
5. Vista de Seguridad

Integra controles relacionados con:

- Autenticación y autorización
- Control de acceso por roles
- Cifrado de datos sensibles
- Auditoría y trazabilidad
- Mitigación de amenazas STRIDE
- Cómo representa las necesidades del cliente

La arquitectura propuesta responde a las necesidades principales de BO-TECH Tracking:

- Supervisión de rutas en tiempo real
- Trazabilidad de recorridos históricos
- Validación operativa de conductores
- Escalabilidad para múltiples municipios
- Seguridad de la información y cumplimiento normativo

Además, la integración de vistas permite evidenciar cómo cada componente contribuye al objetivo principal: mejorar el control y monitoreo de la movilidad y transporte.

Qué supuestos se tomaron

Debido a que no se cuenta con acceso completo a la infraestructura real del cliente, se establecieron los siguientes supuestos:

- El sistema utiliza una arquitectura cliente-servidor basada en servicios web.
- La aplicación móvil consume APIs REST para el envío y consulta de ubicación.
- Los datos son almacenados en una base de datos centralizada en la nube.
- Existen diferentes roles de usuario con permisos específicos.
- Los mecanismos de seguridad implementados son básicos y pueden fortalecerse.
## 📈 Diagrama final entregado

<img width="1536" height="1024" alt="ChatGPT Image 22 may 2026, 18_53_03" src="https://github.com/user-attachments/assets/b4ddcf09-3c26-4dc8-81f7-53f16d01f226" />


El diagrama final muestra cómo las capas de negocio, información, aplicaciones, infraestructura y seguridad se relacionan entre sí para soportar el funcionamiento completo de BO-TECH Tracking.

## 📋 Tabla de actores, entidades o componentes
| Nombre del elemento | Tipo            | Descripción                                  | Responsable     |
| ------------------- | --------------- | -------------------------------------------- | --------------- |
| Conductor           | Actor           | Ejecuta la ruta y reporta ubicación          | Cliente         |
| Acudiente           | Actor           | Consulta el estado y ubicación del recorrido | Cliente         |
| Administrador       | Actor           | Gestiona usuarios, rutas y monitoreo         | Empresa         |
| Aplicación móvil    | Aplicación      | Permite seguimiento y reporte de ubicación   | Sistema         |
| API Tracking        | Aplicación      | Gestiona comunicación entre app y backend    | Sistema         |
| Base de Datos       | Información     | Almacena rutas, usuarios y recorridos        | Sistema         |
| Servidor Backend    | Infraestructura | Procesa lógica del negocio y APIs            | Infraestructura |
| Sistema de Logs     | Seguridad       | Registra eventos y actividades del sistema   | DevOps          |
| Control RBAC        | Seguridad       | Gestiona permisos por roles                  | Seguridad       |

## 🔍 Investigación complementaria
### Tema investigado

Buenas prácticas para integración de vistas arquitectónicas empresariales y documentación basada en TOGAF y C4 Model.

### Resumen

La integración de vistas arquitectónicas permite representar un sistema desde diferentes perspectivas, facilitando la comprensión de cómo los procesos de negocio se soportan tecnológicamente. Frameworks como TOGAF proponen separar la arquitectura en dominios (negocio, datos, aplicaciones y tecnología), mientras que modelos como C4 ayudan a visualizar las relaciones entre componentes de software e infraestructura.

En arquitecturas modernas, la integración visual de estas capas facilita la identificación de dependencias, riesgos y oportunidades de mejora. Además, permite mantener coherencia entre objetivos estratégicos y decisiones técnicas.

En el caso de BO-TECH Tracking, integrar las vistas permitió entender cómo los procesos operativos de monitoreo dependen directamente de aplicaciones móviles, APIs de rastreo, infraestructura cloud y mecanismos de seguridad para garantizar disponibilidad, trazabilidad y protección de datos.

## 📚 Referencias
[1] The Open Group. TOGAF Standard – Enterprise Architecture Framework.
[2] Simon Brown. The C4 Model for Software Architecture. https://c4model.com/
[3] Microsoft Azure Architecture Center. Cloud Architecture Patterns.
[4] OWASP Foundation. Application Security Verification Standard.

Este documento hace parte de la entrega del Taller 7 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana.
