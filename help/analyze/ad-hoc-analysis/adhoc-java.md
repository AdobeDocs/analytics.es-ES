---
description: Instrucciones sobre cómo ejecutar análisis específicos con Java 11.
title: Ejecutar Ad Hoc Analysis en Java 11
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ejecutar Ad Hoc Analysis en Java 11

Con Java 11, a diferencia de Java 8, es necesario seguir unos pasos adicionales al ejecutar el Ad Hoc Analysis.

## Requisitos previos

Trabaje con su equipo de TI para comprobar que se cumpla lo siguiente:

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* JavaFX debe estar instalado, con la variable de entorno *PATH_TO_FX_SDK* direccionada hacia el directorio JavaFX SDK. Por ejemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* en un Mac, o *PATH_TO_FX_SDK=C:\Usersername\javafx-sdk-11.0.2* en un PC.

## Instalación de Ad Hoc Analysis para Java 11

1. Vaya a **[!UICONTROL Analytics &gt; Herramientas &gt; Ad Hoc Analysis]**.
1. Haga clic en **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Esto descarga un archivo zip.
1. Descomprima el archivo descargado.
1. **Seleccione el archivo .bat (PC) o .sh (Mac)**. Para seleccionar el archivo del centro de datos adecuado, fíjese en el número siguiente a "sc" en la URL de Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Si utiliza un PC, verifique si está ejecutando un sistema operativo Windows de 32 o 64 bits si va a "Acerca de su PC". A continuación, seleccione el archivo .bat apropiado.
1. **Ejecutar el archivo seleccionado**. Para PC: Haga doble clic en el archivo .bat. Para Mac: Haga clic derecho en el archivo .sh y, a continuación, seleccione **[!UICONTROL Abrir con &gt; Otro....  &gt; Utilidades &gt; (Activar todas las aplicaciones) &gt; seleccione Terminal &gt; Abrir]**.
1. Inicie sesión en el Ad Hoc Analysis.

> [!NOTE] Los métodos de autenticación de Federated ID y Enterprise ID no son compatibles con la versión de Java 11 de los análisis específicos.

## Características no admitidas en el Ad Hoc Analysis (Java 11)

Existen algunas limitaciones conocidas en la versión de Java 11 compatible con los análisis específicos:

* No se admiten los métodos de autenticación Federated y Enterprise ID.
* Los sistemas operativos de Linux no son compatibles.
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). Esto puede hacer que el Ad Hoc Analysis se cierre sin previo aviso. En su lugar, utilice el menú dentro del Ad Hoc Analysis.
* La visualización del análisis del sitio no es compatible cuando al ejecutar el Ad Hoc Analysis en MacOS.

## Preguntas más frecuentes

**P: Aparece el error "No se encuentra \bin\javaw" (ejemplo más abajo): ¿qué debo hacer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Si le ocurre este error, trabaje con su equipo de TI para establecer la variable de entorno *JAVA_HOME* necesaria para ejecutar el Ad Hoc Analysis en Java 11.
