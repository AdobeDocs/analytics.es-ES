---
description: Funciones de soporte de accesibilidad en Análisis Workspace
title: Accesibilidad en el área de trabajo de Análisis
translation-type: tm+mt
source-git-commit: a8fa30ecd8f3f230dac98a6f69ff6334d996fb9c
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 4%

---


# Accesibilidad en el área de trabajo de Análisis

Obtenga información sobre la compatibilidad con la accesibilidad en [!UICONTROL Análisis Workspace], la herramienta de análisis más importante para Adobe Analytics.

La accesibilidad se refiere a hacer que los productos sean utilizables para personas con discapacidades visuales, auditivas, cognitivas, motoras y de otro tipo. Algunos ejemplos de funciones de accesibilidad para productos de software son la compatibilidad con lectores de pantalla, equivalentes de texto para gráficos, métodos abreviados de teclado, cambio de colores de visualización a alto contraste, etc.

[!UICONTROL Espacio de trabajo] de Análisis proporciona algunas herramientas que lo hacen accesible para su uso, entre las que se incluyen:

## Navegar por [!UICONTROL Workspace] mediante el teclado

La navegación en [!UICONTROL Análisis Workspace] funciona arriba > abajo e izquierda > derecha. Los siguientes elementos de navegación facilitan la accesibilidad:

* La `F6` tecla habilita los accesos directos de puntos de referencia
* La `Tab` clave se mueve entre elementos individuales.
* Aplicamos indicadores de enfoque para que los usuarios de teclado con visión de futuro tengan una clara indicación de qué elemento de interfaz de usuario está seleccionado actualmente. El indicador es un borde azul alrededor del elemento seleccionado.

   ![Indicador de enfoque](assets/focus-indicator.png)

### Navegación por teclado para interacciones de arrastrar y soltar

[!UICONTROL Análisis Workspace] es una interfaz de usuario de arrastrar y soltar. Sin embargo, los usuarios pueden agregar componentes mediante el teclado:

1. Tabulación a un componente en el carril izquierdo.
1. Pulse `Enter` para seleccionar.
1. Utilice las teclas de flecha para desplazarse hasta el área en la que desea soltar el componente.
1. Pulse `Enter` para colocar el componente.

### Métodos abreviados de teclado (teclas de acceso directo)

[!UICONTROL Espacio de trabajo] de Análisis oferta un completo conjunto de atajos [de](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.translate.html) teclado para lograr un flujo de trabajo más fluido. A continuación se enumeran algunos métodos abreviados comunes para la navegación, la creación de análisis y la democratización de la perspectiva.

#### Navegación

| Acceso directo | Acción |
|---|---|
| Alt + Mayús + 1 / 2 / 3 | Saltar a diferentes carriles: [!UICONTROL Paneles], [!UICONTROL visualizaciones]o [!UICONTROL componentes] |
| Alt + flecha izquierda/derecha | Desplazamiento entre paneles |
| Alt + M | Contraer/expandir todos los paneles |
| Alt + Ctrl + M | Contraer/expandir panel activo |
| Ctrl + / | Buscar carril izquierdo |

#### Creación de Análisis

| Acceso directo | Acción |
|---|---|
| Alt + 1 | Nueva tabla improvisada |
| Ctrl + Mayús + C | Nueva métrica calculada |
| Ctrl + Mayús + D | Nuevo intervalo de fechas |
| Ctrl + Mayús + E | Nuevo segmento |
| Ctrl + Z | Deshacer |
| Mantenga pulsada la tecla Mayús (en la zona desplegable de segmentos del panel) | Creación de un filtro [desplegable](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### Democratización

| Acceso directo | Acción |
|---|---|
| Ctrl + S | Guardar |
| Ctrl + Mayús + G | Depurar |
| Ctrl + G | Compartir |
| Alt + Mayús + S | Programa |
| Alt + L | Obtener vínculo al proyecto |
| Ctrl + Mayús + B | Descargar PDF |

## Compatibilidad con lectores de pantalla y ampliadores de pantalla

Un lector de pantalla lee el texto que aparece en la pantalla del equipo. También lee información no textual, como etiquetas de botones o descripciones de imágenes en la aplicación, proporcionada en etiquetas o atributos de accesibilidad.

## Paletas de color y contraste

[!UICONTROL Espacio de trabajo] de Análisis se esfuerza por lograr la conformidad con WCAG 2.1 AA, incluidos los requisitos para el contraste de color.

Además, los usuarios pueden establecer su propia paleta de colores preferida para un proyecto en **[!UICONTROL Proyecto]** > Ajustes **[!UICONTROL del]** proyecto > Paleta [de color](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html)Proyecto.

## Validación de campo requerida en los generadores de componentes

Al crear un componente, los campos obligatorios se validan al guardarlos. Si un campo requerido no supera la validación, se delineará en rojo con un icono de error. Aparece una descripción por escrito del problema que debe solucionarse.

Una vez validado el componente, al pulsar `Save` se cierra el generador.

![Validación de errores](assets/error-validation.png)

## Compatibilidad con las funciones de accesibilidad del sistema operativo

Análisis Workspace admite funciones de accesibilidad integradas de MS Windows y macOS, como modo de alto contraste, teclas adhesivas y teclas de filtro/teclas lentas. También proporciona información sobre la interfaz de usuario del sistema operativo para habilitar la interacción con tecnologías de asistencia, incluidos lectores de pantalla como VoiceOver para macOS y NVDA en Windows.