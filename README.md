# **Segmentación de clientes aplicado al análisis de reducción de tasas de natalidad en Colombia** 
## Seminario de Analítica y Ciencia de Datos

## **1. Generalidades**

### **1.1 Objetivo:**
Pre-procesar un conjunto de datos extraidos del DANE **(nombrado: nac2022.csv )** con las  estadísticas asociadas a los nacimientos en Colombia para el año 2022. Este, corresponde a una 
muestra del total de datos seleccionados en el planteamiento del presente proyecto (5 años) y serviran de base para explorar los modelos de regresión y clasificación
a implementar. 

### **1.2 Anotaciones importantes sobre el conjunto de datos**
Se tiene una base de datos con 39 columnas y 573.625 filas con datos demograficos, sociales, geograficos y educativos asociados a los nacimientos de individuos en el territorio
Colombiano, esta información se encuentra codificada de la siguiente manera: 

****
    
| Campo | Descripción | Ejemplo |
| :--- | :--- |:--- |
| COD_DPTO | Departamento de Nacimiento  | 17=Caldas |
| COD_MUNIC | Municipio de Nacimiento  | 15= Boyaca |
| AREANAC | Área del Nacimiento  | 3 = Rural disperso |
| SIT_PARTO | Sitio de la Parto  | 1= Institución de salud |
| OTRO_SIT | Otro sitio, ¿cuál?  | 2 = Domicilio |
| SEXO | Sexo del nacido vivo  | 1= Masculino |
| PESO_NAC | Peso del nacido vivo, al nacer | 1 = Menos de 1.000 |
| TALLA_NAC | Talla del nacido vivo, al nacer  | 1 = Menos de 20 |
| ANO | Año de la ocurrencia  | 2022 |
| MES | Mes de la ocurrencia  | 03 = Marzo |
| ATEN_PAR | El parto fue atendido por  | 1 = Médico |
| T_GES | Tiempo de gestación del nacido vivo  | 2 = De 22 a 27 |
| T_GES_AGRU_CIE | Tiempo de gestación del nacido vivo ajustado a la agrupación sugerida por la CIE (T_GES_AGRU_CIE)  | 3 = De 28 a 36|
| NUMCONSUL | Número de consultas prenatales que tuvo la madre del nacido vivo  | 00= Ninguna |
| TIPO_PARTO | Tipo de parto de este nacimiento  | 2 = Cesárea |
| MUL_PARTO | Multiplicidad del embarazo  | 3 = Triple |
| APGAR1 | Prueba APGAR al minuto del nacido vivo  | 01 - 10 = Al minuto |
| APGAR2 | Prueba APGAR a los cinco minutos del nacido vivo  | 01 - 10 = A los cinco minutos |
| IDHEMOCLAS | Hemoclasificación del nacido vivo: Grupo Sanguíneo  | 1 = A |
| IDFACTORRH | Hemoclasificación del nacido vivo: Factor RH | 1 = Positivo |
| IDPERTET | De acuerdo con la cultura, pueblo o rasgos físicos, el nacido vivo es reconocido por sus padres como  | 1 = Indígena |
| EDAD_MADRE | Edad de la madre a la fecha del parto | 2 = De 15-19 Años |
| EST_CIVM | Estado conyugal de la madre  | 4 = Está viuda |
| NIV_EDUM | Ultimo nivel de estudio que aprobó la madre  | 2 = Básica primaria |
| ULTCURMAD | Ultimo año o grado aprobado de la madre  | 99 = Sin información |
| CODPRES | País de residencia habitual de la madre en el extranjero  | Colombia |
| CODPTORE | Departamento de residencia habitual de la madre | 05 =	Antioquia |
| CODMUNRE | Municipio de residencia habitual de la madre  | 1 = Cabecera municipal |
| AREA_RES | Área de residencia habitual de la madre  | 2 = Centro poblado |
| N_HIJOSV | Número de hijos nacidos vivos que ha tenido la madre, incluido el presente  | 3 = 3 hijos |
| FECHA_NACM | Fecha de nacimiento del anterior hijo nacido vivo  | 99 = Sin información |
| N_EMB | Número de embarazos, incluido el presente  | 99 = Sin información |
| SEG_SOCIAL | Régimen de seguridad social en salud de la madre | 2 = Subsidiado |
| IDCLASADMI | Entidad Administradora en Salud a la que pertenece la madre  | 1 = Entidad promotora de salud |
| EDAD_PADRE | Edad del padre en años cumplidos a la fecha del nacimiento de este hijo  | 999 = Sin información |
| NIV_EDUP | Nivel educativo del padre, ultimo año de estudio que aprobó el padre | 5 = Media técnica |
| ULTCURPAD | Ultimo año o grado aprobado del padre  | 99 = Sin información |
| PROFESION | Profesión de quien certifica el nacimiento  | 2 = Enfermero(a) |
| TIPOFORMULARIO | Fuente del Certificado  | 1 = Certificado RUAF-ND |

    
****

    
Url origen datos: https://microdatos.dane.gov.co/index.php/catalog/807/data-dictionary/F32?file_name=nac2022
