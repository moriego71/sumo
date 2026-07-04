# Smart Parking Platform
# Escenario S01 – Grilla 4×4
## Especificación del Escenario Experimental
**Versión:** 0.1

---

# 1. Objetivo

Construir el primer escenario de simulación suficientemente completo para validar el funcionamiento integral de la Smart Parking Platform.

Este escenario permitirá probar:

- circulación vehicular;
- solicitudes de estacionamiento;
- asignación de plazas;
- estacionamientos inteligentes;
- estacionamientos ilegales;
- reasignaciones;
- actuación de grúas;
- registro de eventos.

Este escenario constituye la base experimental sobre la cual se desarrollarán los siguientes prototipos de la plataforma.

---

# 2. Estructura de la red

La red estará formada por una cuadrícula de **4 × 4 nodos**, conectados mediante calles de una sola mano.

```text
N1 ----- N2 ----- N3 ----- N4
 |        |        |        |
 |        |        |        |
N5 ----- N6 ----- N7 ----- N8
 |        |        |        |
 |        |        |        |
N9 ----- N10 ---- N11 ---- N12
 |        |        |        |
 |        |        |        |
N13 ---- N14 ---- N15 ---- N16
```

Todos los tramos tendrán inicialmente la misma longitud para simplificar los experimentos.

---

# 3. Circulación general

La circulación normal de los vehículos se realizará únicamente sobre el anillo exterior de la red.

Los vehículos que no soliciten estacionamiento nunca ingresarán a las calles interiores.

Los vehículos que reciban una plaza asignada abandonarán temporalmente el anillo exterior, ingresarán por la calle correspondiente, estacionarán y luego regresarán a la circulación normal.

---

# 4. Ingreso del tráfico

El ingreso principal del tráfico se ubicará en:

**Nodo N1**

Desde allí se incorporarán todos los vehículos que participen de la simulación.

---

# 5. Bases de grúas

Se incorporarán dos calles auxiliares exclusivas para las grúas.

Estas calles no formarán parte del circuito normal de circulación.

---

## TowBaseNorth

Ubicación:

**Acceso por Nodo N2**

Contendrá inicialmente una única grúa.

Vehículo asociado:

**Tow01**

---

## TowBaseSouth

Ubicación:

**Acceso por Nodo N15**

Contendrá inicialmente una única grúa.

Vehículo asociado:

**Tow02**

---

# 6. Estacionamientos inteligentes

Inicialmente existirán dos plazas inteligentes.

---

## SmartPark01

Ubicación:

Entre **N2** y **N6**

Capacidad inicial:

1 vehículo.

---

## SmartPark02

Ubicación:

Entre **N15** y **N11**

Capacidad inicial:

1 vehículo.

---

# 7. Funcionamiento esperado

Los vehículos circularán normalmente sobre el anillo exterior.

Cuando un vehículo solicite estacionamiento:

1. El controlador registrará la solicitud.
2. Buscará una plaza disponible.
3. Asignará una plaza.
4. El vehículo abandonará el circuito exterior.
5. Ingresará por la calle interior correspondiente.
6. Estacionará.
7. Permanecerá estacionado el tiempo indicado.
8. Regresará posteriormente a la circulación normal.

---

# 8. Gestión de estacionamientos ilegales

Cuando un vehículo ocupe una plaza sin autorización:

1. Se detectará el estacionamiento ilegal.
2. Se emitirá una advertencia.
3. Se abrirá una ventana de regularización.
4. Si el vehículo no regulariza su situación, pasará al estado de penalización.
5. Se emitirá una última advertencia.
6. Si continúa ocupando la plaza, se ordenará el acarreo.
7. La grúa correspondiente retirará el vehículo.
8. La grúa regresará a su base.

---

# 9. Recorridos previstos de las grúas

## Tow01 (Base Norte)

Recorrido operativo previsto:

```text
Base
 ↓
N2 → N6 → N7 → N3
            ↓
       regreso a Base
```

Su zona principal de actuación será el sector norte de la ciudad.

---

## Tow02 (Base Sur)

Recorrido operativo previsto:

```text
Base
 ↓
N15 → N11 → N10 → N14
               ↓
          regreso a Base
```

Su zona principal de actuación será el sector sur de la ciudad.

---

# 10. Objetivos funcionales del escenario

Este escenario deberá permitir validar:

- circulación continua de vehículos;
- solicitudes de estacionamiento;
- asignación automática de plazas;
- ingreso y salida de los estacionamientos;
- liberación de plazas;
- reasignaciones;
- detección de estacionamientos ilegales;
- advertencias;
- penalizaciones;
- órdenes de acarreo;
- desplazamiento de las grúas;
- retiro de vehículos;
- regreso de las grúas a su base;
- registro completo de eventos.

---

# 11. Escalabilidad

Este escenario constituye el primer banco de pruebas de la plataforma.

Las versiones posteriores podrán ampliar:

- cantidad de nodos;
- cantidad de plazas;
- cantidad de vehículos;
- cantidad de grúas;
- algoritmos de asignación;
- algoritmos de despacho de grúas;
- tipos de estacionamientos;
- sensores urbanos;
- comunicación V2X;
- vehículos autónomos;
- múltiples zonas de estacionamiento.

La arquitectura del escenario deberá mantenerse compatible con el Contrato de Arquitectura de la Smart Parking Platform.

---

# 12. Propósito experimental

Este escenario permitirá realizar las primeras evaluaciones experimentales sobre el impacto de los comportamientos no cooperativos en un sistema inteligente de estacionamiento.

Los resultados obtenidos servirán como base para la construcción de escenarios urbanos de mayor complejidad y para el estudio de la robustez de los algoritmos de asignación desarrollados en la plataforma.