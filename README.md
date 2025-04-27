# ED-Act3 - Sistema de Gestión de Torneos de eSports
**Entornos de Desarrollo (DAW)**  
**Autora:** Paula Arroyo Ajenjo  
**Curso:** 2024-2025

## Descripción

Proyecto de Entornos de Desarrollo (DAW) para el modelado de un sistema de gestión de torneos de eSports, aplicando diagramas UML de casos de uso y de clases.

---

##  Tabla de Contenidos

- [Descripción](#-descripción)
- [Funcionalidades](#-funcionalidades)
- [Casos de Uso Principales](#-casos-de-uso-principales)
- [Modelado UML](#-modelado-uml)
- [Estructura del Sistema](#-estructura-del-sistema)
- [Conclusiones](#-conclusiones)
- [Repositorio](#-repositorio)
---

## Funcionalidades

###  Acciones por tipo de usuario

- **Administrador**:
  - Registrar equipos y añadir jugadores.
  - Crear torneos e inscribir equipos.
  - Registrar resultados de partidas.
  - Actualizar clasificaciones.
  - Asignar premios.
  - Consultar información completa.

- **Usuario Básico**:
  - Consultar equipos, torneos, partidas, premios y estadísticas.

- **Sistema**:
  - Generar emparejamientos de partidas.
  - Generar clasificaciones y estadísticas automáticamente.

---

##  Casos de Uso Principales

- Gestión de Equipos y Jugadores.
- Gestión de Torneos.
- Gestión de Partidas y Resultados.
- Gestión de Premios.

---

##  Modelado UML


### **Diagrama de Casos de Uso**:
  - Interacciones claras entre usuarios y sistema.
  - Uso de relaciones *include* y *extend*.
    #### CASO DE USO GESTIÓN DE EQUIPOS Y JUGADORES
    - El usuario Admin puede registrar equipos y añadir jugadores. Para añadir jugadores a un equipo, el equipo tiene que estar registrado (dependencia -  include)
    - El usuario Básico puede consultar el listado de equipos y jugadores (depende de que el equipo esté registrado, por eso el uso de extend)
    - Además se incluyen comprobaciones.
    
    #### CASO DE USO GESTIÓN DE TORNEOS
    - El Usuario Admin puede registrar un nuevo torneo en el sistema.
    - El Usuario Admin inscribe un equipo en un torneo. (Incluye la acción de "Crear torneo" porque no se puede inscribir sin un torneo creado primero.)
    - El Sistema automáticamente organiza qué equipos juegan contra quién.
    - Tanto el Usuario Admin como el Usuario Básico pueden consultar la lista de torneos disponibles.

    #### CASO DE USO GESTIÓN DE PARTIDAS Y RESULTADOS
    - El Usuario Admin registra quién ganó/perdió o el resultado del partido.
    - Basado en los resultados, se actualiza el ranking o tabla de posiciones. Incluye "Registrar resultado de una partida" porque necesitas resultados antes de actualizar la tabla.
    - Tanto el Usuario Admin como el Usuario Básico pueden ver la lista de partidas jugadas o por jugar.
    - El Sistema automáticamente calcula los puntos y posiciones basados en los resultados.

    #### CASO DE USO GESTIÓN DE PREMIOS
    - El Usuario Admin entrega premios basándose en las posiciones en la clasificación. Incluye "Actualizar clasificación del torneo" porque primero debes saber quién ganó.
    - Tanto el Usuario Admin como el Usuario Básico pueden consultar qué premios se asignaron o están disponibles
    - "Asignar premios" incluye "Actualizar clasificación", porque no puedes asignar premios sin saber los resultados finales.

### **Diagrama de Clases**:
  - Modelado de entidades, atributos y asociaciones.

> *Nota:* Los diagramas están disponibles en el repositorio.

---

##  Estructura del Sistema

###  Clases de Entidad
- `Equipo` (nombre, lista de jugadores, id)
- `Jugador` (nombre, edad, id)
- `Torneo` (nombre, fecha, equipos participantes, partidas, id)
- `Partida` (equipos enfrentados, resultado, fecha, id)
- `Premio` (descripción, valor, id)

###  Clases de Control
- `GestorEquipos`
- `GestorTorneos`
- `GestorPartidas`
- `GestorPremios`

###  Clase de Interfaz
- `MenuPrincipal`

---

##  Conclusiones

- Identificación y análisis de requisitos de un sistema real.
- Representación gráfica mediante UML.
- Diseño de entidades, controladores e interfaces.
- Aplicación de buenas prácticas en modelado orientado a objetos.

---

##  Repositorio

 [Accede al repositorio aquí](https://github.com/Polita86/ED-Act3.git)

---

