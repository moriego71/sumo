# Modelo Conceptual

## 1. Propósito

El presente documento define el modelo conceptual de la plataforma de investigación.

Su propósito es establecer un lenguaje común para describir los principales conceptos del dominio, sus relaciones y sus responsabilidades, independientemente de cualquier decisión de implementación.

Este modelo constituye la base para el diseño posterior de la arquitectura del sistema, las iteraciones de desarrollo y la evolución funcional de la plataforma.

Las definiciones aquí contenidas representan conceptos del dominio y no clases, módulos, componentes o decisiones de implementación.

---

## 2. Principios del Modelo Conceptual

El modelo conceptual representa exclusivamente conceptos propios del dominio de investigación.

En su elaboración deberán respetarse los siguientes principios:

- cada concepto representará una única responsabilidad;
- las relaciones entre conceptos deberán ser explícitas;
- se evitarán conceptos redundantes, ambiguos o superpuestos;
- las decisiones de implementación no formarán parte del modelo conceptual;
- el modelo podrá evolucionar durante el proyecto, preservando siempre la coherencia del dominio.


## 3. Conceptos Fundamentales

El modelo conceptual de la plataforma se construye sobre los siguientes conceptos fundamentales:

- Plataforma de Investigación
- Campaña Experimental
- Infraestructura
- Experimento
- Configuración Experimental
- Ejecución
- Escenario urbano
- Estrategia
- Resultado
- Métrica
- Conclusión
- 

### Plataforma de Investigación

Sistema de software destinado a diseñar, ejecutar y analizar experimentos relacionados con la gestión inteligente del estacionamiento urbano.

La plataforma proporciona la infraestructura necesaria para desarrollar investigaciones de manera configurable, reutilizable y trazable, desacoplando la infraestructura experimental de las estrategias específicas que se deseen evaluar.

Se compone de campañas experimentales, escenarios urbanos, infraestructuras experimentales, estrategias, mecanismos de ejecución y herramientas para el análisis de resultados.

### Campaña Experimental

Conjunto organizado de experimentos orientados a estudiar un mismo problema, objetivo o pregunta de investigación.

Una campaña constituye la unidad principal de organización del trabajo científico dentro de la plataforma, agrupando los experimentos, sus configuraciones, las ejecuciones realizadas, los resultados obtenidos, las métricas calculadas y las conclusiones derivadas de su análisis.

Su propósito es facilitar la planificación, ejecución y análisis sistemático de investigaciones sobre la gestión inteligente del estacionamiento urbano.


### Configuración Experimental

Conjunto de parámetros que define las condiciones bajo las cuales se desarrollará un experimento.

Una configuración experimental define las condiciones bajo las cuales se desarrollará un experimento, especificando el escenario urbano, la infraestructura experimental, las estrategias utilizadas y los parámetros necesarios para garantizar la reproducibilidad del estudio.

Un mismo experimento podrá ejecutarse múltiples veces utilizando la misma configuración experimental.

Distintas configuraciones permiten comparar el comportamiento del sistema bajo diferentes condiciones experimentales.


### Infraestructura

Conjunto de componentes físicos y lógicos desplegados sobre un escenario urbano para conformar el entorno experimental de una investigación.

La infraestructura define los recursos disponibles durante la ejecución de los experimentos, incluyendo, entre otros elementos, zonas de estacionamiento, sensores, grúas, inspectores, dispositivos inteligentes y cualquier otro componente susceptible de ser incorporado, modificado o eliminado durante la evolución del sistema.

Una misma infraestructura podrá utilizarse en múltiples configuraciones experimentales.


### Experimento

Unidad básica de investigación destinada a evaluar el comportamiento del sistema bajo una configuración experimental determinada.

Un experimento define qué se desea analizar y bajo qué condiciones deberá realizarse el estudio.

Cada experimento podrá ejecutarse múltiples veces mediante ejecuciones independientes, permitiendo obtener resultados estadísticamente representativos.


### Ejecución

Instancia individual de ejecución de un experimento.

Cada ejecución utiliza la configuración experimental definida para el experimento y produce un conjunto de resultados que posteriormente podrán analizarse mediante distintas métricas.

La repetición de múltiples ejecuciones bajo las mismas condiciones permite obtener resultados estadísticamente confiables.

Campaña
│
├── Experimento
│      │
│      ├── Configuración Experimental
│      │      ├── Infraestructura
│      │      │      ├── Escenario
│      │      │      ├── Parkings
│      │      │      ├── Sensores
│      │      │      └── ...
│      │      │
│      │      ├── Estrategia
│      │      └── Parámetros Experimentales
│      │
│      ├── Ejecuciones
│             └── Resultados
│
└── Conclusiones




### Escenario Urbano  (Escenario)

Representación física del entorno urbano sobre el cual se desarrollan los experimentos.

Describe la estructura espacial de la ciudad, incluyendo la red vial y aquellos elementos permanentes que caracterizan el entorno simulado.

Un mismo escenario podrá utilizarse en múltiples configuraciones experimentales.


### Estrategia

Conjunto de reglas que determina el comportamiento de uno o más actores durante la ejecución de un experimento.

Las estrategias permiten definir, modificar o reemplazar distintos algoritmos de decisión sin alterar la infraestructura experimental de la plataforma.

Una misma estrategia podrá utilizarse en múltiples experimentos, facilitando la comparación objetiva entre distintos enfoques de resolución.


### Resultado

Conjunto de datos obtenidos durante una ejecución de un experimento.

Los resultados representan las observaciones producidas por la plataforma y constituyen la materia prima para el cálculo de métricas y el posterior análisis de la investigación.

Cada ejecución genera un conjunto independiente de resultados que representan las observaciones obtenidas durante esa ejecución específica.


### Métrica

Medida cuantitativa calculada a partir de los resultados obtenidos durante una o varias ejecuciones.

Las métricas permiten comparar distintas configuraciones experimentales y evaluar objetivamente el comportamiento del sistema frente a una hipótesis de investigación.

Una misma colección de resultados podrá analizarse mediante diferentes métricas.


### Conclusión

Interpretación de los resultados obtenidos durante una campaña experimental a partir del análisis de las métricas calculadas y la evidencia generada por los experimentos.

Las conclusiones sintetizan el conocimiento obtenido durante la investigación, permitiendo responder la pregunta de investigación, evaluar el comportamiento del sistema bajo las condiciones estudiadas e identificar oportunidades para futuras investigaciones o nuevas campañas experimentales.


# 4. Relaciones Conceptuales

Las principales relaciones conceptuales de la plataforma son las siguientes:

- Una Plataforma de Investigación contiene múltiples Campañas Experimentales.
- Una Campaña Experimental agrupa uno o más Experimentos y constituye la unidad principal de organización del trabajo experimental.
- Cada Experimento posee una única Configuración Experimental.
- Una Configuración Experimental referencia un Escenario y define los parámetros bajo los cuales se ejecutará el experimento.
- Una Configuración Experimental referencia un Escenario Urbano.
- Una Configuración Experimental referencia una Infraestructura Experimental.
- Una Configuración Experimental referencia una Estrategia.
- Un Experimento puede ejecutarse múltiples veces mediante Ejecuciones independientes.
- Cada Ejecución genera un conjunto de Resultados.
- Las Métricas se calculan a partir de los Resultados obtenidos en una o varias Ejecuciones.
- Las Conclusiones se elaboran a partir del análisis de las Métricas obtenidas durante la Campaña Experimental.


## 5. Flujo General de una Investigación

Una investigación desarrollada sobre la plataforma sigue, conceptualmente, el siguiente flujo:

Campaña Experimental
        │
        ▼
Experimento
        │
        ├── Configuración Experimental
        │
        ▼
Ejecuciones
        │
        ▼
Resultados
        │
        ▼
Métricas
        │
        ▼
Conclusiones