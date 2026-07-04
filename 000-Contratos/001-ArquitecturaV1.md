# Smart Parking Platform
## Contrato de Arquitectura
### Versión 0.1
**Estado:** Borrador de trabajo

---

# 1. Objetivo del sistema

La **Smart Parking Platform** es una plataforma experimental destinada al diseño, implementación y evaluación de algoritmos de asignación dinámica de plazas de estacionamiento en entornos urbanos simulados mediante **SUMO** y controlados mediante **TraCI**.

La plataforma permitirá evaluar el comportamiento del sistema bajo condiciones normales y frente a distintos niveles de comportamientos no cooperativos, registrando eventos primarios que posteriormente serán utilizados para el cálculo de métricas y la evaluación de la robustez del sistema.

---

# 2. Objetivo experimental

El propósito de la plataforma no es únicamente simular un sistema inteligente de estacionamiento.

Su objetivo principal es evaluar experimentalmente cómo se degrada el desempeño global del sistema a medida que aumenta la presencia de comportamientos no cooperativos, identificando los puntos de quiebre en los cuales el sistema deja de aportar beneficios significativos respecto de un escenario sin asistencia inteligente.

---

# 3. Principios de diseño

La plataforma deberá respetar los siguientes principios arquitectónicos:

- Separación entre simulación y lógica de control.
- Separación entre lógica operativa y lógica administrativa.
- Separación entre registro de eventos y cálculo de métricas.
- Todas las decisiones serán tomadas por el controlador.
- SUMO actuará únicamente como simulador físico.
- Todo comportamiento será representado mediante estados y transiciones de estados.
- El sistema almacenará únicamente información primaria; toda métrica derivada será calculada externamente.

---

# 4. Componentes del sistema

## 4.1 Simulador (SUMO)

Responsabilidades:

- Simulación física de los vehículos.
- Simulación física de peatones (futuro).
- Simulación de la red vial.
- Simulación de estacionamientos.
- Representación gráfica.

SUMO no toma decisiones inteligentes.

---

## 4.2 Controlador (TraCI)

Responsabilidades:

- Supervisar los vehículos.
- Detectar solicitudes de estacionamiento.
- Asignar plazas.
- Reasignar plazas.
- Liberar plazas.
- Gestionar estados operativos.
- Gestionar estados de las plazas.

Toda la inteligencia del sistema reside en este componente.

---

## 4.3 Gestor Administrativo

Responsabilidades:

- Detectar estacionamientos ilegales.
- Emitir advertencias.
- Gestionar penalizaciones.
- Gestionar procesos de acarreo.

---

## 4.4 Event Logger

Responsabilidades:

Registrar exclusivamente eventos primarios.

No realiza análisis.

No calcula indicadores.

No calcula estadísticas.

---

# 5. Estados operativos del vehículo

## NORMAL

**Representación visual**

Vehículo con su color original.

**Descripción**

Circula normalmente.

No necesita estacionamiento.

---

## REQUESTING

**Representación visual**

Punto amarillo.

**Descripción**

El conductor solicitó una plaza de estacionamiento.

Permanece circulando mientras espera una asignación.

---

## ASSIGNED

**Representación visual**

Punto verde.

**Descripción**

El sistema asignó una plaza.

El vehículo se dirige hacia dicha plaza.

---

## FAILED_ASSIGNMENT

**Representación visual**

Punto naranja.

**Descripción**

El vehículo llegó a la plaza asignada pero no pudo estacionar.

El sistema deberá generar posteriormente una nueva asignación.

---

## PARKED

**Representación visual**

Vehículo con su color original.

**Descripción**

Vehículo correctamente estacionado.

---

# 6. Estados administrativos

## NONE

Sin infracciones.

---

## ILLEGAL_PARKED

**Representación visual**

Vehículo Rojo

**Descripción**

Vehículo estacionado ilegalmente.

Se inicia una ventana de regularización.

---

## LAST_WORNING

**Representación visual**

Triángulo rojo

**Descripción**

Finalizó la ventana de regularización.

El vehículo entra en situación de acarreo.

Se inicia una segunda ventana temporal.

---

## TOW_PENDING

**Representación visual**

Triángulo negro

**Descripción**

Finalizó la ventana de regularización.

El vehículo entra en situación de acarreo.

Se inicia una segunda ventana temporal.

---

## TOWED

**Descripción**

Finalizó la ventana de regularización.

La grúa retira el vehículo de la simulación.

---

# 7. Estados de una plaza de estacionamiento

Inicialmente se consideran los siguientes estados:

- FREE
- RESERVED
- OCCUPIED
- ILLEGALLY_OCCUPIED
- LAST_WARNING

Estos estados podrán ampliarse en futuras versiones.

---

# 8. Registro de eventos

El sistema registrará únicamente eventos primarios.

Inicialmente se contemplan los siguientes eventos:

- ParkingRequestCreated
- ParkingAssigned
- ParkingAssignmentFailed
- ParkingSucceeded
- ParkingReleased

Eventos administrativos:

- IllegalParkingDetected
- IllegalParkingWarningIssued
- PenaltyStateEntered
- IllegalParkingLastWarning
- TowOrderIssued
- VehicleTowed

Estos eventos constituyen la fuente de información para todos los análisis posteriores.

---

# 9. Métricas primarias

La plataforma registrará únicamente información primaria.

Inicialmente se consideran:

- Cantidad total de solicitudes de estacionamiento.
- Cantidad total de asignaciones exitosas.
- Cantidad total de asignaciones fallidas.
- Cantidad total de estacionamientos ilegales.
- Distancia extra recorrida desde la solicitud hasta el estacionamiento. Caso: asignación fallida.
- Tiempo extra transcurrido desde la solicitud hasta el estacionamiento. Caso: asignación fallida.

No se calcularán internamente:

- promedios;
- máximos;
- mínimos;
- desviaciones estándar;
- índices de robustez;
- indicadores agregados.

Todo análisis estadístico será realizado externamente.

---

# 10. Definición de robustez

En esta plataforma la robustez no se define únicamente como la capacidad del sistema para recuperarse frente a perturbaciones.

La robustez se define como la capacidad del sistema para mantener un nivel aceptable de eficiencia operativa a medida que aumenta la presencia de comportamientos no cooperativos.

El comportamiento del sistema será evaluado observando la degradación progresiva de su desempeño global.

---

# 11. Degradación del sistema

Se entiende por degradación el incremento de recursos consumidos respecto del escenario ideal (sin perturbaciones).

Los principales recursos considerados serán:

- distancia total recorrida;
- tiempo total de circulación;
- tiempo de búsqueda de estacionamiento.

En etapas futuras podrán incorporarse:

- consumo energético;
- emisiones contaminantes;
- consumo de combustible;
- otros indicadores ambientales.

---

# 12. Punto de quiebre

Se define como **Punto de Quiebre** la condición experimental en la cual el sistema inteligente deja de aportar beneficios significativos respecto de un escenario sin asistencia.

En términos prácticos, un punto de quiebre ocurre cuando reservar una plaza de estacionamiento produce un beneficio general equivalente al de no utilizar el sistema.

Este criterio será evaluado principalmente mediante:

- distancia total recorrida;
- tiempo total de circulación.

En futuras versiones podrán incorporarse otros criterios de comparación.

---

# 13. Hipótesis de investigación

La hipótesis principal que guía esta plataforma es la siguiente:

> A medida que aumenta la presencia de comportamientos no cooperativos, el desempeño del sistema inteligente se degrada progresivamente hasta alcanzar uno o más puntos de quiebre en los cuales la utilización del sistema deja de aportar beneficios significativos respecto de un escenario sin asistencia.

La plataforma permitirá cuantificar dicha degradación mediante simulaciones controladas y comparar diferentes algoritmos de asignación bajo condiciones equivalentes.

---

# 14. Evolución del contrato

Este documento constituye la primera versión del contrato arquitectónico de la plataforma.

Las futuras versiones podrán incorporar, entre otras funcionalidades:

- múltiples algoritmos de asignación;
- distintos tipos de plazas;
- reservas temporales;
- peatones;
- sensores urbanos;
- comunicaciones V2X;
- predicción de demanda;
- aprendizaje automático;
- vehículos autónomos;
- nuevos indicadores de robustez.

Todas las futuras funcionalidades deberán respetar los principios establecidos en este contrato.