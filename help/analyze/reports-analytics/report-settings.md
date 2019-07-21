---
description: Configuración que define cómo aparecen todos los informes y la información que toma las opciones de menú predeterminadas a su ubicación en el menú simplificado.
seo-description: Configuración que define cómo aparecen todos los informes y la información que toma las opciones de menú predeterminadas a su ubicación en el menú simplificado.
seo-title: La configuración de visualización de informes y navegación
solution: Analytics
title: La configuración de visualización de informes y navegación
topic: Informes,Reports and Analytics
uuid: e 7 e 571 ce-a 1 cf -4714-b 400-9571805 ceeac
translation-type: tm+mt
source-git-commit: 612cbb694f16b5b4fcbf2d9cae55bc52103cc0b9

---


# La configuración de visualización de informes y navegación

Configuración que define cómo aparecen todos los informes y la información que asigna las opciones de menú predeterminadas a su ubicación en el menú simplificado.

## Report display settings and navigation {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Configuración de informes]**

<!--Meike, I replaced this table with one from https://marketing.adobe.com/resources/help/en_US/sc/user/report_settings.html -bob -->

| Elemento | Descripción |
|--- |--- |
| **Ajustes generales** |  |
| Incluir la sección Métricas relacionadas | Las métricas relacionadas tienen relación estrecha con el informe que está viendo (por ejemplo, las cinco páginas más visitadas del informe Vistas de páginas). |
| Mostrar el promedio de Internet en la sección Detalles | Expresa el valor promedio de una estadística determinada, teniendo en cuenta miles de sitios Web comerciales. Cuando está habilitada, esta sección aparece como una columna por separado en las secciones Resumen del informe y Detalles del informe. Solo los informes de tráfico del grupo de tecnología, como los informes de motores de búsqueda, de idiomas y de dominios utilizan esta función. |
| Mostrar la estructura de menú predeterminada de Adobe | Omite la configuración de las Herramientas de administración, donde los administradores personalizan los menús del informe para ajustarse a las preferencias de los usuarios, y restaura el menú del informe con la configuración predeterminada. |
| Forzar los anchos de columna cuando se muestren los informes | Fuerza los anchos de columna de los informes para lograr uniformidad desde el punto de vista estético. Esta opción es útil cuando se muestran más de tres métricas. |
| **Gráficos y diagramas** |  |
| Resaltar los fines de semana en los gráficos de tendencia | Resalta las fechas de fin de semana de forma vertical en los gráficos de informes de tendencia. Los informes de tendencia podrían ser más fáciles de evaluar cuando se identifican los fines de semana. |
| Incluir previsión en resumen y en gráfico | Estima la cantidad de estadísticas particulares que se producirán en un futuro. La previsión aparece en la sección resumen del informe cuando está habilitada. |
| Incluir eventos de calendario en los informes | Rastrea el rendimiento del sitio en relación con eventos específicos. Cuando se habilita, dichos eventos aparecen en los informes. |
| Usar gráficos Flash | Habilita los gráficos Flash en los informes. Los gráficos Flash proporcionan imágenes más interactivas y más nítidas para los informes, pero no permiten copiar ni guardar fácilmente las imágenes. Para copiar y guardar con más facilidad, deshabilite esta opción (las imágenes estarán en formato .gif). Si deshabilita esta opción, el botón Copiar gráfico no aparece en la barra de herramientas del informe. |
| Mostrar los datos "Restantes" en los gráficos seleccionados | Muestra todos los demás debajo de los cinco más populares en un mismo objeto. (Los gráficos de barra muestran las cinco páginas Web más visitadas u otros datos dentro del informe.) |
| Mostrar los datos de "Ninguno," "No especificado" y "Escritos o marcadores" en los gráficos de los informes | Muestra las métricas en las que ningún valor recibió crédito por la métrica especificada. |
| Mostrar minigráficos en informes de clasificación | Muestra un minigráfico en el campo de totales de los informes de clasificación. Esto proporciona una visión rápida de la tendencia general sin necesidad de generar un informe aparte. |
| **Aceleración** |  |
| Habilitar el acelerador de informes para ver los informes más rápidamente | Habilita el acelerador de informes, que utiliza un algoritmo basado en el tiempo para almacenar en caché los informes solicitados recientemente y examina solamente los elementos únicos que ocurren con poca frecuencia, teniendo como resultado envíos de informes más rápidos. Si almacena en caché los informes solicitados durante 15 minutos, el acelerador de informes puede recuperar esos informes para solicitudes posteriores de forma instantánea. Esta opción es útil cuando explora hacia atrás y adelante, imprime informes o para obtener acceso en forma frecuente a los mismos informes. Cuando está desactivado, el sistema vuelve a generar los informes cada vez que se solicitan. |
| Habilitar el acelerador de tableros y mostrar las versiones en caché disponibles | Habilita el acelerador de tableros que almacena una versión en caché del tablero para vistas subsiguientes. Si almacena en caché una vista del tablero durante 24 horas, el acelerador de tableros es capaz de ver casi de forma instantánea, porque la base de datos y el procesamiento intensivo se realizan con antelación. Si la versión en caché disponible tiene más de 24 horas, se generará un nuevo tablero y se creará una nueva versión en caché. Del mismo modo, se creará una versión en caché cada vez que actualice el tablero (o cualquier informe breve mostrado en el tablero). La versión en caché se basa en el usuario. Otros usuarios que ven un tablero compartido ven una versión basada en su propio uso del acelerador de tableros y en la actualización del mismo. |
| Habilitar la aceleración de redes para un rendimiento de informes mejorado | Acelera el envío de datos a su ubicación, optimizando la ruta entre la infraestructura de Adobe y su entorno. |
| Habilitar la aceleración regional para una experiencia de usuario más rápida en China | El Acelerador regional utiliza dominios acelerados específicos de la región para ofrecer una experiencia de usuario más rápida dentro de una región específica. Actualmente, la aceleración regional solo es compatible en China. La activación de esta función para usuarios que no estén ubicados en China hará que la experiencia sea más lenta. Después de habilitar la aceleración regional debe iniciar sesión de nuevo para que la configuración sea efectiva. Si desea deshabilitar el Acelerador regional, desactive esta casilla de verificación. |
| **Idioma/Moneda/Codificación** |  |
| Separador de miles | Seleccione un separador para cada miles (decimal o coma). Según el país, se utiliza el punto o la coma para separar los miles. (Este separador se aplica a todos los números del sistema, no solo a la moneda.) |
| Utilice la moneda predeterminada del grupo de informes | Especifica si se utiliza la moneda predeterminada del grupo de informes. |
| Moneda | La moneda a la que quiere convertir sus datos. Cuando se selecciona un valor en esta configuración, la selección no afecta a los datos almacenados en la base de datos, pero se muestra como un valor convertido basado en la tasa de conversión de moneda del día actual. Cuando no se han configurado las opciones de moneda (cuando son las predeterminadas), no se realiza ninguna conversión de moneda, y todos los valores se almacenan y se muestran en dólares estadounidenses (USD). Para convertir la moneda cuando se procesen los datos (antes de mostrarlos), póngase en contacto con su Administrador de cuentas. |
| Codificación de informe programado | Shift-JIS para la codificación de caracteres japoneses. EUC-JP para código Unix ampliado, principalmente para japonés, coreano y chino simplificado. |
| Carácter separador de CSV | El carácter que desea utilizar para separar valores CSV. |

## Menú de navegación {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Si está acostumbrado al menú predeterminado, la tabla siguiente le facilita encontrar las opciones de menú en el menú simplificado.

| Ubicación en el menú predeterminado | Ubicación en el menú simplificado |
|---|---|
| **Métricas del sitio** |  |  |
|  | Información general de sitio | Métricas &gt; Información general del sitio |
|  | Métricas clave | Métricas &gt; Métricas clave |
|  | Vistas de páginas | Métricas &gt; Vistas de páginas |
|  | Visitas | Métricas &gt; Visitas |
|  | Visitantes | Métricas &gt; Visitantes |
|  | Tiempo empleado por visita | Métricas &gt; Tiempo empleado por visita |
|  | Tiempo previo al evento | Métricas &gt; Tiempo previo al evento |
|  | Compras | Métricas &gt; Compras |
|  | Carro de compras | Métricas &gt; Carro de compras |
|  | Eventos personalizados | Métricas &gt; Eventos personalizados |
|  | Bots | Audiencia &gt; Bots |
|  | Detección de anomalías | Métricas &gt; Detección de anomalías |
|  | Tiempo real | Métricas &gt; Tiempo real |
| **Contenido del sitio** |  |  |
|  | Páginas | Contenido &gt; Páginas |
|  | Secciones del sitio | Contenido &gt; Secciones del sitio |
|  | Servidores | Contenido &gt; Servidores |
|  | Vínculos | Navegación &gt; Vínculos personalizados; Navegación &gt; Vínculos de salida; Navegación &gt; ClickMap; Navegación &gt; Descargas de archivos |
|  | Páginas no encontradas | Navegación &gt; Páginas no encontradas |
| **Móvil** |  |  |
|  | Dispositivos | Audiencia &gt; Móvil &gt; Dispositivos |
|  | Tipo de dispositivo | Audiencia &gt; Móvil &gt; Tipo de dispositivo |
|  | Fabricante | Audiencia &gt; Móvil &gt; Fabricante |
|  | Tamaño de la pantalla | Audiencia &gt; Móvil &gt; Tamaño de la pantalla |
|  | Altura de la pantalla | Audiencia &gt; Móvil &gt; Altura de la pantalla |
|  | Ancho de la pantalla | Audiencia &gt; Móvil &gt; Ancho de la pantalla |
|  | Compatibilidad con cookies | Audiencia &gt; Móvil &gt; Compatibilidad con cookies |
|  | Compatibilidad con imágenes | Audiencia &gt; Móvil &gt; Compatibilidad con imágenes |
|  | Profundidad de color | Audiencia &gt; Móvil &gt; Profundidad de color |
|  | Compatibilidad con audio | Audiencia &gt; Móvil &gt; Compatibilidad con audio |
|  | Compatibilidad con vídeo | Audiencia &gt; Móvil &gt; Compatibilidad con vídeo |
|  | Sistema operativo | Audiencia &gt; Móvil &gt; Sistema operativo |
| **Rutas** |  |  |
|  | Páginas | Navegación &gt; Rutas &gt; Páginas |
|  | Términos de búsqueda interna | Navegación &gt; Rutas &gt; Términos de búsqueda interna |
| **Fuentes de tráfico** |  |  |
|  | Palabra clave de búsqueda: todo | Fuentes de tráfico &gt; Palabra clave de búsqueda: todo |
|  | Palabra clave de búsqueda: de pago | Fuentes de tráfico &gt; Palabra clave de búsqueda: de pago |
|  | Palabra clave de búsqueda: natural | Fuentes de tráfico &gt; Palabra clave de búsqueda: natural |
|  | Motores de búsqueda: todo | Fuentes de tráfico &gt; Motores de búsqueda: todo |
|  | Motores de búsqueda: de pago | Fuentes de tráfico &gt; Motores de búsqueda: de pago |
|  | Motores de búsqueda: natural | Fuentes de tráfico &gt; Motores de búsqueda: natural |
|  | Clasificación de todas las páginas de búsqueda | Fuentes de tráfico &gt; Clasificación de todas las páginas de búsqueda |
|  | Dominios de referencia | Fuentes de tráfico &gt; Dominios de referencia |
|  | Dominios de referencia originales | Fuentes de tráfico &gt; Dominios de referencia originales |
|  | Referentes | Fuentes de tráfico &gt; Referentes |
|  | Tipos de referente | Fuentes de tráfico &gt; Tipos de referente |
| **Campañas** |  |  |
|  | Canal de conversión de campañas | Fuentes de tráfico &gt; Campañas &gt; Canal de conversión de campañas |
|  | Código de seguimiento | Fuentes de tráfico &gt; Campañas &gt; Código de seguimiento |
| **Productos** |  |  |
|  | Canal de conversión de productos | Conversión &gt; Productos &gt; Canal de conversión de productos |
|  | Productos | Conversión &gt; Productos &gt; Productos |
|  | Venta cruzada | Conversión &gt; Productos &gt; Venta cruzada |
|  | Categorías | Conversión &gt; Productos &gt; Categorías |
| **Retención de visitantes** |  |  |
|  | Frecuencia de retorno | Audiencia &gt; Retención de visitantes &gt; Frecuencia de retorno |
|  | Visitas de retorno | Audiencia &gt; Retención de visitantes &gt; Visitas de retorno |
|  | Visitas de retorno diario | Audiencia &gt; Retención de visitantes &gt; Visitas de retorno diario |
|  | Número de visitas | Audiencia &gt; Retención de visitantes &gt; Número de visitas |
|  | Ciclo de ventas | Audiencia &gt; Retención de visitantes &gt; Ciclo de ventas |
| **Perfil del visitante** |  |  |
|  | Segmentación geográfica | Audiencia &gt; Perfil del visitante &gt; Segmentación geográfica |
|  | Idiomas | Audiencia &gt; Perfil del visitante &gt; Idiomas |
|  | Zonas horarias | Audiencia &gt; Perfil del visitante &gt; Zonas horarias |
|  | Dominios | Audiencia &gt; Perfil del visitante &gt; Dominios |
|  | Dominios de nivel superior | Audiencia &gt; Perfil del visitante &gt; Dominios de nivel superior |
|  | Tecnología | Audiencia &gt; Perfil del visitante &gt; Tecnología |
|  | Estado del visitante | Audiencia &gt; Perfil del visitante &gt; Estado de visitante |
|  | Código postal del visitante | Audiencia &gt; Perfil del visitante &gt; Código postal del visitante |
| **Conversión personalizada** |  |  |
|  | Conversión personalizada 1-10 | Conversión &gt; Conversión personalizada &gt; Conversión personalizada 1-10 |
|  | Conversión personalizada 11-20 | Conversión &gt; Conversión personalizada &gt; Conversión personalizada 11-20 |
| **Tráfico personalizado ** |  |  |
|  | Tráfico personalizado 1-10 | Contenido &gt; Tráfico personalizado &gt; Tráfico personalizado 1-10 |
| **Test&amp;Target ** |  | Conversión &gt; Test&amp;Target |
| **Survey** |  | Audiencia &gt; Survey |
| **Canales de marketing** |  |  |
|  | Informe de descripción general de canal | Fuentes de tráfico &gt; Canales de marketing &gt; Informe de descripción general de canal |
|  | Canal de primer toque | Fuentes de tráfico &gt; Canales de marketing &gt; Canal de primer toque |
|  | Detalles de canal de primer toque | Fuentes de tráfico &gt; Canales de marketing &gt; Detalles de canal de primer toque |
|  | Canal de último toque | Fuentes de tráfico &gt; Canales de marketing &gt; Canal de último toque |
|  | Detalles de canal de último toque | Fuentes de tráfico &gt; Canales de marketing &gt; Detalles de canal de último toque |
| **Aplicación móvil** |  |  |
|  | Información general de aplicación móvil | Contenido &gt; Aplicación móvil &gt; Información general de aplicación móvil |
|  | Informes de ciclo de vida | Contenido &gt; Aplicación móvil &gt; Informes de ciclo de vida |
| **Informes personalizados ** |  |  |
|  | Los informes personalizados solo se muestran si tiene alguno configurado. | Informes personalizados |
|  |  |  |

