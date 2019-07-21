---
description: Las tablas siguientes muestran la asignación de informes a variables, o los informes y las variables que contienen.
keywords: Implementación de Analytics
seo-description: Las tablas siguientes muestran la asignación de informes a variables, o los informes y las variables que contienen.
seo-title: Informe a asignación de variables
solution: Analytics
title: Informe a asignación de variables
topic: Desarrollador e implementación
uuid: 4707660 c -4 be 5-425 c-a 690-7 bc 6 df 4 cc 0 fa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informe a asignación de variables

Las tablas siguientes muestran la asignación de informes a variables, o los informes y las variables que contienen.

**Informes de conversión** La siguiente tabla enumera las variables de conversión utilizadas para rellenar cada informe:

| Compras |
|---|
| Conversiones y promedios | s.events, s.products, s.purchaseID | Configure s.events como compra, detalle del producto o número de pedido |
| Ingresos | s.events, s.products, s.purchaseID | Configure s.events como compra, detalle del producto o número de pedido |
| Pedidos | s.events, s.products, s.purchaseID | Configure s.events como compra, detalle del producto o número de pedido |
| Unidades | s.events, s.products, s.purchaseID | Configure s.events como compra, detalle del producto o número de pedido |

| Carro de compras |
|---|
| Conversiones y promedios | s.events, s.products, s.purchaseID |  |
| Carro de compras | s.events. | Configure s.events como scOpen |
| Vistas del carro de compras | s.events. | Configure s.events como scView |
| Adiciones al carro de compras | s.events. | Configure s.events como scAdd |
| Eliminaciones del carro de compras | s.events. | Configure s.events como scRemove |
| Cierres de compra | s.events. | Configure s.events como scCheckout |

| Eventos personalizados |
|---|
| Evento personalizado n.º 1 | s.events. | Rellenar con event1 - event100 |
| … | … | Rellenar con event1 - event100 |
| Evento personalizado 100 | s.events | Rellenar con event1 - event100 |

| Productos |
|---|
| Conversiones y promedios | s.events, s.products, s.purchaseID |  |
| Productos | s.products, s.events | Puede variar en función de las métricas de la columna derecha |
| Venta cruzada | s.products, s.events, s.purchaseID | Puede variar en función de las métricas de la columna derecha |
| Categorías | s.products | Puede variar en función de las métricas de la columna derecha |

| Campañas |
|---|
| Conversiones y promedios | s.products, s.events, s.campaign |  |
| Código de seguimiento | s.campaign |  |
| Elementos creativos | N.D. | Defined in [!DNL Analytics] |
| Campañas | N.D. | Defined in [!DNL Analytics] |

| Lealtad del cliente |
|---|
| Lealtad del cliente | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |

| Ciclo de ventas |
|---|
| Días antes de la primera compra | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |
| Días desde la última compra | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |
| Número de visitas | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |
| Clientes únicos diarios | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |
| Clientes únicos mensuales | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |
| Clientes únicos anuales | s.products, s.events, s.purchaseID | Variables configuradas en la confirmación del pedido (Gracias) page |

| Métodos de búsqueda |
|---|
| Dominios de referencia | N.D. | Configurado automáticamente por el archivo .JS |
| Dominios de referencia originales | N.D. | Configurado automáticamente por el archivo .JS |
| Motores de búsqueda | N.D. | Configurado automáticamente por el archivo .JS |
| Palabras clave de búsqueda | N.D. | Configurado automáticamente por el archivo .JS |

| Perfil del visitante |
|---|
| Dominios de nivel superior | N.D. | Configurado automáticamente por el archivo .JS |
| Idiomas | N.D. | Configurado automáticamente por el archivo .JS |
| Zonas horarias | N.D. | Configurado automáticamente por el archivo .JS |
| Estados | s.state | Variable configurada en la confirmación del pedido (Gracias) page |
| Códigos postales | s.zip | Variable configurada en la confirmación del pedido (Gracias) page |
| Dominios | N.D. | Configurado automáticamente por el archivo .JS |

| Tecnología |
|---|
| Exploradores | N.D. | Configurado automáticamente por el archivo .JS |
| Sistemas operativos | N.D. | Configurado automáticamente por el archivo .JS |
| Resoluciones de monitor | N.D. | Configurado automáticamente por el archivo .JS |

| Ruta del sitio |
|---|
| Valor de la página | s.pageName, s.products, s.events, s.purchaseID |  |
| Páginas de entrada | s.pageName |  |
| Páginas de entrada originales | s.pageName |  |
| Páginas por visita | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Tiempo empleado en el sitio | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Secciones del sitio | [!UICONTROL s.channel] | Igual que el informe [!UICONTROL Canal] en la sección de informes [!UICONTROL Tráfico] |

| Variables del cliente |
|---|
| Evar personalizada 1 | [!UICONTROL s.eVar] 1 |  |
| Evar personalizada 2 | [!UICONTROL s.eVar] 2 |  |
| Evar personalizada 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| Evar personalizada 75 | [!UICONTROL s.eVar] 75 |  |

## Informes de tráfico {#section_76A74C3D7B60461D9ADE0E5E183DD777}

La tabla siguiente muestra las variables de [!UICONTROL tráfico] que se usan para rellenar cada informe:

| Métricas calculadas |
|---|
| N.D. | N.D. | N.D. |

| Tráfico del sitio |
|---|
| Vistas de páginas | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitantes únicos por hora | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitantes únicos diarios | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitantes únicos mensuales | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitantes únicos anuales | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitas | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Descargas de archivos | N.D. | Configurado automáticamente por el archivo .JS (depende de la configuración de las variables JS) |

| Métodos de búsqueda |
|---|
| Dominios de referencia | N.D. | Configurado automáticamente por el archivo .JS |
| Referentes | N.D. | Configurado automáticamente por el archivo .JS |
| Motores de búsqueda | N.D. | Configurado automáticamente por el archivo .JS |
| Palabras clave de búsqueda | N.D. | Configurado automáticamente por el archivo .JS |
| Frecuencia de retorno | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitas de retorno diario | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Visitas de retorno | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Números de visita | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |

| Perfil del visitante |
|---|
| Dominios | N.D. | Configurado automáticamente por el archivo .JS |
| Dominios de nivel superior | N.D. | Configurado automáticamente por el archivo .JS |
| Idiomas | N.D. | Configurado automáticamente por el archivo .JS |
| Zonas horarias | N.D. | Configurado automáticamente por el archivo .JS |
| Detalles del visitante | N.D. | Configurado automáticamente por el archivo .JS |
| Últimos 100 visitantes | N.D. | Calculado mediante reglas empresariales en [!DNL Analytics] |
| Página principal del usuario | N.D. | Configurado automáticamente por el archivo .JS |
| Visitantes clave | N.D. | Basado en la dirección IP del visitante |
| Páginas consultadas por los visitantes clave | N.D. | Basado en la dirección IP del visitante |

| Segmentación geográfica |
|---|
| Países | N.D. | Basado en la dirección IP del visitante |
| Estados de EE. UU. | N.D. | Basado en la dirección IP del visitante |
| DMA | N.D. | Basado en la dirección IP del visitante |
| Ciudades internacionales | N.D. | Basado en la dirección IP del visitante |
| Ciudades de EE. UU. | N.D. | Basado en la dirección IP del visitante |

| Tecnología |
|---|
| Tipos de explorador | N.D. | Configurado automáticamente por el archivo .JS |
| Exploradores | N.D. | Configurado automáticamente por el archivo .JS |
| Dispositivos móviles | N.D. | Configurado automáticamente por el archivo .JS |
| Ancho del explorador | N.D. | Configurado automáticamente por el archivo .JS |
| Altura del explorador | N.D. | Configurado automáticamente por el archivo .JS |
| Sistemas operativos | N.D. | Configurado automáticamente por el archivo .JS |
| Profundidad del color del monitor | N.D. | Configurado automáticamente por el archivo .JS |
| Resoluciones de monitor | N.D. | Configurado automáticamente por el archivo .JS |
| Complementos de Netscape | N.D. | Configurado automáticamente por el archivo .JS |
| Java | N.D. | Configurado automáticamente por el archivo .JS |
| Las etiquetas | N.D. | Configurado automáticamente por el archivo .JS |
| Versión de JavaScript | N.D. | Configurado automáticamente por el archivo .JS |
| Cookies | N.D. | Configurado automáticamente por el archivo .JS |
| Tipos de conexión | N.D. | Configurado automáticamente por el archivo .JS |
| Segmentación |

| Segmentación |
|---|
| Páginas más populares | s.pageName |  |
| Secciones del sitio más populares | s.channel |  |
| Servidores más populares | s.server |  |

| Perspectiva personalizada |
|---|
| Vínculos personalizados | s.linkName | Requiere una implementación personalizada |
| Perspectiva personalizada 1 | s.prop1 |  |
| … | … |  |
| Perspectiva personalizada 75 | s.prop75 |  |

| Jerarquías |
|---|
| Jerarquía 1 | s.hier1 |  |
| … | … |  |
| Jerarquía 5 | s.hier5 |  |

## Informes de rutas {#section_85E0A2396B894659A6BE572819263E95}

La tabla siguiente muestra las variables de rutas que se usan para rellenar cada informe en [!DNL Analytics]:

| Páginas |
|---|
| Resumen de página | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Valor de la página | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Páginas más populares | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Recargas | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Clics hasta la página | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Tiempo empleado en la página | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Páginas no encontradas | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |

| Entradas y salidas |
|---|
| Páginas de entrada | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Páginas de salida | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Vínculos de salida | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |

| Rutas completas |
|---|
| Rutas completas | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Rutas más largas | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Longitud de ruta | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Tiempo empleado por visita | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Visitas a una sola página | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |

| Análisis avanzado |
|---|
| Página anterior | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Página siguiente | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Flujo de página anterior | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Flujo de página siguiente | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| PathFinder | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
| Visitas en el orden previsto | s.pageName (u otra variable con ruta) | También depende de las reglas empresariales internas |
