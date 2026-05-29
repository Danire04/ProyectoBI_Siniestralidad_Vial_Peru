Diccionario de datos

 # Diccionario de Datos — Datamart de Siniestros Viales

-------------------------------------------------------------------------------------------------------------------
## FACT_SINIESTROS

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_siniestro_fact | INT | Identificador único del registro en la tabla de hechos de siniestros. |
| codigo_siniestro | VARCHAR(50) | Código identificador del siniestro vial registrado. |
| id_fecha | INT | Clave foránea que referencia a la dimensión fecha. |
| id_ubicacion | INT | Clave foránea que referencia a la dimensión ubicación. |
| id_via | INT | Clave foránea que referencia a la dimensión vía. |
| id_causa | INT | Clave foránea que referencia a la dimensión causa. |
| id_clima | INT | Clave foránea que referencia a la dimensión clima. |
| id_senalizacion | INT | Clave foránea que referencia a la dimensión señalización. |
| cantidad_fallecidos | INT | Total de personas fallecidas registradas en el siniestro. |
| cantidad_lesionados | INT | Total de personas lesionadas registradas en el siniestro. |
| cantidad_vehiculos_danados | INT | Total de vehículos dañados registrados en el siniestro. |
| total_siniestros | INT | Indicador numérico para conteo y agregación de siniestros. |

-------------------------------------------------------------------------------------------------------------------
## FACT_PERSONAS

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_persona_fact | INT | Identificador único del registro en la tabla de hechos de personas. |
| codigo_siniestro | VARCHAR(50) | Código del siniestro vial al que pertenece la persona. |
| id_fecha | INT | Clave foránea que referencia a la dimensión fecha. |
| id_ubicacion | INT | Clave foránea que referencia a la dimensión ubicación. |
| id_persona_dim | INT | Clave foránea que referencia a la dimensión persona. |
| id_licencia | INT | Clave foránea que referencia a la dimensión licencia. |
| id_dosaje | INT | Clave foránea que referencia a la dimensión dosaje. |
| id_gravedad | INT | Clave foránea que referencia a la dimensión gravedad. |
| total_personas | INT | Total de personas involucradas en el siniestro. |
| fallecido | INT | Indicador numérico de personas fallecidas en el evento. |
| lesionado | INT | Indicador numérico de personas lesionadas en el evento. |

-------------------------------------------------------------------------------------------------------------------
## FACT_VEHICULOS

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_vehiculo_fact | INT | Identificador único del registro en la tabla de hechos de vehículos. |
| codigo_siniestro | VARCHAR(50) | Código del siniestro vial al que pertenece el vehículo. |
| id_fecha | INT | Clave foránea que referencia a la dimensión fecha. |
| id_ubicacion | INT | Clave foránea que referencia a la dimensión ubicación. |
| id_vehiculo_dim | INT | Clave foránea que referencia a la dimensión vehículo. |
| id_modalidad | INT | Clave foránea que referencia a la dimensión modalidad transporte. |
| id_seguridad_vehiculo | INT | Clave foránea que referencia a la dimensión seguridad vehículo. |
| total_vehiculos | INT | Total de vehículos involucrados en el siniestro. |
| vehiculo_sin_soat | INT | Indicador numérico de vehículos sin SOAT vigente. |
| vehiculo_sin_revision | INT | Indicador numérico de vehículos sin revisión técnica vigente. |

-------------------------------------------------------------------------------------------------------------------
## DIM_FECHA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_fecha | INT | Identificador único de la dimensión fecha. Llave primaria para relacionar las tablas de hechos. |
| fecha | DATE | Fecha exacta en la que ocurrió el siniestro o evento relacionado. |
| anio | INT | Año correspondiente al evento vial. Facilita análisis históricos anuales. |
| mes | INT | Número del mes del evento, utilizado para agrupaciones temporales. |
| nombre_mes | VARCHAR(20) | Nombre textual del mes para facilitar visualizaciones y reportes. |
| trimestre | INT | Trimestre del año en que ocurrió el evento vial. |
| dia | INT | Día del mes correspondiente al evento. |
| dia_semana | VARCHAR(20) | Día de la semana asociado a la fecha del evento. |
| fin_semana | VARCHAR(10) | Indicador de si el evento ocurrió durante un fin de semana. |

-------------------------------------------------------------------------------------------------------------------
## DIM_UBICACION

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_ubicacion | INT | Identificador único de la dimensión ubicación. |
| departamento | VARCHAR(100) | Departamento del Perú donde ocurrió el siniestro vial. |
| provincia | VARCHAR(100) | Provincia donde se registró el evento vial. |
| distrito | VARCHAR(100) | Distrito exacto donde ocurrió el siniestro. |
| ubicacion | VARCHAR(255) | Nombre aproximado de la vía o zona georreferenciada asociada al evento. |
| latitud | DECIMAL(10,6) | Coordenada geográfica de latitud utilizada para análisis espacial. |
| longitud | DECIMAL(10,6) | Coordenada geográfica de longitud utilizada para análisis espacial. |
| codigo_carretera | VARCHAR(50) | Código identificador de la carretera asociada al siniestro vial. |
| red_vial | VARCHAR(100) | Clasificación o tipo de red vial a la que pertenece la vía. |

-------------------------------------------------------------------------------------------------------------------
## DIM_VIA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_via | INT | Identificador único de la dimensión vía. |
| tipo_via | VARCHAR(100) | Clasificación del tipo de vía donde ocurrió el evento vial. |
| superficie_calzada | VARCHAR(100) | Tipo de superficie presente en la calzada de la vía. |
| caracteristicas_via | VARCHAR(150) | Características estructurales registradas en la vía del siniestro. |
| perfil_longitudinal | VARCHAR(100) | Perfil longitudinal de la vía asociado al accidente. |

-------------------------------------------------------------------------------------------------------------------
## DIM_CAUSA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_causa | INT | Identificador único de la dimensión causa. |
| causa_principal | VARCHAR(150) | Factor principal identificado como origen del siniestro vial. |
| causa_especifica | VARCHAR(255) | Descripción específica y detallada de la causa registrada. |

-------------------------------------------------------------------------------------------------------------------
## DIM_CLIMA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_clima | INT | Identificador único de la dimensión clima. |
| condicion_climatica | VARCHAR(100) | Condición climática registrada al momento del siniestro vial. |
| zonificacion | VARCHAR(100) | Tipo de zona geográfica o zonificación donde ocurrió el evento. |

-------------------------------------------------------------------------------------------------------------------
## DIM_SENALIZACION

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_senalizacion | INT | Identificador único de la dimensión señalización. |
| existe_senal_vertical | VARCHAR(10) | Indicador de existencia de señalización vertical en la vía. |
| clasificacion_senal_1 | VARCHAR(150) | Primera clasificación de señal vertical registrada. |
| clasificacion_senal_2 | VARCHAR(150) | Segunda clasificación de señal vertical registrada. |
| existe_senal_horizontal | VARCHAR(10) | Indicador de existencia de señalización horizontal en la vía. |

-------------------------------------------------------------------------------------------------------------------
## DIM_PERSONA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_persona_dim | INT | Identificador único de la dimensión persona. |
| tipo_persona | VARCHAR(100) | Tipo de persona involucrada en el evento vial: conductor, peatón o pasajero. |
| sexo | VARCHAR(20) | Sexo registrado de la persona involucrada. |
| edad | INT | Edad registrada de la persona involucrada en el siniestro. |
| rango_edad | VARCHAR(30) | Clasificación etaria utilizada para segmentación y análisis estadístico. |

-------------------------------------------------------------------------------------------------------------------
## DIM_LICENCIA

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_licencia | INT | Identificador único de la dimensión licencia. |
| posee_licencia | VARCHAR(10) | Indicador de si la persona posee licencia de conducir. |
| estado_licencia | VARCHAR(50) | Estado actual de la licencia registrada. |
| clase_licencia | VARCHAR(50) | Clase o categoría de licencia asociada a la persona. |

-------------------------------------------------------------------------------------------------------------------
## DIM_DOSAJE

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_dosaje | INT | Identificador único de la dimensión dosaje. |
| sometio_dosaje_cualitativo | VARCHAR(10) | Indicador de si se realizó prueba cualitativa de alcoholemia. |
| resultado_dosaje_cualitativo | VARCHAR(100) | Resultado obtenido en la prueba cualitativa de alcoholemia. |
| sometio_dosaje_cuantitativo | VARCHAR(10) | Indicador de si se realizó prueba cuantitativa de alcoholemia. |

-------------------------------------------------------------------------------------------------------------------
## DIM_GRAVEDAD

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_gravedad | INT | Identificador único de la dimensión gravedad. |
| gravedad | VARCHAR(50) | Nivel de gravedad registrado para la persona involucrada. |

-------------------------------------------------------------------------------------------------------------------
## DIM_VEHICULO

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_vehiculo_dim | INT | Identificador único de la dimensión vehículo. |
| vehiculo | VARCHAR(100) | Tipo o categoría del vehículo involucrado. |

-------------------------------------------------------------------------------------------------------------------
## DIM_MODALIDAD_TRANSPORTE

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_modalidad | INT | Identificador único de la dimensión modalidad transporte. |
| estado_modalidad | VARCHAR(100) | Estado de la modalidad de transporte registrada. |
| modalidad_transporte | VARCHAR(100) | Modalidad de transporte asociada al vehículo. |
| ambito_servicio | VARCHAR(100) | Ámbito de servicio correspondiente al vehículo. |

-------------------------------------------------------------------------------------------------------------------
## DIM_SEGURIDAD_VEHICULO

| Campo | Tipo de dato | Descripción |
|:---|:---|:---|
| id_seguridad_vehiculo | INT | Identificador único de la dimensión seguridad vehicular. |
| posee_seguro | VARCHAR(10) | Indicador de si el vehículo posee seguro vigente. |
| estado_soat | VARCHAR(50) | Estado del SOAT registrado para el vehículo. |
| tipo_seguro | VARCHAR(100) | Tipo de seguro asociado al vehículo. |
| posee_citv | VARCHAR(10) | Indicador de existencia de certificado CITV. |
| estado_citv | VARCHAR(50) | Estado del certificado de inspección técnica vehicular. |

