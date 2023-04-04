---
title: Resumen de fuentes de datos
description: Importe datos en Adobe Analytics mediante archivos externos.
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Resumen de fuentes de datos

Las fuentes de datos de Adobe Analytics permiten importar datos sin conexión o en línea adicionales para la realización de informes. Son útiles para comprender las facetas de su negocio fuera del sitio web y cómo interactúan con el sitio. El flujo de trabajo general para utilizar fuentes de datos consta de los siguientes pasos:

1. Su organización recopila datos de otras fuentes. Algunos ejemplos son los datos preclic, los datos del centro de llamadas o la información sobre transacciones que se produjeron fuera del sitio.
1. Los datos tienen un formato que Adobe Analytics entiende que se utiliza un archivo de texto delimitado por tabuladores.
1. El archivo de texto se carga en el Adobe de un sitio FTP y se adjunta `.fin` archivo.
1. Adobe ingesta el archivo de texto y muestra esos datos junto con las dimensiones y métricas recopiladas en el sitio.

Existen dos tipos generales de fuentes de datos que ofrecen Adobe. Todas las plantillas de fuentes de datos se basan en uno de estos dos tipos:

* **Fuente de datos de resumen**: Proporciona una forma sencilla de importar datos de alto nivel en Adobe Analytics. La marca de tiempo, el valor de la variable y las métricas asociadas se especifican. Estas métricas para cada elemento de dimensión se incrementan en consecuencia. Es útil si desea ver los datos sin conexión y en línea en paralelo. Sin embargo, no vincula los datos en línea y sin conexión.
* **Fuente de datos de ID de transacción**: Si una visita enviada por AppMeasurement y una fila de fuentes de datos contienen ID de transacción coincidentes, los valores de dimensión y métrica de la fuente de datos se adjuntan a esa visita.

**Fuentes de datos de procesamiento completo** ya no se ofrecen como tipo de fuente de datos a partir del 25 de marzo de 2021. Consulte la [Anuncio de fin de vida útil](full-processing-eol.md) para obtener más información.

El Adobe también ofrece la [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que le permite crear fuentes de datos y cargar datos sin usar la interfaz de usuario del producto ni una ubicación FTP.

## Pasos siguientes

[Introducción a las fuentes de datos](getting-started.md): Cargue una fuente de datos sencilla en un grupo de informes de desarrollo.
