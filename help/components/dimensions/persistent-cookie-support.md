---
title: Compatibilidad con cookies persistentes
description: Determina si el visitante puede admitir cookies persistentes.
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 11%

---

# Compatibilidad con cookies persistentes

La dimensión &quot;Compatibilidad con cookies persistentes&quot; muestra si la visita utilizó un identificador de visitante originado en una fuente persistente. La fuente persistente más común es de una cookie, pero también puede utilizar encabezados móviles y otras fuentes.

## Rellene esta dimensión con datos

Adobe determina el valor de esta dimensión del lado del servidor en función del origen del identificador de la visita. No hay una forma de configurarlo directamente. Funciona de forma predeterminada para todas las implementaciones.

## Elementos de dimensión

* **`Enabled`**: El identificador de visitante de la visita proviene de un origen que normalmente persiste. Los ejemplos más comunes incluyen parámetros de cadena de consulta `aid`, `fid` o `mid`, ya que derivan sus valores de una cookie.
* **`Disabled`**: El identificador de visitante de la visita proviene de una fuente que el Adobe no reconoce como persistente, como IP + cadena del agente de usuario. Este elemento de dimensión también incluye los ID de visitante personalizados que utilizan la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) .

## Diferencia entre &#39;Compatibilidad con cookies&#39; y &#39;Compatibilidad con cookies persistentes&#39;

* **Compatibilidad con cookies**: AppMeasurement intenta establecer una cookie genérica. El elemento de dimensión se basa en si la cookie se configuró correctamente.
* **Compatibilidad con cookies persistentes**: El elemento de dimensión se basa en si el identificador de la visita se originó a partir de una fuente persistente, como una cookie.
