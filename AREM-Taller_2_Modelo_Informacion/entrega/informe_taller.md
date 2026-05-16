# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 2: Modelo de Información y Diagrama de Contexto_

## 👥 Integrantes del equipo
- Tomás Ariza
- Felipe Ballesteros
- Andrés Beltrán

## 🧠 Descripción general del trabajo
El presente informe tiene como objetivo diseñar un modelo Entidad–Relación (ERD) que represente la estructura de datos necesaria para el funcionamiento de la aplicación **BO-TECH TRACKING**, una plataforma orientada al monitoreo y rastreo en tiempo real de transporte escolar.

A diferencia del modelo BPMN trabajado que representaba el flujo del proceso, en esta fase se abordó la representación estructural de la información que el sistema debe almacenar de manera permanente. El enfoque se baso en identificar las entidades principales, sus atributos, las relaciones entre ellas y las cardinalidades correspondientes.

El modelo propuesto busca garantizar coherencia, integridad y organización sobre el sistema de seguimiento de rutas escolares y notificaciones a los acudientes.

## 🔧 Proceso de desarrollo
Para la construcción del modelo ERD se siguieron los siguientes pasos:

### 2.1 Identificación de entidades

Se analizaron los elementos del proceso de rastreo y se determinaron como entidades principales aquellas que representan objetos persistentes del sistema como:

- Estudiante  
- Acudiente  
- Ruta  
- Conductor  
- Vehículo  
- Registro_Ubicacion  
- Notificación  

### 2.2 Definición de atributos

Se definieron atributos básicos para cada entidad:

- **Estudiante:** id_estudiante (PK), nombre, grado, estado.
- **Acudiente:** id_acudiente (PK), nombre, teléfono, correo.
- **Ruta:** id_ruta (PK), nombre_ruta, horario.
- **Conductor:** id_conductor (PK), nombre, licencia.
- **Vehículo:** id_vehiculo (PK), placa, capacidad.
- **Registro_Ubicacion:** id_registro (PK), latitud, longitud, fecha_hora, id_ruta (FK).
- **Notificación:** id_notificacion (PK), tipo, mensaje, fecha_envio, id_estudiante (FK).

### 2.3 Definición de relaciones

Se establecieron las siguientes relaciones principales:

- Un acudiente puede tener varios estudiantes (1:N).
- Un estudiante pertenece a una ruta (N:1).
- Una ruta tiene un conductor asignado (1:1 o 1:N según operación).
- Una ruta utiliza un vehículo (1:1).
- Una ruta genera múltiples registros de ubicación (1:N).
- Un estudiante puede generar múltiples notificaciones (1:N).

### 2.4 Definición de claves

Cada entidad fue definida con una clave primaria (PK) única, y se establecieron claves foráneas (FK) para mantener la integridad referencial entre las relaciones.

## 🧩 Análisis del modelo propuesto

### 3.1 Estructura del modelo

El modelo se estructuró con entidades centrales como **Ruta** y **Estudiante**, ya que representan el núcleo operativo del sistema.

La entidad **Registro_Ubicacion** permite almacenar información dinámica del GPS, mientras que la entidad **Notificación** representa los eventos de comunicación enviados a los acudientes.

El modelo respeta principios básicos de diseño:

- Separación clara de entidades.
- Definición de claves primarias.
- Uso adecuado de claves foráneas.
- Relaciones con cardinalidades definidas.
- Reducción de redundancia de información.

### 3.2 Representación de las necesidades del sistema

El modelo permite:

- Registrar estudiantes y sus acudientes.
- Asignar estudiantes a rutas.
- Asociar rutas con conductor y vehículo.
- Almacenar historial de ubicaciones GPS.
- Registrar notificaciones enviadas.

De esta manera, el ERD soporta adecuadamente las funcionalidades principales de la aplicación.

### 3.3 Limitaciones identificadas

El modelo inicial no incluye:

- Gestión de autenticación de usuarios.
- Historial de cambios de ruta.
- Manejo de múltiples conductores por ruta en distintos turnos.
- Control avanzado de permisos.

Estas extensiones podrían incorporarse en una versión futura del modelo.

## 📈 Diagrama final entregado
<img width="795" height="582" alt="{2C4600E9-B451-46D1-BBAC-DDA87868501B}" src="https://github.com/user-attachments/assets/3211b87c-f5f9-452f-ad22-79951882048d" />



## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento   | Tipo     | Descripción                                                   | Responsable |
|-----------------------|----------|---------------------------------------------------------------|-------------|
| Estudiante            | Entidad  | Alumno que utiliza el servicio de transporte escolar         | Sistema     |
| Acudiente             | Entidad  | Persona responsable que monitorea al estudiante              | Usuario     |
| Ruta                  | Entidad  | Recorrido asignado al transporte escolar                     | Empresa     |
| Conductor             | Entidad  | Responsable de operar el vehículo en la ruta                 | Empresa     |
| Vehículo              | Entidad  | Medio de transporte asignado a una ruta                      | Empresa     |
| Registro_Ubicacion    | Entidad  | Historial de coordenadas GPS registradas en tiempo real      | Sistema     |
| Notificación          | Entidad  | Registro de mensajes enviados al acudiente                   | Sistema     |

## 🔍 Investigación complementaria
### Tema investigado:
(Ej: Buenas prácticas BPMN, comparación TOGAF vs C4, principios de seguridad STRIDE, etc.)

### Resumen:
Describa en 2–3 párrafos lo investigado, citando fuentes cuando sea necesario. Incluya cómo se relaciona con el taller.

## 📚 Referencias
- [1] Apellido, Nombre. *Título*. Año. URL o DOI.
- [2] Fuente oficial BPMN: https://www.omg.org/spec/BPMN/

---

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
