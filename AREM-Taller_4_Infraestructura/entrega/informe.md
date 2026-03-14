# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
Taller 4 - Mapa de Infraestructura y Diagnóstico Técnico

## 👥 Integrantes del equipo
- Felipe Ballesteros
- Andres Beltran
- Tomas Ariza Rodriguez

## 🧠 Descripción general del trabajo
El objetivo del taller fue construir un mapa de infraestructura tecnológica y realizar un diagnóstico técnico del sistema del cliente analizado durante el proyecto del curso. En este caso se trabajó con la plataforma BO-TECH Tracking, un sistema orientado al monitoreo de rutas de transporte escolar en tiempo real.

Durante el desarrollo del taller se modeló una arquitectura lógica de infraestructura que representa los principales componentes tecnológicos que permiten el funcionamiento del sistema, incluyendo usuarios, servicios backend, bases de datos, servicios de monitoreo y mecanismos de comunicación con dispositivos GPS.

Posteriormente, se realizó un diagnóstico técnico identificando posibles debilidades de infraestructura, cuellos de botella y riesgos de disponibilidad o escalabilidad. Este análisis permite entender qué aspectos de la arquitectura actual podrían representar problemas a medida que la plataforma crece o aumenta el número de usuarios.

## 🔧 Proceso de desarrollo
Para el desarrollo del taller el equipo siguió una metodología progresiva de modelado y análisis.

Primero se revisó el contexto del cliente y los elementos del sistema identificados en entregas anteriores del proyecto, particularmente los procesos de negocio, el modelo de datos (ERD) y la arquitectura general del sistema. A partir de esta información se identificaron los componentes tecnológicos necesarios para soportar el funcionamiento de la plataforma de monitoreo.

Posteriormente se construyó un primer borrador del mapa de infraestructura utilizando una herramienta de modelado visual (draw.io), donde se representaron los principales nodos del sistema: usuarios finales, servicios de acceso, balanceo de carga, servicios backend, base de datos y sistemas de notificación.

Finalmente se ajustó el modelo agregando componentes adicionales relacionados con seguridad, monitoreo y almacenamiento de datos históricos. Con base en este mapa final se realizó el diagnóstico técnico, analizando posibles puntos únicos de falla, riesgos de latencia en el rastreo en tiempo real y limitaciones en la escalabilidad del sistema.

## 🧩 Análisis del modelo propuesto
1. Estructura del modelo

El modelo de infraestructura propuesto se organiza en varias capas tecnológicas que representan el flujo de información dentro del sistema:

Capa de usuarios: incluye a los acudientes, administradores y conductores que interactúan con el sistema mediante aplicaciones móviles o web.

Capa de acceso: compuesta por servicios de red como el firewall, CDN o balanceador de carga que gestionan el tráfico entrante y protegen la plataforma.

Capa de servicios de aplicación: contiene los servicios backend responsables de gestionar funcionalidades como el registro de usuarios, la administración de rutas, el procesamiento de ubicaciones GPS y el envío de notificaciones.

Capa de datos: incluye la base de datos principal donde se almacenan los registros de estudiantes, rutas, ubicaciones y notificaciones.

Capa de monitoreo y almacenamiento: donde se registran logs del sistema, métricas de rendimiento y datos históricos de ubicación.

2. Representación de las necesidades del cliente

El modelo refleja las necesidades operativas de BO-TECH Tracking, especialmente aquellas relacionadas con el monitoreo de rutas escolares en tiempo real. La arquitectura incluye mecanismos para recibir información de dispositivos GPS o aplicaciones móviles de conductores, procesar dicha información mediante servicios backend y distribuirla a los usuarios finales mediante notificaciones o visualización en la aplicación.

Además, la presencia de componentes como balanceadores de carga y servicios de monitoreo permite considerar aspectos de disponibilidad y rendimiento, los cuales son críticos para una plataforma que depende de datos en tiempo real.

3. Supuestos del modelo

Debido a que no se cuenta con acceso directo a la infraestructura real de la empresa, el modelo se construyó con base en varios supuestos técnicos razonables:

La plataforma utiliza una arquitectura basada en servicios web o APIs.

Los servicios backend se ejecutan en entornos de nube o servidores virtualizados.

La base de datos es relacional y centraliza la información del sistema.

El sistema utiliza servicios de notificaciones externas para enviar alertas a los usuarios.

Estos supuestos permiten construir un modelo coherente que represente una arquitectura plausible para una plataforma de rastreo en tiempo real.

## 📈 Diagrama final entregado
> (Inserte aquí una imagen o enlace al modelo-final.drawio / .asta / PDF)

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento       | Tipo                          | Descripción                                                                     | Responsable |
| ------------------------- | ----------------------------- | ------------------------------------------------------------------------------- | ----------- |
| Acudiente                 | Actor                         | Usuario que monitorea la ubicación del estudiante mediante la aplicación        | Cliente     |
| Conductor                 | Actor                         | Persona que opera el vehículo y envía información de ubicación al sistema       | Cliente     |
| Administrador             | Actor                         | Usuario encargado de gestionar rutas, estudiantes y configuraciones del sistema | Empresa     |
| Aplicación Web/Móvil      | Sistema                       | Interfaz utilizada por usuarios para interactuar con la plataforma              | Sistema     |
| API Gateway               | Componente de infraestructura | Punto central de acceso a los servicios backend del sistema                     | Sistema     |
| Servicios Backend         | Componente de infraestructura | Procesan la lógica del sistema como gestión de rutas y ubicaciones              | Sistema     |
| Base de Datos             | Componente de infraestructura | Almacena la información de estudiantes, rutas y registros de ubicación          | Sistema     |
| Sistema de Notificaciones | Componente de infraestructura | Envía alertas a los acudientes cuando ocurren eventos importantes               | Sistema     |

## 🔍 Investigación complementaria
### Tema investigado:
Buenas prácticas de arquitectura de infraestructura en sistemas basados en la nube.

### Resumen:
Las arquitecturas modernas de sistemas digitales suelen basarse en infraestructuras en la nube debido a su capacidad de escalabilidad, alta disponibilidad y flexibilidad operativa. Proveedores como AWS, Microsoft Azure y Google Cloud ofrecen servicios gestionados que permiten desplegar aplicaciones distribuidas con balanceo de carga, bases de datos replicadas y sistemas de monitoreo integrados.

Una de las buenas prácticas más relevantes es evitar puntos únicos de falla mediante la replicación de servicios críticos y el uso de balanceadores de carga que distribuyan el tráfico entre múltiples instancias de aplicación. Asimismo, el uso de contenedores y orquestadores como Docker y Kubernetes facilita la escalabilidad horizontal de los servicios, permitiendo aumentar o reducir la capacidad del sistema según la demanda.

En el contexto del sistema BO-TECH Tracking, estas prácticas son especialmente importantes debido a la naturaleza en tiempo real del servicio. La disponibilidad del sistema y la latencia en la transmisión de ubicaciones GPS pueden afectar directamente la experiencia de los usuarios, por lo que una infraestructura escalable y monitoreada es fundamental para garantizar el correcto funcionamiento de la plataforma.

## 📚 Referencias
[1] Bass, L., Clements, P., & Kazman, R. Software Architecture in Practice. Addison-Wesley, 2013.
[2] Amazon Web Services. AWS Well-Architected Framework. https://aws.amazon.com/architecture/well-architected/
[3] Newman, S. Building Microservices. O'Reilly Media, 2021.

---

_Este documento hace parte de la entrega del taller 4 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
