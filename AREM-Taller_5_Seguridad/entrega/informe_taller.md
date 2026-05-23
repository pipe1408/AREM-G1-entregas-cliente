# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 5 - Evaluación de Seguridad con STRIDE

## 👥 Integrantes del equipo
- Felipe Ballesteros
- Andres Beltran
- Tomas Ariza Rodriguez

## 🧠 Descripción general del trabajo
El objetivo de este taller fue analizar los riesgos de seguridad de un sistema utilizando el marco STRIDE, el cual permite identificar amenazas relacionadas con suplantación, manipulación de datos, negación de acciones, divulgación de información, denegación de servicio y escalamiento de privilegios.

Para el desarrollo del taller se seleccionó un proceso crítico del sistema BO-TECH Tracking, específicamente el flujo de monitoreo de ubicación en tiempo real de las rutas escolares. Este flujo involucra la transmisión de información desde dispositivos móviles o sistemas GPS utilizados por los conductores hacia el servidor de la plataforma, donde los datos son procesados y posteriormente visualizados por los acudientes mediante la aplicación.

A partir de este proceso se identificaron posibles amenazas de seguridad que podrían afectar la integridad, disponibilidad y confidencialidad del sistema. Posteriormente se evaluó el impacto potencial de dichas amenazas y se propusieron mecanismos de mitigación basados en buenas prácticas de ciberseguridad.

## 🔧 Proceso de desarrollo
El desarrollo del taller se realizó en varias etapas. En primer lugar, el equipo identificó un flujo crítico dentro del sistema del cliente, priorizando aquellos procesos que manejan información sensible o que son fundamentales para la operación de la plataforma. En este caso se seleccionó el proceso de transmisión y procesamiento de datos de ubicación GPS.

Posteriormente se modeló el flujo de interacción entre los principales componentes del sistema, incluyendo los dispositivos de los conductores, el backend del sistema, la base de datos y la aplicación utilizada por los acudientes. Este modelo permitió visualizar los puntos donde podrían presentarse vulnerabilidades o amenazas de seguridad.

Una vez definido el flujo, se aplicó el marco STRIDE para identificar amenazas específicas asociadas a cada categoría del modelo. Para cada amenaza identificada se analizó su posible impacto en el sistema y se propusieron controles de seguridad adecuados, como mecanismos de autenticación, cifrado de datos, control de acceso y monitoreo de eventos.

Finalmente, se registraron los resultados en una tabla de análisis STRIDE y se elaboró un diagnóstico técnico que resume los principales riesgos de seguridad identificados en el sistema.

## 🧩 Análisis del modelo propuesto
1. Estructura del modelo

El modelo de seguridad analizado se basa en el flujo de información que permite el monitoreo en tiempo real de las rutas escolares dentro de la plataforma BO-TECH Tracking. Este flujo incluye varios componentes principales:

Dispositivo del conductor: encargado de capturar y enviar la ubicación GPS del vehículo.

API de tracking: servicio backend que recibe y procesa las solicitudes enviadas por los dispositivos.

Servidor de aplicación: responsable de procesar la lógica del sistema y gestionar las solicitudes de los usuarios.

Base de datos: almacena información relacionada con estudiantes, rutas y registros de ubicación.

Aplicación del acudiente: interfaz que permite visualizar la ubicación del transporte escolar en tiempo real.

2. Representación de las necesidades del cliente

El modelo representa adecuadamente las necesidades del cliente, ya que se enfoca en el proceso central de la plataforma: el seguimiento en tiempo real de las rutas escolares. Este proceso requiere un flujo constante de información entre los dispositivos de los conductores y el sistema central, lo que implica riesgos de seguridad relacionados con la transmisión de datos, el acceso a la información y la disponibilidad del servicio.

El análisis de amenazas mediante STRIDE permite identificar posibles escenarios en los que un atacante podría intentar suplantar usuarios, manipular información de ubicación o acceder a datos sensibles. La identificación de estas amenazas permite proponer controles de seguridad que fortalezcan la arquitectura del sistema y protejan la información de los usuarios.

3. Supuestos del modelo

Debido a que no se cuenta con acceso directo a la infraestructura real de la empresa, el modelo se construyó con base en varios supuestos técnicos razonables:

El sistema utiliza APIs para la comunicación entre dispositivos móviles y servidores.

La transmisión de datos se realiza a través de internet utilizando protocolos HTTP o HTTPS.

La plataforma utiliza una base de datos centralizada para almacenar información del sistema.

Los usuarios acceden al sistema mediante aplicaciones móviles o interfaces web.

Estos supuestos permiten construir un escenario de análisis coherente que refleja la arquitectura típica de una plataforma de monitoreo en tiempo real.

## 📈 Diagrama final entregado
# Análisis de Amenazas STRIDE

| ID | Componente / Activo | Tipo STRIDE | Descripción de la Amenaza | Escenario de Ataque | Impacto | Probabilidad | Nivel de Riesgo | Controles de Seguridad Existentes | Mitigación Recomendada | Responsable | Estado |
|----|---------------------|-------------|---------------------------|---------------------|---------|--------------|-----------------|-----------------------------------|------------------------|-------------|--------|
| B1 | API Tracking | Datos de ubicación GPS | Spoofing | Suplantación de identidad de un conductor o dispositivo GPS | Un atacante roba credenciales de acceso y envía ubicaciones falsas al sistema | Información incorrecta de rutas y pérdida de confianza en el sistema | Media | Alto | Autenticación básica con usuario y contraseña | Implementar autenticación con tokens seguros (JWT) y validación por dispositivo | Backend | Pendiente |
| B2 | API Tracking | Datos de rastreo | Tampering | Manipulación de datos durante la transmisión | Un atacante intercepta el tráfico y modifica las coordenadas GPS enviadas al sistema | Alteración del historial de rutas y errores en monitoreo | Media | Alto | Comunicación HTTPS básica | Implementar cifrado TLS completo y verificación de integridad de mensajes | Backend | Pendiente |
| B3 | Sistema de Logs | Registros de actividad | Repudiation | Negación de acciones realizadas por usuarios | Un conductor niega haber enviado ciertos datos de ubicación o actividad | Dificultad para auditorías o investigaciones | Baja | Medio | Logs básicos del sistema | Implementar auditoría completa y firmas digitales en registros | DevOps | Pendiente |
| B4 | Base de Datos | Información de estudiantes y rutas | Information Disclosure | Acceso no autorizado a información sensible | Un atacante accede a la base de datos y obtiene información de estudiantes y ubicación | Exposición de datos personales y posibles riesgos de seguridad | Media | Alto | Control de acceso básico | Cifrado de datos en base de datos y control de acceso basado en roles (RBAC) | Seguridad | Pendiente |
| B5 | Servidor Backend | Servicios de rastreo | Denial of Service | Saturación del sistema mediante múltiples solicitudes | Un bot envía miles de solicitudes a la API de tracking | Caída del sistema y pérdida de monitoreo en tiempo real | Media | Alto | Firewall básico | Implementar rate limiting, balanceadores de carga y protección DDoS | Infraestructura | Pendiente |
| B6 | Panel Administrativo | Gestión del sistema | Elevation of Privilege | Escalamiento de privilegios de usuario | Un atacante explota una vulnerabilidad para obtener permisos de administrador | Acceso total al sistema y modificación de datos críticos | Baja | Alto | Roles de usuario básicos | Implementar RBAC estricto y auditoría de permisos | Arquitectura | Pendiente |

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento             | Tipo                          | Descripción                                                            | Responsable |
| ------------------------------- | ----------------------------- | ---------------------------------------------------------------------- | ----------- |
| Conductor                       | Actor                         | Persona que opera el vehículo y envía la ubicación GPS al sistema      | Cliente     |
| Acudiente                       | Actor                         | Usuario que monitorea la ubicación del transporte escolar              | Cliente     |
| Administrador                   | Actor                         | Usuario encargado de gestionar el sistema y configurar rutas           | Empresa     |
| Dispositivo GPS / App Conductor | Componente del sistema        | Dispositivo que captura y transmite la ubicación del vehículo          | Sistema     |
| API de Tracking                 | Servicio                      | Recibe y procesa las ubicaciones enviadas por los conductores          | Sistema     |
| Servidor Backend                | Componente de aplicación      | Gestiona la lógica del sistema y las solicitudes de los usuarios       | Sistema     |
| Base de Datos                   | Componente de infraestructura | Almacena información del sistema como rutas, estudiantes y ubicaciones | Sistema     |

## 🔍 Investigación complementaria
### Tema investigado:
Buenas prácticas de seguridad en aplicaciones que manejan datos de geolocalización en tiempo real.

### Resumen:
Las aplicaciones que utilizan datos de geolocalización en tiempo real requieren altos estándares de seguridad debido a la sensibilidad de la información que manejan. Datos como la ubicación de usuarios o rutas de transporte pueden representar riesgos de privacidad y seguridad si no se protegen adecuadamente. Por esta razón, es fundamental implementar mecanismos de cifrado para proteger los datos durante su transmisión y almacenamiento.

Una de las prácticas más importantes es el uso de protocolos seguros como HTTPS y TLS para evitar la interceptación o manipulación de datos durante su transmisión. Asimismo, se recomienda implementar sistemas de autenticación robusta y control de acceso basado en roles para garantizar que solo usuarios autorizados puedan acceder a información sensible.

En el contexto del sistema BO-TECH Tracking, estas medidas son especialmente relevantes debido a que la plataforma maneja información relacionada con la ubicación de estudiantes. Por esta razón, el uso de mecanismos de cifrado, autenticación segura y monitoreo de eventos es fundamental para garantizar la protección de los datos y la confiabilidad del sistema.

## 📚 Referencias
- [1] Shostack, A. Threat Modeling: Designing for Security. Wiley, 2014.
- [2] OWASP Foundation. OWASP Top Ten Web Application Security Risks. https://owasp.org/www-project-top-ten/
- [3] Microsoft. The STRIDE Threat Model. https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats

---

_Este documento hace parte de la entrega del taller 5 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
