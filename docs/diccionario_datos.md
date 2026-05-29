# Diccionario de Datos — DataMart de Siniestralidad Vial

## DIM_FECHA

### Descripción
La dimensión fecha almacena la información temporal relacionada con los siniestros viales, personas involucradas y vehículos registrados. Permite realizar análisis históricos y tendencias temporales.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_fecha | INT | Identificador único de la dimensión fecha. |
| fecha | DATE | Fecha exacta en que ocurrió el evento vial. |
| anio | INT | Año correspondiente a la fecha del evento. |
| mes | INT | Número del mes del evento. |
| nombre_mes | VARCHAR(20) | Nombre textual del mes. |
| trimestre | INT | Trimestre del año asociado a la fecha. |
| dia | INT | Día del mes del evento. |
| dia_semana | VARCHAR(20) | Día de la semana correspondiente a la fecha. |
| fin_semana | VARCHAR(10) | Indicador que identifica si ocurrió en fin de semana. |

## DIM_UBICACION

### Descripción
La dimensión ubicación almacena información geográfica relacionada con los siniestros viales ocurridos en el Perú.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_ubicacion | INT | Identificador único de la dimensión ubicación. |
| departamento | VARCHAR(100) | Departamento donde ocurrió el siniestro. |
| provincia | VARCHAR(100) | Provincia donde ocurrió el evento. |
| distrito | VARCHAR(100) | Distrito donde ocurrió el evento vial. |
| ubicacion | VARCHAR(255) | Nombre aproximado de la vía o ubicación del siniestro. |
| latitud | DECIMAL(10,6) | Coordenada geográfica de latitud. |
| longitud | DECIMAL(10,6) | Coordenada geográfica de longitud. |
| codigo_carretera | VARCHAR(50) | Código identificador de carretera. |
| red_vial | VARCHAR(100) | Tipo de red vial asociada al evento. |

## DIM_VIA

### Descripción
La dimensión vía almacena las características físicas y estructurales de las vías donde ocurrieron los siniestros.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_via | INT | Identificador único de la dimensión vía. |
| tipo_via | VARCHAR(100) | Tipo de vía donde ocurrió el evento. |
| superficie_calzada | VARCHAR(100) | Tipo de superficie de la calzada. |
| caracteristicas_via | VARCHAR(150) | Características físicas de la vía. |
| perfil_longitudinal | VARCHAR(100) | Perfil longitudinal registrado en la vía. |

## DIM_CAUSA

### Descripción
La dimensión causa almacena los factores principales y específicos asociados a los siniestros viales.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_causa | INT | Identificador único de la dimensión causa. |
| causa_principal | VARCHAR(150) | Factor principal relacionado al siniestro. |
| causa_especifica | VARCHAR(255) | Descripción específica de la causa registrada. |

## DIM_CLIMA

### Descripción
La dimensión clima almacena información relacionada con las condiciones climáticas y ambientales del evento vial.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_clima | INT | Identificador único de la dimensión clima. |
| condicion_climatica | VARCHAR(100) | Condición climática registrada durante el evento. |
| zonificacion | VARCHAR(100) | Tipo de zonificación asociada al lugar del evento. |

## DIM_SENALIZACION

### Descripción
La dimensión señalización almacena información sobre las señales de tránsito presentes en la vía donde ocurrió el siniestro.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_senalizacion | INT | Identificador único de la dimensión señalización. |
| existe_senal_vertical | VARCHAR(10) | Indicador de existencia de señalización vertical. |
| clasificacion_senal_1 | VARCHAR(150) | Primera clasificación de señal vertical registrada. |
| clasificacion_senal_2 | VARCHAR(150) | Segunda clasificación de señal vertical registrada. |
| existe_senal_horizontal | VARCHAR(10) | Indicador de existencia de señalización horizontal. |

## DIM_PERSONA

### Descripción
La dimensión persona almacena información demográfica y características generales de las personas involucradas en los siniestros.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_persona_dim | INT | Identificador único de la dimensión persona. |
| tipo_persona | VARCHAR(100) | Tipo de persona involucrada en el evento vial. |
| sexo | VARCHAR(20) | Sexo de la persona involucrada. |
| edad | INT | Edad de la persona registrada. |
| rango_edad | VARCHAR(30) | Clasificación de rango etario utilizada para análisis. |

## DIM_LICENCIA

### Descripción
La dimensión licencia almacena información relacionada con licencias de conducir de las personas involucradas.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_licencia | INT | Identificador único de la dimensión licencia. |
| posee_licencia | VARCHAR(10) | Indicador de posesión de licencia de conducir. |
| estado_licencia | VARCHAR(50) | Estado de la licencia registrada. |
| clase_licencia | VARCHAR(50) | Clase o categoría de licencia de conducir. |

## DIM_DOSAJE

### Descripción
La dimensión dosaje almacena información relacionada con pruebas de alcoholemia realizadas a personas involucradas.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_dosaje | INT | Identificador único de la dimensión dosaje. |
| sometio_dosaje_cualitativo | VARCHAR(10) | Indicador de realización de dosaje cualitativo. |
| resultado_dosaje_cualitativo | VARCHAR(100) | Resultado obtenido en la prueba cualitativa. |
| sometio_dosaje_cuantitativo | VARCHAR(10) | Indicador de realización de dosaje cuantitativo. |

## DIM_GRAVEDAD

### Descripción
La dimensión gravedad clasifica el nivel de afectación de las personas involucradas en los siniestros.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_gravedad | INT | Identificador único de la dimensión gravedad. |
| gravedad | VARCHAR(50) | Nivel de gravedad asociado a la persona. |

## DIM_VEHICULO

### Descripción
La dimensión vehículo almacena información general relacionada con los vehículos involucrados en siniestros viales.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_vehiculo_dim | INT | Identificador único de la dimensión vehículo. |
| vehiculo | VARCHAR(100) | Tipo o categoría del vehículo involucrado. |

## DIM_MODALIDAD_TRANSPORTE

### Descripción
La dimensión modalidad transporte almacena información relacionada con la modalidad y ámbito de servicio del vehículo.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_modalidad | INT | Identificador único de la dimensión modalidad transporte. |
| estado_modalidad | VARCHAR(100) | Estado de la modalidad de transporte. |
| modalidad_transporte | VARCHAR(100) | Modalidad de transporte registrada. |
| ambito_servicio | VARCHAR(100) | Ámbito de servicio asociado al vehículo. |

## DIM_SEGURIDAD_VEHICULO

### Descripción
La dimensión seguridad vehículo almacena información relacionada con documentación y seguridad vehicular.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_seguridad_vehiculo | INT | Identificador único de la dimensión seguridad vehicular. |
| posee_seguro | VARCHAR(10) | Indicador de existencia de seguro vehicular. |
| estado_soat | VARCHAR(50) | Estado del SOAT registrado. |
| tipo_seguro | VARCHAR(100) | Tipo de seguro asociado al vehículo. |
| posee_citv | VARCHAR(10) | Indicador de existencia de CITV. |
| estado_citv | VARCHAR(50) | Estado del certificado CITV. |

## FACT_SINIESTROS

### Descripción
La tabla de hechos FACT_SINIESTROS almacena las métricas principales relacionadas con cada siniestro vial registrado.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_siniestro_fact | INT | Identificador único de la tabla de hechos siniestros. |
| codigo_siniestro | VARCHAR(50) | Código identificador original del siniestro. |
| id_fecha | INT | Llave foránea relacionada con la dimensión fecha. |
| id_ubicacion | INT | Llave foránea relacionada con la dimensión ubicación. |
| id_via | INT | Llave foránea relacionada con la dimensión vía. |
| id_causa | INT | Llave foránea relacionada con la dimensión causa. |
| id_clima | INT | Llave foránea relacionada con la dimensión clima. |
| id_senalizacion | INT | Llave foránea relacionada con la dimensión señalización. |
| cantidad_fallecidos | INT | Cantidad total de fallecidos registrados en el siniestro. |
| cantidad_lesionados | INT | Cantidad total de lesionados registrados en el siniestro. |
| cantidad_vehiculos_danados | INT | Cantidad total de vehículos dañados en el evento. |
| total_siniestros | INT | Métrica utilizada para conteo total de siniestros. |

## FACT_PERSONAS

### Descripción
La tabla de hechos FACT_PERSONAS almacena información relacionada con las personas involucradas en los siniestros viales.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_persona_fact | INT | Identificador único de la tabla de hechos personas. |
| codigo_siniestro | VARCHAR(50) | Código identificador del siniestro asociado. |
| id_fecha | INT | Llave foránea relacionada con la dimensión fecha. |
| id_ubicacion | INT | Llave foránea relacionada con la dimensión ubicación. |
| id_persona_dim | INT | Llave foránea relacionada con la dimensión persona. |
| id_licencia | INT | Llave foránea relacionada con la dimensión licencia. |
| id_dosaje | INT | Llave foránea relacionada con la dimensión dosaje. |
| id_gravedad | INT | Llave foránea relacionada con la dimensión gravedad. |
| total_personas | INT | Métrica utilizada para conteo total de personas involucradas. |
| fallecido | INT | Indicador de persona fallecida. |
| lesionado | INT | Indicador de persona lesionada. |

## FACT_VEHICULOS

### Descripción
La tabla de hechos FACT_VEHICULOS almacena información relacionada con los vehículos involucrados en siniestros viales.

| Nombre de columna | Tipo de dato | Descripción |
|---|---|---|
| id_vehiculo_fact | INT | Identificador único de la tabla de hechos vehículos. |
| codigo_siniestro | VARCHAR(50) | Código identificador del siniestro asociado. |
| id_fecha | INT | Llave foránea relacionada con la dimensión fecha. |
| id_ubicacion | INT | Llave foránea relacionada con la dimensión ubicación. |
| id_vehiculo_dim | INT | Llave foránea relacionada con la dimensión vehículo. |
| id_modalidad | INT | Llave foránea relacionada con la dimensión modalidad transporte. |
| id_seguridad_vehiculo | INT | Llave foránea relacionada con la dimensión seguridad vehicular. |
| total_vehiculos | INT | Métrica utilizada para conteo total de vehículos involucrados. |
| vehiculo_sin_soat | INT | Indicador de vehículo sin SOAT vigente. |
| vehiculo_sin_revision | INT | Indicador de vehículo sin CITV o revisión técnica vigente. |

