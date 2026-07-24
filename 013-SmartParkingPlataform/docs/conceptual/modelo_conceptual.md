




## Flujo científico general
#### ¿Cómo se desarrolla una investigación?

Hipótesis
↓
Campaña Experimental
↓
Configuración Experimental
↓
Experimentos
↓
Simulaciones
↓
Resultados
↓
Métricas
↓
Análisis
↓
Conclusiones


## Subsistemas

Plataforma
│
├── Gestión Experimental
├── Simulación
├── Infraestructura
├── Estrategias
├── Métricas
├── Persistencia
├── Visualización
└── Interfaz

**************************************************

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
- Experimento
- Configuración Experimental
- Ejecución
- Escenario
- Estrategia
- Resultado
- Métrica
- Hipótesis
- Conclusión
- 

### Plataforma de Investigación

Sistema de software destinado a diseñar, ejecutar y analizar experimentos relacionados con la gestión inteligente del estacionamiento urbano.

La plataforma proporciona la infraestructura necesaria para desarrollar investigaciones de manera configurable, reutilizable y trazable, desacoplando la infraestructura experimental de las estrategias específicas que se deseen evaluar.

Se compone de campañas experimentales, experimentos, escenarios, estrategias, mecanismos de ejecución y herramientas para el análisis de resultados.


### Campaña Experimental

Conjunto organizado de experimentos destinados a validar una misma hipótesis o responder una misma pregunta de investigación.

Una campaña define el objetivo científico de la investigación y agrupa los experimentos, sus configuraciones experimentales, las ejecuciones realizadas, los resultados obtenidos, las métricas calculadas y las conclusiones derivadas.

Constituye la unidad principal de organización del trabajo experimental dentro de la plataforma.


### Configuración Experimental

Conjunto de parámetros que define las condiciones bajo las cuales se desarrollará un experimento.

Una configuración experimental especifica, entre otros aspectos, el escenario urbano, las estrategias utilizadas, el comportamiento de los distintos actores y cualquier otro parámetro necesario para reproducir las condiciones del experimento.

Un mismo experimento podrá ejecutarse múltiples veces utilizando la misma configuración experimental.

Distintas configuraciones permiten comparar el comportamiento del sistema bajo diferentes condiciones experimentales.


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
    ├── Experimentos
    │       │
    │       ├── Configuración
    │       │
    │       ├── Ejecución 1
    │       ├── Ejecución 2
    │       ├── Ejecución 3
    │       └── ...
    │
    ├── Resultados
    ├── Métricas
    └── Conclusiones


### Escenario

Representación del entorno urbano sobre el cual se desarrollan las ejecuciones de un experimento.

Un escenario define la infraestructura física de la simulación, incluyendo, entre otros elementos, la red vial, las zonas de estacionamiento, las plazas disponibles y cualquier otro componente permanente del entorno.

Un mismo escenario podrá utilizarse en múltiples experimentos y configuraciones experimentales.


### Estrategia

Conjunto de reglas que determina el comportamiento de uno o más actores durante la ejecución de un experimento.

Las estrategias permiten definir, modificar o reemplazar distintos algoritmos de decisión sin alterar la infraestructura experimental de la plataforma.

Una misma estrategia podrá utilizarse en múltiples experimentos, facilitando la comparación objetiva entre distintos enfoques de resolución.


### Resultado

Conjunto de datos obtenidos durante una ejecución de un experimento.

Los resultados representan las observaciones producidas por la plataforma y constituyen la materia prima para el cálculo de métricas y el posterior análisis de la investigación.

Cada ejecución genera un conjunto independiente de resultados.


### Métrica

Medida cuantitativa calculada a partir de los resultados obtenidos durante una o varias ejecuciones.

Las métricas permiten comparar distintas configuraciones experimentales y evaluar objetivamente el comportamiento del sistema frente a una hipótesis de investigación.

Una misma colección de resultados podrá analizarse mediante diferentes métricas.


### Hipótesis

Afirmación o pregunta de investigación cuya validez se pretende analizar mediante una campaña experimental.

La hipótesis establece el objetivo científico de la investigación y orienta el diseño de los experimentos, las métricas a calcular y el análisis de los resultados.


### Conclusión

Interpretación de los resultados obtenidos durante una campaña experimental en relación con la hipótesis planteada.

Las conclusiones sintetizan la evidencia generada por los experimentos y permiten aceptar, rechazar o reformular las hipótesis de investigación.


## 4. Relaciones Conceptuales

Las principales relaciones conceptuales de la plataforma son las siguientes:

- Una Plataforma de Investigación contiene múltiples Campañas Experimentales.
- Una Campaña Experimental se orienta a validar una Hipótesis.
- Una Campaña Experimental agrupa uno o más Experimentos.
- Cada Experimento posee una única Configuración Experimental.
- Un Experimento puede ejecutarse múltiples veces mediante Ejecuciones independientes.
- Cada Ejecución genera un conjunto de Resultados.
- Las Métricas se calculan a partir de los Resultados obtenidos en una o varias Ejecuciones.
- Las Conclusiones se elaboran a partir del análisis de las Métricas obtenidas durante la Campaña Experimental.


## 5. Flujo General de una Investigación

Una investigación desarrollada sobre la plataforma sigue, conceptualmente, el siguiente flujo:

Hipótesis
      │
      ▼
Campaña Experimental
      │
      ▼
Experimentos
      │
      ├── Configuración Experimental
      │
      └── Ejecuciones
              │
              ▼
         Resultados
              │
              ▼
          Métricas
              │
              ▼
          Conclusiones
