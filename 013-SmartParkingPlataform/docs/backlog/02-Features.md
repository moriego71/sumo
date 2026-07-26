## EP01 - Gestión de Campañas Experimentales

### Objetivo
Permitir organizar, administrar y dar seguimiento a campañas de investigación destinadas a responder un mismo problema, objetivo o pregunta de investigación mediante la ejecución coordinada de múltiples experimentos.

### Features

#### FE01.01 [RF] - Crear Campaña Experimental
Permite registrar una nueva campaña de investigación definiendo su información general.

#### FE01.02 [RF] - Consultar Campañas Experimentales
Permite visualizar y consultar las campañas registradas en la plataforma.

#### FE01.03 [RF] - Modificar Campaña Experimental
Permite actualizar la información de una campaña mientras su estado lo permita.

#### FE01.04 [RF] - Gestionar el Estado de una Campaña
Permite administrar el ciclo de vida de una campaña durante su desarrollo.

#### FE01.05 [RF] - Asociar Experimentos a una Campaña
Permite incorporar, organizar y administrar los experimentos pertenecientes a una campaña.

#### FE01.06 [RF] - Consultar el Estado General de la Campaña
Permite visualizar un resumen del estado de avance de la campaña, incluyendo la cantidad de experimentos, ejecuciones realizadas, resultados obtenidos, métricas calculadas y conclusiones disponibles.

 

## EP02 - Gestión de Experimentos

### Objetivo
Permitir definir, organizar y administrar los experimentos que forman parte de una campaña experimental, estableciendo las condiciones necesarias para su posterior ejecución y análisis.

### Features

#### FE02.01 [RF] - Crear Experimento
Permite registrar un nuevo experimento dentro de una campaña experimental.

#### FE02.02 [RF] - Consultar Experimentos
Permite visualizar y consultar los experimentos pertenecientes a una campaña.

#### FE02.03 [RF] - Modificar Experimento
Permite actualizar la información de un experimento mientras su estado lo permita.

#### FE02.04 [RF] - Gestionar el Estado de un Experimento
Permite administrar el ciclo de vida de un experimento durante su desarrollo.

#### FE02.05 [RF] - Asociar una Configuración Experimental
Permite vincular una configuración experimental que defina las condiciones bajo las cuales será ejecutado el experimento.

#### FE02.06 [RF] - Planificar Ejecuciones
Permite definir la cantidad de ejecuciones que deberán realizarse para un experimento y las condiciones generales bajo las cuales serán efectuadas.

#### FE02.07 [RF] - Duplicar Experimento
Permite generar un nuevo experimento a partir de otro existente, reutilizando total o parcialmente su configuración.



## EP03 - Gestión de Configuraciones Experimentales

### Objetivo

Permitir definir, administrar y reutilizar las configuraciones experimentales que establecen las condiciones bajo las cuales se ejecutarán los experimentos.

### Features

#### FE03.01 [RF] - Crear Configuración Experimental
Permite definir una nueva configuración experimental especificando todos los parámetros necesarios para la ejecución de un experimento.

#### FE03.02 [RF] - Consultar Configuraciones Experimentales
Permite visualizar y consultar las configuraciones experimentales disponibles en la plataforma.

#### FE03.03 [RF] - Modificar Configuración Experimental
Permite actualizar una configuración experimental mientras no existan restricciones que lo impidan.

#### FE03.04 [RF] - Asociar un Escenario
Permite seleccionar el escenario urbano que representará el entorno físico de la simulación sobre el cual se desplegará la infraestructura experimental.

#### FE03.05 [RF] - Asociar una Estrategia
Permite seleccionar la estrategia que será evaluada durante las ejecuciones del experimento.

#### FE03.06 [RF] - Configurar Parámetros Experimentales
Permite establecer los parámetros específicos del experimento, tales como cantidad de vehículos, distribución de actores, semilla aleatoria y cualquier otra variable necesaria para garantizar la reproducibilidad del estudio.

#### FE03.07 [RF] - Reutilizar Configuraciones Experimentales
Permite utilizar una configuración previamente definida como punto de partida para nuevos experimentos, facilitando la comparación sistemática entre distintas condiciones experimentales.



## EP04 - Motor de Ejecución Experimental

### Objetivo

Permitir planificar, ejecutar, controlar y monitorear las ejecuciones de los experimentos, garantizando su reproducibilidad, trazabilidad y correcta finalización.

### Features

#### FE04.01 - Iniciar Ejecuciones
Permite lanzar la ejecución de un experimento utilizando una configuración experimental determinada.

#### FE04.02 - Ejecutar Múltiples Ejecuciones
Permite repetir automáticamente un mismo experimento mediante múltiples ejecuciones independientes.

#### FE04.03 - Monitorear Ejecuciones
Permite conocer el estado y el progreso de las ejecuciones en curso.

#### FE04.04 - Gestionar el Estado de las Ejecuciones
Permite administrar el ciclo de vida de cada ejecución desde su inicio hasta su finalización.

#### FE04.05 - Controlar la Reproducibilidad Experimental
Permite garantizar que una ejecución pueda repetirse bajo las mismas condiciones experimentales.

#### FE04.06 - Registrar la Trazabilidad de las Ejecuciones
Permite registrar toda la información necesaria para reconstruir posteriormente las condiciones bajo las cuales fue realizada una ejecución.

#### FE04.07 - Gestionar Errores de Ejecución
Permite detectar, registrar y administrar las situaciones que impidan completar correctamente una ejecución experimental.

#### FE04.08 - Persistir los Resultados de las Ejecuciones
Permite almacenar de forma organizada los resultados generados por cada ejecución experimental, preservando toda la información necesaria para su posterior análisis, reproducibilidad y comparación.



## EP04 - Motor de Ejecución Experimental

### Objetivo

Permitir planificar, ejecutar, controlar y monitorear las ejecuciones de los experimentos, garantizando su reproducibilidad, trazabilidad y correcta finalización.

### Features

#### FE04.01 [RF] - Iniciar Ejecuciones
Permite lanzar la ejecución de un experimento utilizando una configuración experimental determinada.

#### FE04.02 [RF] - Ejecutar Múltiples Ejecuciones
Permite repetir automáticamente un mismo experimento mediante múltiples ejecuciones independientes.

#### FE04.03 [RF] - Monitorear Ejecuciones
Permite conocer el estado y el progreso de las ejecuciones en curso.

#### FE04.04 [RF] - Gestionar el Estado de las Ejecuciones
Permite administrar el ciclo de vida de cada ejecución desde su inicio hasta su finalización.

#### FE04.05 [RNF] - Controlar la Reproducibilidad Experimental
Permite garantizar que una ejecución pueda repetirse bajo las mismas condiciones experimentales.

#### FE04.06 [RNF] - Registrar la Trazabilidad de las Ejecuciones
Permite registrar toda la información necesaria para reconstruir posteriormente las condiciones bajo las cuales fue realizada una ejecución.

#### FE04.07 [RNF] - Gestionar Errores de Ejecución
Permite detectar, registrar y administrar las situaciones que impidan completar correctamente una ejecución experimental.

#### FE04.08 [RNF] - Persistir los Resultados de las Ejecuciones
Permite almacenar de forma organizada los resultados generados por cada ejecución experimental, preservando toda la información necesaria para su posterior análisis, reproducibilidad y comparación.



## EP06 - Gestión de Infraestructura Experimental

### Objetivo
Permitir diseñar, administrar y evolucionar infraestructuras experimentales mediante la composición de escenarios urbanos y activos del dominio, definiendo el entorno sobre el cual se desarrollarán los experimentos.

### Features

#### FE06.01 [RF] - Crear Infraestructura Experimental
Permite registrar una nueva infraestructura experimental.

#### FE06.02 [RF] - Consultar Infraestructuras Experimentales
Permite visualizar y consultar las infraestructuras disponibles.

#### FE06.03 [RF] - Modificar Infraestructura Experimental
Permite actualizar la definición de una infraestructura experimental.

#### FE06.04 [RF] - Asociar un Escenario Urbano
Permite seleccionar el escenario urbano que servirá como base física de la infraestructura experimental.

#### FE06.05 [RF] - Incorporar Activos a la Infraestructura
Permite agregar y configurar los distintos activos que conforman una infraestructura experimental.

#### FE06.06 [RF] - Organizar la Distribución Espacial de los Activos
Permite definir la ubicación y disposición de los activos dentro del escenario urbano.

#### FE06.07 [RNF] - Validar la Consistencia de la Infraestructura
Permite verificar que la infraestructura experimental sea coherente, completa y apta para ser utilizada por las configuraciones experimentales.



## EP07 - Gestión de Estrategias *(Fuera del MVP / MVP 2)*

### Objetivo
Permitir administrar las estrategias utilizadas por la plataforma para resolver la asignación de plazas durante los experimentos.

### Features

#### FE07.01 [RF] - Registrar Estrategia
Permite registrar una nueva estrategia disponible para ser utilizada por las configuraciones experimentales.

#### FE07.02 [RF] - Consultar Estrategias
Permite visualizar y consultar las estrategias registradas.

#### FE07.03 [RF] - Modificar Estrategia
Permite actualizar la definición de una estrategia manteniendo su consistencia.



## EP08 - Gestión de Persistencia

### Objetivo
Garantizar la persistencia, organización y recuperación de la información administrada por la plataforma, preservando la trazabilidad, integridad y reproducibilidad de las investigaciones.

### Features

#### FE08.01 [RNF]- Almacenar Campañas Experimentales
Permite persistir la información correspondiente a las campañas de investigación.

#### FE08.02 [RNF]- Almacenar Experimentos
Permite persistir la configuración y el estado de los experimentos realizados.

#### FE08.03 [RNF]- Almacenar Ejecuciones
Permite registrar cada ejecución realizada junto con su información asociada.

#### FE08.04 [RNF]- Almacenar Resultados
Permite persistir los resultados generados por cada ejecución de manera organizada y trazable.

#### FE08.05 [RNF] - Recuperación Persistente de la Información
Permite reconstruir y recuperar la información previamente almacenada preservando su integridad y consistencia.



## EP09 - Gestión de Métricas

### Objetivo
Permite definir, calcular y administrar las métricas utilizadas para evaluar objetivamente el comportamiento de los experimentos.

#### FE09.01 [RF]- Definir Métrica
Permite definir el típo de métrica que queremos obtener.

#### FE09.02 [RF]- Definir Parámetros.
Permite establecer qué parámetros se quiere analizar.

#### FE09.03 [RF]- Establecer Método de Analisis.
Permite detarminar métodos de selección y análisis de los datos obtenidos.

#### FE09.04 [RF]- Modificaciones o correcciones
Permite validar o corregir, métricas, parámetros y/o método de análisis

#### FE09.05 [RNF]- Preservar las Métricas obtenidad.
Almacena en Base de Datos las métricas obtenidas referenciando a la campaña experimental y los datos que le dieron origen.

(queda pendiente brindarle al usuario la elección del tipo de gráfico con que quiere ver las métricas)
(queda pendiente le generación de los gráficos a partir de la métrica obtenida)
Supongo que ésto lo resolveremos al resolver la interfaz gráfica.



## EP10 - Análisis Científico

### Objetivo
Permite analizar los resultados experimentales para interpretar el comportamiento del sistema, obtener conocimiento a partir de la evidencia generada y elaborar conclusiones sustentadas en métricas objetivas.

#### FE10.01 [RF]- Definir Analizar Científico
Permite definir qué comportamiento vamos a Analizar o qué queremos corroborar.

#### FE10.02 [RF]- Definir Parámetros.
Permite establecer qué métricas y datos usaremos para sacar conclusiones.

#### FE10.03 [RF]- Establecer Método de Analisis.
Permite detarminar métodos de selección y análisis de los métricas y datos.

#### FE10.04 [RF]- Modificaciones o correcciones
Permite validar o corregir, tipo de análisis, parámetros y/o método de análisis

#### FE10.05 [RNF]- Preservar Análisis y Conclusiones.
Almacena en Base de Datos Análisis y Conclusiones referenciando a las métricas y los datos que le dieron origen.



## EP11 - Administración de la Plataforma

### Objetivo
Permite administrar los recursos, configuraciones y servicios generales necesarios para el correcto funcionamiento de la plataforma de investigación.

Replantease: qué es una Plataforma ahora? 
Tal vez con los últimos cambios de enfoque se deba refactorizar
En modelo conceptual quedó:
### Plataforma de Investigación

Sistema de software destinado a diseñar, ejecutar y analizar experimentos relacionados con la gestión inteligente del estacionamiento urbano.

La plataforma proporciona la infraestructura necesaria para desarrollar investigaciones de manera configurable, reutilizable y trazable, desacoplando la infraestructura experimental de las estrategias específicas que se deseen evaluar.

Se compone de campañas experimentales, escenarios urbanos, infraestructuras experimentales, estrategias, mecanismos de ejecución y herramientas para el análisis de resultados.  
