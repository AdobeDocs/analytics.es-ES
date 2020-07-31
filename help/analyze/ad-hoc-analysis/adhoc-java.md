---
description: Instrucciones sobre cómo ejecutar Ad Hoc Analysis con Java 11.
title: Ejecutar Ad Hoc Analysis en Java 11
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '369'
ht-degree: 100%

---


# Ejecutar Ad Hoc Analysis en Java 11

Con Java 11, a diferencia de Java 8, es necesario seguir unos pasos adicionales al ejecutar el Ad Hoc Analysis.

## Requisitos previos

Trabaje con su equipo de TI para comprobar que se cumpla lo siguiente:

* Java 11 debe estar instalado, con el conjunto de variables de entorno *JAVA_HOME* configurado
* JavaFX debe estar instalado, con la variable de entorno *PATH_TO_FX_SDK* direccionada hacia el directorio JavaFX SDK. Por ejemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* en un Mac, o *PATH_TO_FX_SDK=C:\Usersername\javafx-sdk-11.0.2* en un PC.

## Instalación de Ad Hoc Analysis para Java 11

1. Vaya a **[!UICONTROL Analytics > Herramientas > Ad Hoc Analysis]**.
1. Haga clic en **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Esto descarga un archivo zip.
1. Descomprima el archivo descargado.
1. **Seleccione el archivo .bat (PC) o .sh (Mac)**. Seleccione el archivo del centro de datos adecuado mirando el número que sigue a “sc” en la URL de Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Si utiliza un PC, compruebe si está ejecutando un sistema operativo Windows de 32 bits o de 64 bits en “Acerca de su PC”. A continuación, seleccione el archivo .bat apropiado.
1. **Ejecutar el archivo seleccionado**. Para PC: Haga doble clic en el archivo .bat. Para Mac: Haga clic derecho en el archivo .sh y, a continuación, seleccione **[!UICONTROL Abrir con > Otro.... > Utilidades > (Activar todas las aplicaciones) > seleccione Terminal > Abrir]**.
1. Inicie sesión en el Ad Hoc Analysis.

>[!NOTE]
>
>La versión Java 11 del Ad Hoc Analysis no admite los métodos de autenticación Federated y Enterprise ID.

## Características no admitidas en el Ad Hoc Analysis (Java 11)

Existen algunas limitaciones conocidas en la versión Java 11 compatible con Ad Hoc Analysis:

* No se admiten los métodos de autenticación Federated y Enterprise ID.
* Los sistemas operativos de Linux no son compatibles.
* Cuando utilice Mac, no use el menú de aplicación de Mac (incluido *cmd + Q*). Esto puede hacer que el Ad Hoc Analysis se cierre sin previo aviso. En su lugar, utilice el menú dentro del Ad Hoc Analysis.
* La visualización del análisis del sitio no es compatible cuando al ejecutar el Ad Hoc Analysis en MacOS.

## Preguntas más frecuentes

**P: Aparece un error “No se puede encontrar el archivo \bin\javaw” (ejemplo abajo), ¿qué tengo que hacer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Si le ocurre este error, trabaje con su equipo de TI para establecer la variable de entorno *JAVA_HOME* necesaria para ejecutar el Ad Hoc Analysis en Java 11.
