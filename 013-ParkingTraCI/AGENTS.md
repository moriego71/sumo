# 1. Objetivo del Proyecto

## Nombre

Smart Parking Research Platform (ParkingTraCI)

---

## Propósito

El objetivo de este proyecto es desarrollar una plataforma de investigación para el estudio de sistemas inteligentes de estacionamiento urbano utilizando SUMO y TraCI como motor de simulación y Python como lenguaje principal de desarrollo.

La plataforma deberá permitir diseñar, ejecutar y analizar experimentos relacionados con la asignación dinámica de plazas de estacionamiento, proporcionando un entorno flexible, reproducible y extensible para la investigación científica.

---

## Alcance

La plataforma evolucionará progresivamente hasta permitir:

- simular tránsito vehicular urbano;
- administrar plazas de estacionamiento;
- gestionar solicitudes y reservas;
- implementar distintos algoritmos de asignación;
- incorporar vehículos cooperativos y no cooperativos;
- administrar grúas y procesos de remoción;
- medir indicadores de desempeño;
- ejecutar experimentos reproducibles;
- comparar distintos escenarios de simulación;
- generar evidencia científica para investigaciones futuras.

---

## Filosofía del Proyecto

La plataforma será desarrollada de forma incremental.

Cada iteración deberá aportar una funcionalidad visible, completamente operativa y compatible con la arquitectura existente.

Se priorizará siempre un sistema estable y ejecutable por sobre la incorporación acelerada de nuevas funcionalidades.

---

## Naturaleza del Proyecto

Este proyecto constituye una plataforma de investigación y experimentación.

No se desarrolla con fines comerciales sino como una infraestructura científica destinada a facilitar investigaciones sobre sistemas inteligentes de estacionamiento urbano.

La arquitectura deberá privilegiar la claridad, la modularidad, la trazabilidad y la capacidad de experimentación.

---

## Evolución

La plataforma deberá evolucionar mediante la incorporación progresiva de nuevas funcionalidades, procurando que cada nueva versión mantenga compatibilidad con las versiones anteriores.

Toda nueva funcionalidad deberá integrarse respetando la arquitectura existente y minimizando el impacto sobre los componentes previamente desarrollados.

---

# 2. Objetivos Científicos

## Propósito de la investigación

La plataforma constituye la infraestructura experimental utilizada para investigar sistemas inteligentes de asignación dinámica de estacionamiento urbano.

Su finalidad es facilitar el diseño, ejecución y análisis de experimentos científicos que permitan estudiar el comportamiento de distintos algoritmos bajo diferentes condiciones de operación.

---

## Líneas de investigación

La plataforma deberá permitir desarrollar investigaciones relacionadas con:

- algoritmos inteligentes de asignación de plazas;
- reservas dinámicas de estacionamiento;
- optimización del uso del espacio urbano;
- comportamiento cooperativo y no cooperativo de los conductores;
- detección de estacionamientos indebidos;
- procesos de penalización y remoción de vehículos;
- gestión inteligente de grúas;
- comparación entre estrategias de asignación;
- análisis de desempeño bajo distintos niveles de demanda;
- generación de escenarios experimentales.

---

## Robustez del sistema

Uno de los principales objetivos científicos consiste en estudiar la robustez de los algoritmos de asignación dinámica de estacionamiento.

La robustez será entendida como la capacidad del sistema para continuar ofreciendo un servicio útil frente a comportamientos no cooperativos, ocupaciones inesperadas de plazas y otros eventos que impidan cumplir las asignaciones originalmente realizadas.

---

## Medida principal de robustez

La medida principal de robustez será la degradación del desempeño global del sistema a medida que aumenta el nivel de incumplimiento de las reglas por parte de los usuarios.

Entre los indicadores experimentales se encuentran:

- distancia adicional recorrida;
- tiempo adicional hasta lograr estacionar;
- incremento de circulación vehicular;
- aumento estimado de emisiones;
- utilización efectiva de las plazas disponibles.

El objetivo final consiste en identificar los puntos de quiebre del sistema, entendidos como aquellos escenarios donde la utilización de un sistema inteligente de reservas deja de ofrecer ventajas significativas respecto de un sistema sin reservas.

---

## Plataforma Experimental

La plataforma deberá evolucionar hacia un laboratorio de experimentación configurable.

Los escenarios experimentales deberán poder configurarse sin modificar el código fuente.

La plataforma deberá permitir parametrizar, entre otros:

- escenario urbano;
- algoritmo de asignación;
- cantidad de vehículos;
- cantidad de plazas de estacionamiento;
- cantidad de solicitudes;
- porcentaje de conductores no cooperativos;
- cantidad de grúas;
- tiempos de advertencia;
- tiempos de penalización;
- duración de las simulaciones;
- características del escenario urbano.

La plataforma deberá soportar distintos tipos de escenarios:

- escenarios predefinidos incluidos con el sistema;
- escenarios importados por el investigador;
- futuras estrategias de generación automática de escenarios.

El investigador deberá poder ejecutar nuevos experimentos modificando únicamente los parámetros del escenario, sin realizar cambios en el código fuente.

La plataforma incorporará un Panel de Control de Experimentos desde el cual será posible configurar, ejecutar y supervisar las simulaciones.

---

## Reproducibilidad

Toda ejecución experimental deberá registrar la información necesaria para permitir su reproducción posterior.

Cada experimento deberá almacenar, como mínimo:

- escenario utilizado;
- algoritmo seleccionado;
- parámetros de configuración;
- fecha y hora de ejecución;
- métricas obtenidas;
- versión de la plataforma.

---

## Visión de Largo Plazo

La plataforma deberá evolucionar hasta convertirse en una aplicación autónoma que permita a investigadores diseñar, ejecutar y analizar experimentos sin necesidad de modificar el código fuente ni poseer conocimientos de programación.

SUMO y TraCI constituirán el motor interno de simulación, mientras que la interacción con el usuario se realizará exclusivamente mediante la interfaz propia de la plataforma.

El objetivo es construir una infraestructura científica reutilizable que permita desarrollar múltiples investigaciones futuras sobre sistemas inteligentes de estacionamiento urbano.

---

# 3. Stack Tecnológico

## Lenguaje principal

El lenguaje oficial de desarrollo será **Python**.

Toda la lógica de negocio, integración con SUMO, algoritmos de asignación, gestión de métricas y control de experimentos deberá implementarse utilizando este lenguaje.

---

## Motor de simulación

La simulación utilizará:

- SUMO (Simulation of Urban Mobility)
- TraCI (Traffic Control Interface)

SUMO será responsable de la simulación del tránsito.

TraCI constituirá el único mecanismo oficial de comunicación entre la plataforma y el simulador.

---

## Persistencia

La primera versión de la plataforma utilizará archivos estructurados para almacenar la configuración de los experimentos y los resultados obtenidos.

La incorporación de una base de datos queda prevista para futuras versiones, procurando que el cambio no requiera modificaciones sobre el resto de la arquitectura.

---

## Portabilidad

La plataforma deberá desarrollarse utilizando tecnologías ampliamente soportadas y de libre disponibilidad, procurando facilitar su instalación, mantenimiento y evolución.

---

# 4. Arquitectura del Sistema

## Arquitectura General

La plataforma adoptará una **arquitectura monolítica modular**, organizada en capas y basada en la separación clara de responsabilidades.

El sistema será desarrollado como una única aplicación ejecutable, manteniendo un fuerte desacoplamiento entre sus componentes internos para facilitar su evolución y mantenimiento.

La arquitectura deberá permitir incorporar nuevas funcionalidades sin afectar el comportamiento de los módulos existentes.


---

## Organización por Capas

La arquitectura estará organizada conceptualmente en las siguientes capas:

- Interfaz de Usuario (UI)
- Aplicación (Casos de Uso)
- Dominio (Lógica de Negocio)
- Infraestructura (SUMO, TraCI, Persistencia y Exportación)

Cada capa deberá interactuar únicamente con las capas definidas por la arquitectura.

---

## Principios Arquitectónicos

Toda evolución del sistema deberá respetar los siguientes principios:

- Responsabilidad única por módulo.
- Alta cohesión.
- Bajo acoplamiento.
- Separación entre lógica de negocio e infraestructura.
- Separación entre simulación y reglas de negocio.
- Componentes reutilizables.
- Arquitectura preparada para evolución incremental.
- Compatibilidad hacia atrás siempre que sea posible.

### Modelado mediante máquinas de estados

Siempre que el dominio represente comportamientos, procesos o ciclos de vida, éstos deberán modelarse explícitamente mediante estados y transiciones de estado.

Se evitarán implementaciones basadas en múltiples variables booleanas o lógica condicional dispersa cuando un modelo de estados resulte más claro, mantenible y expresivo.

Las transiciones deberán producirse únicamente a través de eventos claramente definidos y respetar las reglas de negocio del dominio.

Cuando corresponda, la documentación de la funcionalidad deberá incluir el diagrama de estados correspondiente.


### Desacoplamiento entre infraestructura y estrategias

La infraestructura experimental deberá permanecer desacoplada de las estrategias específicas de asignación, reserva o circulación implementadas.

Las estrategias constituirán componentes intercambiables, permitiendo evaluar una misma infraestructura bajo distintos algoritmos sin modificar la plataforma.

Siempre que resulte posible, este desacoplamiento deberá implementarse mediante abstracciones, interfaces o patrones de diseño que favorezcan la extensibilidad de la plataforma.

La plataforma deberá separar claramente:

- la infraestructura experimental;
- la definición de los experimentos;
- la ejecución de los experimentos;
- el análisis de los resultados.

Cada uno de estos componentes deberá poder evolucionar independientemente.

---

## Lógica de Negocio

Toda la inteligencia del sistema deberá implementarse en Python.

SUMO tendrá exclusivamente la responsabilidad de simular el tránsito vehicular.

TraCI constituirá únicamente el mecanismo de comunicación entre la plataforma y el simulador.

Las decisiones relacionadas con:

- asignación de plazas;
- reservas;
- reasignaciones;
- detección de infracciones;
- administración de grúas;
- cálculo de métricas;
- gestión de experimentos;

deberán implementarse exclusivamente dentro de la lógica de negocio de la plataforma.

---

## Módulos Funcionales

La arquitectura podrá evolucionar incorporando módulos especializados.

Inicialmente se consideran, entre otros:

- Experiment Manager
- Simulation Manager
- Scenario Manager
- Assignment Manager 
- Vehicle Manager
- Parking Manager
- Tow Manager
- Metrics Manager
- UI Manager

La organización definitiva podrá evolucionar durante el desarrollo del proyecto.

---

## Algoritmos de Asignación

Los algoritmos de asignación deberán diseñarse como componentes intercambiables.

La incorporación de un nuevo algoritmo no deberá requerir modificaciones sobre el resto del sistema.

La plataforma deberá facilitar la comparación experimental entre distintos algoritmos de asignación.

---

## Escenarios Urbanos

Los escenarios urbanos serán independientes de la lógica de negocio.

La plataforma deberá permitir trabajar con:

- escenarios predefinidos;
- escenarios importados por el investigador;
- futuros escenarios generados automáticamente.

La incorporación de nuevos escenarios no deberá requerir modificaciones en la arquitectura del sistema.

---

## Persistencia

La persistencia deberá permanecer desacoplada del resto de la aplicación.

El mecanismo de almacenamiento podrá evolucionar desde archivos estructurados hacia bases de datos u otras tecnologías sin afectar la lógica de negocio.

---

## Interfaz de Usuario

La interfaz de usuario constituirá un componente independiente de la plataforma.

SUMO será utilizado como motor de simulación, pero no representará la interfaz principal del investigador.

La interfaz evolucionará progresivamente hasta convertirse en un Panel de Control de Experimentos desde el cual será posible:

- configurar escenarios;
- seleccionar algoritmos;
- ejecutar simulaciones;
- pausar y reanudar experimentos;
- monitorear métricas en tiempo real;
- exportar resultados.

La evolución de la interfaz no deberá requerir modificaciones en la lógica de negocio.

---

## Evolución Arquitectónica

La arquitectura deberá diseñarse pensando en una evolución de largo plazo.

Las decisiones adoptadas deberán favorecer la incorporación futura de:

- nuevos algoritmos;
- nuevos tipos de escenarios;
- nuevas métricas;
- nuevos módulos de inteligencia artificial;
- nuevas estrategias de experimentación;
- nuevas interfaces de usuario.

Toda nueva funcionalidad deberá integrarse mediante extensión de la arquitectura existente, evitando modificaciones innecesarias sobre componentes previamente desarrollados.

---

# 5. Filosofía de Desarrollo

El desarrollo de la plataforma seguirá una estrategia incremental, priorizando siempre la simplicidad, la estabilidad y la evolución controlada del sistema.

Cada iteración deberá producir una mejora concreta y verificable sobre la versión anterior.

No se implementarán funcionalidades futuras "por anticipación". Cada componente deberá desarrollarse únicamente cuando exista una necesidad real dentro del proyecto.

La plataforma deberá, dentro de lo posible, producir resultados visibles desde las primeras iteraciones.

---

## Desarrollo incremental

Cada iteración deberá incorporar una única funcionalidad principal.

Se evitarán iteraciones excesivamente grandes que dificulten la revisión del código o la validación del comportamiento del sistema.

---

## Simplicidad

Siempre deberá preferirse la solución más simple que cumpla correctamente con los requisitos actuales.

No deberán incorporarse mecanismos complejos para resolver problemas que aún no existen.

---

## Evolución continua

La arquitectura deberá evolucionar mediante pequeñas mejoras sucesivas.

Las refactorizaciones serán parte natural del desarrollo siempre que mejoren la calidad del sistema sin modificar su comportamiento observable.

---

## Estabilidad

Toda nueva funcionalidad deberá preservar el correcto funcionamiento de las funcionalidades previamente implementadas.

Antes de dar una iteración por finalizada deberá verificarse que no se hayan introducido regresiones.

---

## Una responsabilidad por iteración

Cada iteración deberá tener un objetivo claramente definido.

No deberán mezclarse múltiples funcionalidades independientes dentro de una misma implementación.

---

## Calidad sobre velocidad

La prioridad del proyecto será construir una plataforma sólida y mantenible.

Se evitarán soluciones rápidas que comprometan la arquitectura o dificulten la evolución futura del sistema.

---

## Aprendizaje continuo

La plataforma constituye simultáneamente:

- un proyecto de investigación;
- una plataforma experimental;
- una herramienta de aprendizaje.

Las decisiones técnicas deberán favorecer la comprensión del sistema y facilitar su mantenimiento futuro.

---

# 6. Estándares de Implementación

Toda implementación realizada dentro del proyecto deberá respetar los siguientes criterios generales.

---

## Simplicidad

Se deberá implementar la solución más simple que satisfaga correctamente los requisitos actuales.

Se evitará incorporar complejidad innecesaria o funcionalidades anticipadas.

Las soluciones deberán privilegiar la mantenibilidad del software por sobre optimizaciones prematuras de rendimiento.

---

## Legibilidad

El código deberá priorizar la claridad por sobre la cantidad de líneas.

Las implementaciones deberán resultar fáciles de comprender por otro desarrollador sin necesidad de explicaciones adicionales.

---

## Responsabilidad única

Cada clase, módulo o función deberá tener una única responsabilidad claramente definida y explicada mediante comentarios precedentes.

Se evitarán componentes que concentren múltiples responsabilidades.

---

## Bajo acoplamiento

Los módulos deberán depender de abstracciones siempre que resulte razonable.

Se evitarán dependencias innecesarias entre componentes.

---

## Alta cohesión

Cada módulo deberá agrupar únicamente funcionalidades relacionadas con una misma responsabilidad.

---

## Evitar duplicación

No deberá duplicarse lógica de negocio.

Cuando una funcionalidad sea reutilizable deberá abstraerse adecuadamente comentando el patron usado para tal fin.

---

## Nombres descriptivos

Los nombres de clases, funciones, variables y módulos deberán describir claramente su propósito.

Se evitarán abreviaturas innecesarias.

---

## Funciones pequeñas

Las funciones deberán ser breves y realizar una única tarea.

Cuando una función comience a asumir múltiples responsabilidades deberá refactorizarse.

---

## Comentarios

Los comentarios deberán utilizarse únicamente cuando aporten información que no resulte evidente leyendo el código.

No deberán utilizarse comentarios para explicar código confuso; en esos casos deberá mejorarse la implementación.

---

## Refactorización continua

Si durante una iteración se detecta una mejora arquitectónica que no modifica el comportamiento observable del sistema, podrá realizarse la refactorización correspondiente, manteniendo siempre la simplicidad del proyecto.

---

## Consistencia

Toda nueva implementación deberá seguir el mismo estilo, organización y convenciones ya existentes en el proyecto.

No deberán introducirse estilos diferentes dentro de una misma base de código.

---

## Explicación antes de implementar

Antes de generar código, la IA deberá explicar brevemente:

- qué archivos creará;
- qué archivos modificará;
- por qué son necesarios esos cambios.

Solo después de esa explicación deberá comenzar la implementación.

---

## Principios SOLID

Toda implementación deberá respetar, siempre que resulte razonable, los principios SOLID.

En particular, se deberá prestar especial atención a:

- Mantener una única responsabilidad por clase o módulo (SRP).
- Diseñar componentes abiertos a extensión y cerrados a modificación (OCP).
- Garantizar que las implementaciones puedan sustituirse sin alterar el comportamiento esperado (LSP).
- Evitar interfaces excesivamente grandes o con responsabilidades múltiples (ISP).
- Favorecer la dependencia de abstracciones antes que de implementaciones concretas (DIP).

Cuando una decisión de diseño implique apartarse de alguno de estos principios, la justificación deberá ser explícita y responder a una necesidad concreta del proyecto.

---

# 7. Convenciones del Proyecto

Las siguientes convenciones deberán respetarse en todas las implementaciones realizadas dentro del proyecto.

---

## Idioma

Se utilizarán los siguientes idiomas según el contexto:

- Código fuente: inglés.
- Nombres de clases, funciones y variables: inglés.
- Nombres de archivos de código: inglés.
- Documentación técnica: castellano.
- Comentarios del código: castellano.
- Mensajes dirigidos al usuario: castellano.

---

## Organización del código

Cada archivo deberá contener únicamente los elementos relacionados con una misma responsabilidad.

Se evitarán archivos excesivamente extensos.

Cuando un archivo comience a concentrar múltiples responsabilidades deberá dividirse.

---

## Dependencias

Solo podrán incorporarse nuevas dependencias cuando exista una necesidad técnica claramente justificada.

Antes de incorporar una nueva biblioteca deberá evaluarse si el problema puede resolverse utilizando herramientas ya disponibles dentro del proyecto.

---

## Salidas de la IA

Toda respuesta que implique generar documentación deberá entregarse en formato Markdown listo para copiar y pegar.

Cuando se genere código, éste deberá entregarse completo, evitando fragmentos incompletos o referencias implícitas.

Cuando una implementación requiera modificar varios archivos, la IA deberá indicar claramente qué archivos crea, modifica o elimina.

---

## Consistencia

Toda nueva implementación deberá respetar las convenciones previamente adoptadas por el proyecto.

No deberán introducirse cambios de estilo, organización o nomenclatura sin una justificación explícita.

---

## Evolución de las convenciones

Las convenciones definidas en este documento podrán evolucionar durante el proyecto cuando exista un beneficio claro para la mantenibilidad o la calidad general del sistema.

Toda modificación deberá mantener la coherencia con el resto del AGENTS.

---

## Explicaciones

Antes de implementar una solución, la IA deberá explicar brevemente la decisión de diseño adoptada.

Las explicaciones deberán ser concisas y centrarse en las razones técnicas de la solución propuesta.

---

# 8. Documentación

La documentación constituye una parte esencial del proyecto y deberá mantenerse sincronizada con la evolución del sistema.

Se documentará únicamente aquello que aporte valor para la comprensión, mantenimiento o evolución futura de la plataforma.

La documentación innecesaria o redundante deberá evitarse.

---

## Idioma

Toda la documentación del proyecto deberá redactarse íntegramente en castellano.

La única excepción será la referencia explícita a elementos definidos en el código fuente, tales como nombres de clases, funciones, métodos, variables, módulos, archivos, directorios, constantes o cualquier otro identificador implementado en inglés. Estos identificadores deberán conservar exactamente su nombre original para evitar ambigüedades entre la documentación y la implementación.

---

## Pragmatismo

La documentación deberá facilitar el desarrollo del proyecto, no convertirse en un obstáculo para su avance.

Siempre se buscará el equilibrio entre documentación suficiente y desarrollo efectivo del software.

---

## Actualización

Toda modificación relevante de la arquitectura, del comportamiento del sistema o de las decisiones de diseño deberá reflejarse en la documentación correspondiente.

La documentación nunca deberá quedar desactualizada respecto de la implementación.

---

## Nivel de detalle

La documentación deberá ser clara, concreta y proporcional a la complejidad de la funcionalidad implementada.

Se evitarán explicaciones excesivamente extensas cuando una descripción breve resulte suficiente.

---

## Trazabilidad

Siempre que resulte conveniente, la documentación deberá mantener trazabilidad entre:

- requerimientos;
- decisiones de diseño;
- implementación;
- resultados experimentales.

---

## Formato

Toda la documentación deberá escribirse en formato Markdown (.md).

Los documentos deberán estar listos para copiar y pegar sin requerir ediciones posteriores.

---

## Diagramas

Cuando una explicación resulte significativamente más clara mediante un diagrama, la IA podrá proponer su utilización.

Los diagramas deberán mantenerse simples y centrarse únicamente en los elementos relevantes.

---

## Consistencia documental

La documentación deberá mantener un estilo homogéneo en todo el proyecto.

No deberán coexistir documentos que describan el mismo comportamiento de maneras contradictorias.

---

## Documentar decisiones, no el código

La documentación deberá explicar principalmente:

- por qué se tomó una decisión;
- qué problema resuelve;
- qué alternativas fueron descartadas cuando resulte relevante.

No deberá utilizarse la documentación para describir literalmente el funcionamiento interno del código fuente.

---

# 9. Control de Versiones

## Uso de Git

Todo cambio incorporado al proyecto deberá registrarse mediante Git.

Cada commit deberá representar una unidad lógica de trabajo claramente identificable.

Se evitarán commits que agrupen modificaciones no relacionadas entre sí.

---

## Convención de commits

Los mensajes de commit deberán redactarse en inglés y respetar la especificación Conventional Commits.

Se utilizarán, según corresponda, los siguientes prefijos:

- feat:
- fix:
- refactor:
- docs:
- test:
- chore:
- perf:
- build:
- ci:

El mensaje deberá describir de forma breve y precisa el propósito del cambio.

---

## Frecuencia de commits

Se recomienda realizar commits pequeños y frecuentes.

Cada iteración podrá contener múltiples commits intermedios.

La iteración deberá finalizar con un commit estable que cumpla el Quality Gate definido para dicha iteración.

Los commits deberán reflejar la evolución real del proyecto y facilitar la reconstrucción histórica de las decisiones de diseño e implementación.

---

# 10. Interacción con el Desarrollador

La IA deberá actuar como un asistente técnico de ingeniería de software, colaborando activamente en el diseño, implementación y evolución del proyecto.

Las respuestas deberán priorizar la claridad, la precisión técnica y el razonamiento por sobre la generación automática de código.

---

## Explicación previa

Antes de implementar una solución, la IA deberá explicar brevemente:

- el enfoque propuesto;
- los archivos que serán creados o modificados;
- el motivo de cada cambio.

La implementación comenzará únicamente después de dicha explicación.

---

## Detección de inconsistencias

Si la IA detecta contradicciones entre los requerimientos, la arquitectura o las decisiones previamente adoptadas, deberá informarlo antes de continuar.

No deberá asumir interpretaciones ambiguas sin advertirlo.

---

## Propuestas de mejora

Cuando la IA identifique una alternativa significativamente mejor desde el punto de vista técnico, podrá proponerla.

La decisión final siempre corresponderá al desarrollador.

---

## Respeto por las decisiones del proyecto

Las decisiones arquitectónicas previamente adoptadas deberán respetarse durante todas las iteraciones.

La IA no deberá modificar la arquitectura, incorporar nuevas tecnologías o cambiar convenciones del proyecto sin una justificación explícita.

---

## Resolución de dudas

Ante requisitos ambiguos o incompletos, la IA deberá solicitar las aclaraciones necesarias antes de generar una implementación.

---

## Transparencia

La IA deberá indicar claramente cuando una respuesta represente:

- una decisión basada en el AGENTS;
- una recomendación técnica;
- una hipótesis;
- una limitación o incertidumbre.

---

# 11. Evolución del Proyecto

La plataforma deberá evolucionar de forma controlada, preservando la estabilidad de la arquitectura y facilitando la incorporación de nuevas funcionalidades.

Toda evolución deberá procurar aumentar las capacidades de la plataforma sin comprometer su mantenibilidad ni la claridad del diseño.

---

## Compatibilidad

Las nuevas funcionalidades deberán integrarse respetando la arquitectura existente.

Siempre que sea posible, una nueva característica deberá incorporarse mediante extensión antes que modificando componentes ya consolidados.

---

## Escalabilidad funcional

La arquitectura deberá facilitar la incorporación futura de:

- nuevos algoritmos de asignación;
- nuevas estrategias de circulación;
- nuevos tipos de vehículos;
- nuevos escenarios urbanos;
- nuevas métricas;
- nuevos experimentos;
- nuevas interfaces de usuario.

La incorporación de estas funcionalidades deberá requerir modificaciones mínimas sobre el sistema existente.

---

## Plataforma experimental

La plataforma deberá evolucionar hacia un entorno de experimentación configurable.

Los parámetros de los experimentos deberán poder modificarse sin alterar el código fuente.

Siempre que resulte posible, la configuración deberá realizarse mediante archivos de configuración o mediante la interfaz gráfica de la aplicación.

---

## Reutilización

Antes de implementar una nueva funcionalidad deberá evaluarse si existen componentes reutilizables dentro del proyecto.

Se evitará la duplicación de soluciones equivalentes.

---

## Refactorización

La refactorización constituye una actividad normal del desarrollo.

Podrá realizarse siempre que:

- no modifique el comportamiento observable del sistema;
- mejore la mantenibilidad;
- simplifique la arquitectura;
- reduzca el acoplamiento;
- aumente la claridad del código.


La refactorización deberá realizarse de forma controlada y justificada.

Cuando una refactorización implique cambios estructurales relevantes, la IA deberá explicar:

- qué problema motivó la refactorización;
- qué componentes fueron modificados;
- qué mejora aporta;
- qué riesgos fueron evaluados;
- qué principio SOLID se estaba violando;
- si se mantiene el mismo comportamiento observable.

Las refactorizaciones menores no requerirán documentación adicional.

---

## Evolución de la arquitectura

La arquitectura podrá evolucionar durante el proyecto cuando exista una mejora técnica claramente justificada.

Toda modificación arquitectónica deberá preservar los principios definidos en este AGENTS y mantener la coherencia general de la plataforma.

---

# 12. Toma de Decisiones Técnicas

Durante el desarrollo del proyecto podrán existir múltiples alternativas técnicamente válidas para resolver un mismo problema.

La IA deberá seleccionar siempre la alternativa que mejor se alinee con los objetivos generales del proyecto y con las reglas establecidas en este AGENTS.

---

## Prioridades

Ante distintas alternativas de implementación, el siguiente orden de prioridad deberá prevalecer:

1. Correcto funcionamiento.
2. Claridad de la solución.
3. Mantenibilidad.
4. Simplicidad.
5. Extensibilidad.
6. Reutilización.
7. Rendimiento.

Las optimizaciones de rendimiento sólo deberán incorporarse cuando exista una necesidad demostrable.

---

## Consistencia

Las nuevas implementaciones deberán mantener coherencia con la arquitectura, el estilo y las decisiones previamente adoptadas.

No deberán introducirse soluciones alternativas para problemas ya resueltos dentro del proyecto sin una justificación técnica.

---

## Evaluación de alternativas

Cuando existan varias soluciones razonables y la diferencia entre ellas resulte significativa, la IA deberá presentar brevemente las alternativas junto con sus ventajas y desventajas antes de proponer una implementación.

---

## Conservación de la arquitectura

Ninguna decisión técnica deberá comprometer la arquitectura general del sistema para resolver una necesidad puntual.

Las soluciones locales no deberán deteriorar la calidad global del proyecto.

---

## Justificación

Toda decisión de diseño que implique modificar la arquitectura, incorporar nuevas dependencias o apartarse de las reglas definidas en este AGENTS deberá estar debidamente justificada.

---

# 13. Estrategia de Pruebas

Toda funcionalidad incorporada al proyecto deberá ser validada antes de considerarse finalizada.

La estrategia de pruebas evolucionará junto con la plataforma, aumentando progresivamente su nivel de cobertura a medida que el proyecto crezca.

---

## Evolución gradual

Durante las primeras iteraciones se priorizará la correcta implementación de la arquitectura y de las funcionalidades principales.

La incorporación de pruebas automatizadas se realizará de manera progresiva, acompañando la madurez del proyecto.

---

## Tipos de pruebas

A medida que la plataforma evolucione podrán incorporarse distintos niveles de validación, entre ellos:

- pruebas unitarias;
- pruebas de integración;
- pruebas funcionales;
- pruebas end-to-end;
- pruebas experimentales.

La necesidad de cada tipo de prueba dependerá de la complejidad de la funcionalidad implementada.

---

## No introducir regresiones

Toda nueva implementación deberá preservar el correcto funcionamiento de las funcionalidades previamente desarrolladas.

Cuando resulte necesario deberán ejecutarse nuevamente las pruebas correspondientes.

---

## Trazabilidad

Las pruebas deberán validar el comportamiento observable del sistema y no únicamente detalles internos de implementación.

---

## Evolución

La estrategia de pruebas podrá ampliarse y refinarse durante el desarrollo del proyecto conforme aumente la complejidad de la plataforma.

---

# 14. Revisión Arquitectónica

La arquitectura del sistema deberá revisarse periódicamente para garantizar que continúe respetando los principios definidos en este AGENTS.

La revisión arquitectónica constituye una actividad de control y mejora continua, cuyo objetivo es detectar tempranamente problemas de diseño antes de que afecten la evolución del proyecto y reducir al mínimo la duda técnica.

---

## Objetivos

Toda revisión arquitectónica deberá verificar, entre otros aspectos:

- cumplimiento de la arquitectura definida;
- separación adecuada de responsabilidades;
- bajo acoplamiento entre módulos;
- alta cohesión;
- cumplimiento de los principios SOLID;
- ausencia de dependencias innecesarias;
- consistencia general del diseño.

---

## Alcance

Las revisiones arquitectónicas deberán centrarse principalmente en decisiones de diseño y organización del software.

No constituyen una revisión funcional ni reemplazan las pruebas del sistema.

Se realizará una revisión arquitectónica al finalizar toda iteración que incorpore cambios arquitectónicos o modificaciones estructurales significativas.

---

## Registro

Las conclusiones de cada revisión deberán registrarse en el documento:

docs/arquitectura/revision-arquitectonica.md

El registro deberá reflejar únicamente los aspectos relevantes detectados durante la revisión.

---

## Acciones Correctivas

Cuando durante una revisión se detecten problemas arquitectónicos relevantes, éstos deberán documentarse junto con la acción correctiva propuesta.

La corrección podrá realizarse en la misma iteración o planificarse para una iteración posterior cuando no represente un riesgo inmediato para la evolución del proyecto.

---

## Mejora Continua

Las revisiones arquitectónicas tienen como finalidad preservar la calidad del sistema durante toda su evolución.

Su objetivo no es impedir el avance del proyecto, sino facilitar una evolución ordenada, mantenible y coherente.

---

# 15. Atributos de Calidad de la Plataforma

La plataforma posee un doble objetivo:

- constituir un software de alta calidad desde el punto de vista de la ingeniería;
- constituir una herramienta confiable para la investigación científica.

Por este motivo, los atributos de calidad se agrupan en dos categorías complementarias.

Estos atributos constituyen objetivos permanentes del proyecto y deberán considerarse durante el diseño, implementación, revisión arquitectónica y validación de cada iteración.

---

## 15.1 Atributos de Ingeniería

En esta sección se definen los atributos relacionados con la calidad del software como producto de ingeniería.

- Mantenibilidad
- Modularidad
- Extensibilidad
- Configurabilidad
- Robustez
- Usabilidad
- Trazabilidad
- Observabilidad
- Auditabilidad

### Mantenibilidad
El sistema deberá ser fácil de comprender, corregir, modificar y ampliar.

Toda nueva funcionalidad deberá integrarse preservando la claridad de la arquitectura y evitando aumentar innecesariamente la complejidad del código.

---

### Modularidad
La plataforma deberá organizarse mediante módulos con responsabilidades claramente definidas.

La incorporación o modificación de un módulo deberá generar el menor impacto posible sobre el resto del sistema.

Idealmente, una modificación deberá poder realizarse sin afectar el comportamiento de otros módulos.

Cuando ello no resulte posible, la IA deberá:

- explicar el impacto generado;
- justificar técnicamente la decisión;
- registrar el cambio correspondiente;
- proponer una refactorización cuando resulte conveniente.

---

### Extensibilidad
La arquitectura deberá facilitar la incorporación de nuevas funcionalidades sin requerir modificaciones importantes sobre componentes existentes.

Siempre que resulte conveniente deberán utilizarse mecanismos de abstracción (interfaces, polimorfismo o patrones de diseño apropiados) que favorezcan la incorporación de nuevas funcionalidades.

---

### Configurabilidad
Los parámetros configurables deberán poder modificarse sin alterar el código fuente.

Siempre que resulte posible, la configuración deberá realizarse mediante archivos de configuración o mediante la interfaz de usuario.

---

### Robustez
La plataforma deberá continuar funcionando correctamente aun cuando se produzcan situaciones inesperadas.

Los errores deberán aislarse adecuadamente evitando comprometer la estabilidad del sistema.

Cuando ocurra un error relevante deberá:

- registrarlo automáticamente en formato Markdown;
- almacenarlo dentro del historial del proyecto;
- informar claramente al usuario;
- permitir consultar posteriormente el detalle del incidente.

---

### Usabilidad
La plataforma deberá poder ser utilizada tanto por usuarios con conocimientos de programación como por investigadores sin experiencia en desarrollo de software.

La interfaz deberá priorizar:

- simplicidad;
- claridad;
- consistencia;
- facilidad de aprendizaje.

---

### Trazabilidad
Toda decisión arquitectónica, experimento, resultado y modificación relevante deberá poder rastrearse a través de la documentación del proyecto.

---

### Observabilidad
La plataforma deberá proporcionar información suficiente para comprender el estado interno de una simulación durante su ejecución.

Siempre que resulte posible deberán registrarse las variables relevantes para facilitar el análisis y diagnóstico del comportamiento del sistema.

---

### Auditabilidad
Toda ejecución experimental deberá dejar evidencia suficiente para permitir su posterior revisión, análisis y auditoría.

---

## 15.2 Atributos Científicos
En esta sección se definen los atributos relacionados con la calidad de la plataforma como herramienta de investigación científica.

- Confiabilidad Experimental
- Reproducibilidad Experimental
- Escalabilidad Experimental
- Evolución Científica
- Reutilización Científica

### Confiabilidad Experimental
La plataforma deberá garantizar que los resultados obtenidos representen fielmente el comportamiento del experimento ejecutado.

Toda métrica deberá derivarse de datos consistentes, verificables y científicamente válidos.

La plataforma no deberá introducir sesgos no intencionales que puedan afectar las conclusiones de una investigación.

---

### Reproducibilidad Experimental
La plataforma deberá permitir repetir un experimento bajo las mismas condiciones de ejecución.

Cuando existan componentes aleatorios, deberá registrar toda la información necesaria para posibilitar su reproducción posterior, incluyendo la configuración utilizada y, cuando corresponda, la semilla del generador pseudoaleatorio.

---

### Escalabilidad Experimental
La plataforma deberá permitir incrementar progresivamente la complejidad de los experimentos sin requerir rediseños arquitectónicos.

Deberá facilitar el aumento de:

- cantidad de vehículos;
- cantidad de plazas;
- tamaño de los escenarios;
- incorporación de nuevos escenarios;
- cantidad de usuarios colaborativos;
- cantidad de usuarios no colaborativos;
- cantidad de grúas;
- cantidad de métricas;
- cantidad de eventos registrados.

---

### Evolución Científica
La plataforma deberá facilitar la incorporación de nuevas hipótesis de investigación.

Cuando una nueva hipótesis requiera modificaciones arquitectónicas, la IA deberá exponer previamente el impacto esperado, analizar alternativas y discutirlas con el diseñador antes de implementar cualquier cambio.

---

### Reutilización Científica
La plataforma deberá diseñarse para ser utilizada por otros investigadores, evitando soluciones específicas para un único experimento siempre que ello resulte razonable.

---

# 16. Priorización y Resolución de Trade-offs

## Principio General

La corrección funcional constituye un requisito fundamental del proyecto.

Ningún atributo de calidad podrá prevalecer sobre la correcta funcionalidad del sistema.

---

## Prioridad de los Atributos
Los atributos de calidad no poseen todos la misma importancia.

Cuando durante el diseño o la implementación exista un conflicto potencial entre atributos, la IA deberá considerar la siguiente priorización.

### Prioridad Crítica

#### Ingeniería
- Mantenibilidad
- Modularidad
- Extensibilidad
- Robustez

#### Científicos
- Confiabilidad Experimental
- Reproducibilidad Experimental


### Prioridad Alta

#### Ingeniería
- Configurabilidad
- Trazabilidad

#### Científicos
- Escalabilidad Experimental
- Evolución Científica
- Reutilización Científica


### Prioridad Deseable

#### Ingeniería
- Usabilidad
- Observabilidad
- Auditabilidad

La priorización anterior constituye una guía general.

La resolución concreta de los conflictos entre atributos se establecerá en las matrices de resolución de Trade-offs (Sección 16).

### Regla General de Resolución de Conflictos

Cuando exista un conflicto entre atributos de calidad y no se encuentre contemplado explícitamente en las matrices de resolución de Trade-offs (Sección 16), la IA deberá aplicar el siguiente orden general de prioridad:

1. Corrección funcional.
2. Confiabilidad Experimental.
3. Reproducibilidad Experimental.
4. Atributos de prioridad crítica.
5. Atributos de prioridad alta.
6. Atributos de prioridad deseable.

Este orden constituye la regla general de decisión. No obstante, cuando exista un Trade-off específico definido en la Sección 16 para un conflicto determinado, dicho Trade-off prevalecerá sobre esta regla general.

---

# 17- Resolución de Trade-offs

Durante el diseño e implementación podrán presentarse conflictos entre dos o más atributos de calidad.

Cuando ello ocurra, la IA deberá resolverlos respetando la priorización definida en el punto anterior y las reglas particulares establecidas en esta sección.

Si un conflicto no estuviera contemplado explícitamente, la IA deberá:

- identificar los atributos involucrados;
- explicar el conflicto existente;
- proponer las alternativas posibles;
- analizar ventajas y desventajas de cada una;
- solicitar la decisión del diseñador antes de implementar la solución.

---

A continuación se presenta la matriz de resolución de Trade-offs del proyecto.

## Matrices de Resolución de Trade-offs
Los siguientes Trade-offs representan decisiones arquitectónicas permanentes del proyecto. Constituyen reglas de diseño que la IA deberá respetar durante toda la evolución de la plataforma. Cuando un conflicto no se encuentre contemplado explícitamente, deberá aplicarse la Regla General de Resolución de Conflictos definida en la Sección 15.

## 16.1 Prioridad Científica

| Conflicto     | Se prioriza   | Acción esperada              | Justificación       |
|---------------|---------------|------------------------------|---------------------|
| Confiabilidad | Confiabilidad | Mantener la fidelidad de la  | La plataforma debe  |
| Experimental  | Experimental  | simulación, aunque aumente   | producir resultados |
|      vs.      |               | el tiempo de ejecución.      | científicamente     |
| Rendimiento   |               | Optimizar únicamente cuando  | confiables.         |
|               |               | pueda demostrarse que la     |                     |
|               |               | validez científica no se ve  |                     |
|               |               | afectada.                    |                     |
|---------------|---------------|------------------------------|---------------------|
| Confiabilidad | Confiabilidad | Adoptar la solución que      | La simplicidad      |
| Experimental  | Experimental  | garantice la validez del     | nunca deberá        |
|      vs.      |               | experimento, aunque implique | comprometer la      |
| Simplicidad   |               | mayor complejidad de         | calidad científica. |
|               |               | implementación.              |                     |
|---------------|---------------|------------------------------|---------------------|
| Confiabilidad | Confiabilidad | Validar automáticamente      | Evitar resultados   |
| Experimental  | Experimental  | toda configuración           | inválidos derivados |
|      vs.      |               | experimental antes de        | de configuraciones  |
| Configurabi-  |               | ejecutar la simulación.      | incorrectas.        |
| lidad         |               | Impedir configuraciones      |                     |
|               |               | inconsistentes.              |                     |
|---------------|---------------|------------------------------|---------------------|
| Confiabilidad | Confiabilidad | Los mecanismos de            | Es preferible       |
| Experimental  | Experimental  | recuperación deberán         | detener un          |
|      vs.      |               | preservar siempre la         | experimento antes   |
| Robustez      |               | integridad de los datos      | que producir        |
|               |               | experimentales. Nunca        | resultados          |
|               |               | ocultar ni alterar           | incorrectos.        |
|               |               | resultados.                  |                     |
|---------------|---------------|------------------------------|---------------------|
| Confiabilidad | Ambos         | Registrar automáticamente    | Ambos atributos     |
| Experimental  |               | la configuración,            | son esenciales      |
|      vs.      |               | escenario, versión del       | para la             |
| Reproducibi-  |               | software y, cuando           | investigación       |
| lidad         |               | corresponda, la semilla      | científica.         |
| Experimental  |               | utilizada.                   |                     |
--------------------------------------------------------------------------------------



## 17.2 Arquitectura del Software

+-----------------+-----------------+------------------------------+----------------------+
| Conflicto       | Se prioriza     | Acción esperada              | Justificación        |
+-----------------+-----------------+------------------------------+----------------------+
| Modularidad     | Modularidad     | Mantener la separación       | Reduce deuda         |
| vs.             |                 | entre módulos aunque         | técnica y facilita   |
| Rapidez de      |                 | implique un mayor            | la evolución         |
| implementación  |                 | esfuerzo inicial.            | futura.              |
+-----------------+-----------------+------------------------------+----------------------+
| Modularidad     | Modularidad     | Mantener la arquitectura     | La mantenibilidad    |
| vs.             |                 | modular. Sólo aceptar        | prevalece sobre      |
| Rendimiento     |                 | excepciones cuando exista    | optimizaciones       |
|                 |                 | evidencia objetiva y         | prematuras.          |
|                 |                 | aprobación del diseñador.    |                      |
+-----------------+-----------------+------------------------------+----------------------+
| Extensibilidad  | Solución        | Diseñar únicamente las       | Buscar el equilibrio |
| vs.             | simple que      | abstracciones justificadas   | entre simplicidad y  |
| Simplicidad     | permita         | por la evolución prevista,   | evolución futura.    |
|                 | evolucionar     | evitando sobreingeniería.    |                      |
+-----------------+-----------------+------------------------------+----------------------+
| Configurabilidad| Configurabilidad| Todo parámetro relevante     | La plataforma debe   |
| vs.             |                 | deberá poder modificarse     | ser utilizable sin   |
| Complejidad     |                 | sin alterar el código        | necesidad de         |
|                 |                 | fuente.                      | programar.           |
+-----------------+-----------------+------------------------------+----------------------+
| Robustez        | Robustez        | Ante condiciones             | La estabilidad       |
| vs.             |                 | inesperadas, fallar de       | prevalece sobre la   |
| Rendimiento     |                 | forma controlada antes       | velocidad.           |
|                 |                 | que continuar con            |                      |
|                 |                 | resultados incorrectos.      |                      |
+-----------------+-----------------+------------------------------+----------------------+
| Flexibilidad    | Arquitectura    | Evitar soluciones rápidas    | La plataforma está   |
| Arquitectónica  | sostenible      | que comprometan la           | pensada para         |
| vs.             |                 | evolución futura. Si una     | evolucionar durante  |
| Entrega de      |                 | solución temporal resulta    | muchos años.         |
| Resultados      |                 | necesaria, documentarla y    |                      |
|                 |                 | planificar explícitamente    |                      |
|                 |                 | su refactorización.          |                      |
+-----------------+-----------------+------------------------------+----------------------+



## 17.3 Plataforma de Investigación

La prioridad del proyecto es construir una plataforma de investigación reutilizable.

Las investigaciones particulares deberán desarrollarse sobre dicha plataforma y no deberán condicionar negativamente su evolución, reutilización o calidad arquitectónica.

+-----------------+-----------------+------------------------------+----------------------+
| Conflicto       | Se prioriza     | Acción esperada              | Justificación        |
+-----------------+-----------------+------------------------------+----------------------+
| Evolución       | Estabilidad     | Incorporar nuevas            | Preservar la         |
| Científica      | del Núcleo      | hipótesis mediante           | estabilidad          |
| vs.             |                 | módulos, extensiones o       | arquitectónica de    |
| Estabilidad     |                 | puntos de extensión,         | la plataforma.       |
| del Núcleo      |                 | evitando modificar el        |                      |
|                 |                 | núcleo siempre que sea       |                      |
|                 |                 | posible.                     |                      |
+-----------------+-----------------+------------------------------+----------------------+
| Reutilización   | Reutilización   | Diseñar componentes          | Favorecer futuras    |
| Científica      | Científica      | reutilizables siempre que    | investigaciones y    |
| vs.             |                 | ello no comprometa los       | maximizar el valor   |
| Soluciones      |                 | objetivos científicos        | de la plataforma.    |
| Específicas     |                 | actuales.                    |                      |
+-----------------+-----------------+------------------------------+----------------------+
| Plataforma      | Evolución de    | Priorizar soluciones         | La plataforma        |
| vs.             | la Plataforma   | reutilizables que            | constituye el        |
| Investigación   |                 | beneficien a la plataforma   | principal aporte     |
| Particular      |                 | sin comprometer los          | tecnológico del      |
|                 |                 | objetivos científicos        | proyecto.            |
|                 |                 | actuales.                    |                      |
+-----------------+-----------------+------------------------------+----------------------+



## 17.4 Ingeniería del Software

+-----------------+-----------------+------------------------------+----------------------+
| Conflicto       | Se prioriza     | Acción esperada              | Justificación        |
+-----------------+-----------------+------------------------------+----------------------+
| Usabilidad      | Mantenibilidad  | Mejorar la experiencia       | La arquitectura      |
| vs.             |                 | del usuario sin introducir   | es mucho más         |
| Mantenibilidad  |                 | complejidad innecesaria      | costosa de           |
|                 |                 | en la arquitectura.          | recuperar que la     |
|                 |                 |                              | interfaz.            |
+-----------------+-----------------+------------------------------+----------------------+
| Observabilidad  | Observabilidad  | Mantener registros           | Durante el           |
| vs.             |                 | suficientes para comprender  | desarrollo e         |
| Rendimiento     |                 | el comportamiento del        | investigación es     |
|                 |                 | sistema. Reducirlos sólo     | prioritario poder    |
|                 |                 | cuando exista evidencia      | comprender el        |
|                 |                 | objetiva y aprobación del    | comportamiento del   |
|                 |                 | diseñador.                   | sistema.             |
+-----------------+-----------------+------------------------------+----------------------+
| Auditabilidad   | Auditabilidad   | Conservar registros          | Toda investigación   |
| vs.             |                 | suficientes para             | debe poder ser       |
| Simplicidad     |                 | reconstruir cualquier        | auditada             |
|                 |                 | experimento ejecutado.       | posteriormente.      |
+-----------------+-----------------+------------------------------+----------------------+
| Trazabilidad    | Trazabilidad    | Registrar toda decisión      | Facilita el          |
| vs.             |                 | arquitectónica, cambio       | mantenimiento, la    |
| Rapidez de      |                 | relevante y experimento      | auditoría y la       |
| Desarrollo      |                 | significativo.               | reproducibilidad.    |
+-----------------+-----------------+------------------------------+----------------------+

---

# 18. Quality Gate (Criterios Permanentes de Finalización)

El presente **Quality Gate** establece las verificaciones permanentes del proyecto.

Su objetivo es garantizar que toda nueva funcionalidad pueda incorporarse a la plataforma sin comprometer su estabilidad, calidad, mantenibilidad ni validez científica.

Una iteración sólo podrá considerarse finalizada cuando haya superado satisfactoriamente todas las verificaciones que resulten aplicables según el alcance definido para dicha iteración.

La **Definition of Done (DoD)** de cada iteración determinará explícitamente cuáles de estas verificaciones deberán aplicarse.

---

## Verificación funcional

La implementación deberá:

- cumplir todos los objetivos definidos para la iteración;
- respetar el alcance acordado;
- satisfacer los criterios de aceptación establecidos;
- no incorporar funcionalidades fuera del alcance previsto;
- no presentar errores conocidos que impidan su funcionamiento normal.

---

## Verificación arquitectónica

La implementación deberá respetar:

- la arquitectura definida para el proyecto;
- los principios SOLID;
- el bajo acoplamiento;
- la alta cohesión;
- la correcta separación de responsabilidades;
- los atributos de calidad definidos en la Sección 14;
- la priorización de atributos establecida en la Sección 15;
- las reglas de resolución de Trade-offs definidas en la Sección 16;
- todas las convenciones establecidas en el presente AGENTS.

---

## Verificación científica

Cuando la iteración modifique el comportamiento de la simulación o de la plataforma experimental, deberá verificarse, según corresponda:

- la confiabilidad experimental;
- la reproducibilidad experimental;
- la correcta configuración de los experimentos;
- la consistencia de las métricas obtenidas;
- la preservación de resultados previamente validados.

---

## Verificación documental

Toda modificación relevante deberá reflejarse en la documentación correspondiente.

La documentación deberá mantenerse sincronizada con la implementación.

Toda decisión arquitectónica relevante deberá quedar registrada en el historial del proyecto.

---

## Verificación de pruebas

Deberán ejecutarse las pruebas previstas para la iteración.

Cuando corresponda, deberán realizarse:

- pruebas unitarias;
- pruebas de integración;
- pruebas end-to-end;
- pruebas de regresión.

No deberán introducirse regresiones sobre funcionalidades previamente implementadas.

Los resultados de las pruebas deberán quedar documentados cuando así lo establezca la iteración.

---

## Calidad del código

Antes de finalizar una iteración deberá verificarse que:

- no exista código muerto;
- no existan duplicaciones innecesarias;
- no permanezcan implementaciones temporales sin justificar;
- no se introduzca deuda técnica innecesaria;
- toda deuda técnica aceptada quede explícitamente documentada;
- el código mantenga un adecuado nivel de legibilidad, mantenibilidad y consistencia.

---

## Evidencias del Quality Gate

La IA deberá informar explícitamente el resultado de cada una de las verificaciones realizadas.

Cuando una verificación no resulte aplicable a la iteración, deberá indicarlo expresamente junto con su justificación.

No será suficiente indicar que la implementación "cumple el Quality Gate".

Deberá presentarse un resumen de las verificaciones efectuadas y su resultado, indicando claramente cuáles fueron satisfactorias, cuáles no resultaron aplicables y cuáles requieren intervención del diseñador.

---

## Aprobación

Una iteración sólo podrá considerarse finalizada cuando todas las verificaciones obligatorias hayan sido completadas satisfactoriamente.

En caso de detectarse incumplimientos, la IA deberá informar claramente:

- los criterios incumplidos;
- las causas identificadas;
- las acciones necesarias para corregirlos;
- si corresponde o no aprobar la iteración.

---

## Adaptación del Quality Gate

El presente Quality Gate define el conjunto permanente de verificaciones disponibles para el proyecto.

La especificación de cada iteración establecerá explícitamente cuáles de estas verificaciones serán obligatorias de acuerdo con:

- el alcance de la iteración;
- la complejidad de la implementación;
- los riesgos asociados;
- la Definition of Done (DoD) correspondiente.

Las verificaciones no aplicables deberán indicarse expresamente durante el cierre de la iteración.

---

# 19- Historial del AGENTS

Este documento constituye la especificación permanente del proyecto.

Su evolución deberá realizarse de forma controlada.

Toda modificación deberá:

- justificar el motivo del cambio;
- indicar la versión del AGENTS;
- registrar la fecha;
- describir brevemente el impacto esperado.

Las modificaciones al presente documento las realizará únicamente el arquitecto del proyecto y deberán ser excepcionales, procurando mantener la estabilidad de las reglas permanentes del proyecto.