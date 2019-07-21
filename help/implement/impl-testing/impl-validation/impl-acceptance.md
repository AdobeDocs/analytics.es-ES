---
description: Pasos del proceso de implementación
keywords: Implementación de Analytics
seo-description: Pasos del proceso de implementación
seo-title: Aceptación de la implementación
solution: Analytics
title: Aceptación de la implementación
topic: Desarrollador e implementación
uuid: 6 f 7 ec 56 e -9 e 4 f -4 dc 8-b 534-92 b 1580 b 5 b 47
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aceptación de la implementación

Pasos del proceso de implementación

Los pasos siguientes resumen el proceso de implementación.

1. El consultor de Adobe reúne los requisitos de informes y crea un plan de recopilación de datos basado en esos requisitos.

   El plan de recopilación de datos incluye definiciones de variables, reglas de VISTA requeridas y JavaScript personalizado, correlación de datos y todas las opciones de configuración de cada grupo de informes. El cliente completa el Cuestionario de implementación.
1. Los recursos técnicos en el lado del cliente implementan el código, el JavaScript específico del sitio y las variables del lado del servidor.
1. El consultor de Adobe aborda los problemas técnicos durante la implementación y ayuda a idear las soluciones necesarias.
1. Los recursos técnicos en el lado del cliente prueban la implementación.

   Testers log in to [!DNL Analytics] and verifying all variables ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, econversion variables, custom traffic variables, *`products`*, and all other variables).
1. El cliente notifica a Adobe que la implementación se ha completado.

   El cliente proporciona una muestra de validación (muestra de datos) al consultor de Adobe para validar la precisión de los datos. (Los grupos de informes generados por VISTA se validan comparando las métricas correspondientes. Debe realizarse de antemano un acuerdo entre el cliente y Adobe con las métricas que se validarán para dichos grupos de informes, en el momento de crear la regla de VISTA).
1. El cliente envía por fax (o firma en línea) un Acuerdo y aceptación de la implementación para los sitios correspondientes.
1. Una vez recibida la aceptación, el consultor de Adobe habilita la certificación Prácticas recomendadas de Adobe - Verificación de la implementación en la interfaz.
1. El cliente también tiene la opción de contratar servicios de monitoreo con Adobe para las páginas clave del sitio implementado (generalmente son las plantillas principales, la página de inicio y las páginas de entrada críticas).

   Este software de monitoreo se describe en un documento aparte, pero realiza el seguimiento de las páginas cargando y ejecutando la página y, después, compara la solicitud de imagen con una referencia almacenada en la base de datos. Si se detectan diferencias, el software las notifica al personal de Adobe (AM/IE) y del cliente por correo electrónico.

Los siguientes elementos ayudan a garantizar una implementación correcta:

* Un documento de prácticas recomendadas, orientado al cliente, que explica el proceso con detalle.
* El documento de validación que el cliente usa para realizar pruebas unitarias de la implementación.
* Un formulario de Acuerdo y aceptación de la implementación para que lo firme el cliente.
* Una aplicación de monitoreo que valida continuamente las etiquetas.
* Una relación con Accenture para ayudar a realizar las pruebas de implementación.
* Utilidades y herramientas para comparar las vistas de páginas y los pedidos. Estas comparaciones pueden resultar bastante difíciles.
* Un método o proceso para obtener rápidamente el registro de depuración de un día determinado, por ID de grupo de informes.

