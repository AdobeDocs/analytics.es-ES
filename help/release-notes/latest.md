---
title: Ver las notas de la versión actual de Adobe Analytics
description: Últimas notas de la versión de Analytics
source-git-commit: f8c2d98e49ead838781b175aa9f22712d6802a9d
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 98%

---


# Últimas notas de la versión de Adobe Analytics

## Funciones nuevas en Adobe Analytics {#aa-features}

| Función | Descripción | Fecha objetivo |
| ----------- | ---------- | ------- |
| N/A |  | Consulte [Disponibilidad general](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=es) |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics y Customer Journey Analytics {#aa-fixes}

* Se ha corregido un problema de Analysis Workspace en el que el ID de audiencia faltaba en los elementos de dimensión. (AN-262038; AN-279315)
* Se ha corregido un problema que impedía a los usuarios cargar un archivo guardado [!DNL Target] en el Espacio de trabajo. (AN-277461; AN-275825; AN-266397)
* Se ha corregido un problema por el cual las funciones no habilitadas eran visibles en la interfaz de usuario. (AN-262006)
* Se ha corregido un problema que se producía al cambiar la fecha con el campo de fecha en el Espacio de trabajo. Esto resultó en el cambio de [!UICONTROL Hora de finalización] de 11:59 p. m. a 12:00 a. m. (AN-277269; AN-277481)
* Se ha corregido un problema que provocaba que la interfaz de usuario del segmento se interrumpiera al agregar nuevos segmentos a un segmento ya cargado. (AN-260827)
* Se ha corregido un problema que impedía a los usuarios acceder a proyectos compartidos del Espacio de trabajo. (AN-267529)
* Se ha añadido un mensaje de error que muestra cuándo un intervalo de fechas móvil tiene una fecha de inicio posterior a la fecha de finalización. (AN-270488)
* Se han corregido varios problemas de fuentes de datos. (AN-275876; AN-270512; AN-277284; AN-277290; AN-274893; AN-274606; AN-269651)
* Se ha corregido un problema con los intervalos de fechas en los gráficos que ignoraban los filtros de fecha en las tablas. (AN-263999)
* Se ha corregido un problema con los informes programados que se enviaban antes de tiempo debido al horario de verano. (AN-276410; AN-276305)
* Se ha corregido un problema de error con la descarga de proyectos en el archivo `.csv` en el Espacio de trabajo. (AN-275834)

### Correcciones adicionales en Adobe Analytics

AN-253294; AN-254976; AN-255377; AN-255561; AN-258550; AN-259336; AN-263935; AN-265094; AN-269441; AN-269486; AN-269855; AN-271166; AN-271588; AN-272088; AN-272249; AN-272859; AN-272873; AN-272885; AN-273229; AN-273913; AN-274237; AN-274472; AN-274491; AN-274619; AN-274766; AN-275248; AN-275259; AN-275271; AN-275315; AN-275388; AN-275418; AN-275597; AN-275643; AN-275650; AN-275651; AN-275675; AN-275682; AN-275704; AN-275711; AN-275796; AN-275834; AN-275923; AN-275941; AN-276044; AN-276125; AN-276157; AN-276397; AN-276597; AN-276789; AN-276834; AN-276861; AN-276870; AN-276963; AN-276975; AN-277000; AN-277044; AN-277093; AN-277200; AN-277215; AN-277271; AN-277281; AN-277362; AN-277419; AN-277492; AN-277498; AN-277533; AN-277619; AN-277675; AN-277681; AN-277767; AN-277805; AN-277810; AN-277818; AN-277875; AN-277933; AN-277988; AN-278105; AN-278115; AN-278122; AN-278192; AN-278407; AN-278437; AN-278559; AN-278604; AN-278610; AN-278709; AN-278835; AN-278849; AN-278881; AN-279067; AN-279103; AN-279111; AN-279219; AN-279237; AN-279312

## Avisos importantes para los administradores de [!DNL Analytics] {#aa-notices}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| Caducidad de la extensión EOL de la lista de permitidos para integraciones heredadas de Analytics OAuth/JWT | 14 de enero de 2022 | El **25 de mayo de 2022**, la extensión de lista de permitidos de [API de Analytics 1.3, API de SOAP 1.4 y EOL de OAuth/JWT de Analytics heredado](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) caducará. Se ofreció para proporcionar a los clientes que usan las credenciales de OAuth/JWT de [!DNL Adobe Analytics] más tiempo para migrar sus integraciones de cliente a las [credenciales de IMS de Adobe](https://developer.adobe.com/console). Esta caducidad afecta a clientes [!DNL Adobe Analytics Livestream] y [!DNL Adobe Campaign] (entre otros) que no hayan completado las migraciones de IMS requeridas. Clientes que actualmente utilizan las credenciales de la versión heredada [!DNL Analytics] OAuth/JWT a través de la extensión de la lista de permitidos y que no hayan completado su migración a las credenciales de IMS antes del 25 de mayo de 2022 perderán acceso a los servicios de Adobe. Los clientes de Livestream pueden consultar estas [instrucciones](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) al migrar sus aplicaciones cliente a credenciales de IMS. [!DNL Campaign] Los clientes pueden ponerse en contacto con el equipo de su cuenta de Adobe para actualizar a la última versión de [!DNL Campaign]. |
| EOL para [!DNL Reports & Analytics] | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar , y sus informes y funciones correspondientes. [!DNL Reports & Analytics] Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso explica el proceso de finalización de la vida útil.](https://spark.adobe.com/page/6WnF8JK6IRDhf/) |
| Actualización de servicios del Protocolo seguro de transferencia de archivos (SFTP) | 13 de enero de 2022 | El **2 de mayo de 2022**, [!DNL Adobe Analytics] actualizará sus servicios de Protocolo seguro de transferencia de archivos (SFTP) para proporcionar una seguridad mejorada para las transferencias de archivos. Con este cambio, algunas configuraciones de cliente SFTP ya no serán compatibles. También añadiremos algunas opciones de conexión que estarán disponibles el **1 de marzo de 2022**. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se verá afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |
| Tipo de RDC _Global + China_ | 22 de noviembre de 2021 | _Global + China_ es un nuevo tipo de recopilación de datos regionales (RDC) que simplifica el enrutamiento del tráfico para los clientes globales que usan el [!UICONTROL Paquete de complementos para la optimización del rendimiento en China]. En el pasado, tenía que determinar si los datos debían enrutarse al extremo de recopilación de China o a uno de los extremos de recopilación Global. Ahora puede elegir este *tipo* de RDC para permitir que Adobe determine el extremo de recopilación óptimo en función de la geolocalización del usuario. |
| Fin de la vida útil para el procesamiento completo en las fuentes de datos | 18 de octubre de 2021 | El **31 de enero de 2022**, Adobe terminará con el procesamiento completo, que permite a los usuarios ingerir datos de visitas sin conexión en Analytics. Esta funcionalidad está disponible mediante la [API de inserción de datos por lotes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). [Más información](https://experienceleague.adobe.com/docs/analytics/import/data-sources/data-types-and-categories/datasrc-fullproc-eol.html?lang=es ) |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).