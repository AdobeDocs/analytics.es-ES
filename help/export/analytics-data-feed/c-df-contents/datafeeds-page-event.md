---
description: La tabla de búsqueda para determinar el tipo de visita basándose en el valor de page_event.
keywords: Fuente de datos;página;evento;page_event;post_page_event
title: Búsqueda de eventos de página
feature: Conceptos básicos de Reports & Analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 94%

---

# Búsqueda de eventos de página

La tabla de búsqueda para determinar el tipo de visita basándose en el valor de page_event.

| Tipo de visita | `page_event` valor | `post_page_event` valor |
| --- | --- | --- |
| Vistas de páginas | 0: Todas las llamadas de vista de páginas y las llamadas `trackState` del SDK móvil | El mismo valor que `post_page_event` |
| Seguimiento de vínculos | 10: Vínculos personalizados y llamadas `trackAction` del SDK móvil<br>11: Vínculos de descarga<br>12: Vínculos de salida | 100: Vínculos personalizados y `trackAction` llamadas del SDK móvil<br>101: Vínculos de descarga <br>102: Vínculos de salida |
| Vídeo de Milestone | 31: Inicio de los medios<br>32: Actualizaciones de medios (sin otro procesamiento de variables)<br>33: Actualizaciones de medios (con otras variables) | 76: Inicio de los medios<br>77: Actualizaciones de medios (sin otro procesamiento de variables)<br>78: Actualizaciones de medios (con otras variables) |
| Vídeo de Heartbeat | 50: Inicio del flujo de medios (que no sea Primetime)<br>51: Cierre del flujo de medios (que no sea Primetime)<br>52: Eliminación de flujo de medios (que no sea Primetime)<br>53: El flujo de medios se mantiene vivo (no Primetime)<br>54: Inicio de anuncio de flujo de medios (que no sea Primetime)<br>55: Cierre de anuncio de flujo de medios (que no sea Primetime)<br>56: Depuración de anuncios de flujo de medios (que no sea Primetime)<br>60: Inicio del flujo de medios Primetime<br>61: Cierre del flujo de medios Primetime<br>62: Limpieza del flujo de medios Primetime<br>63: El flujo de medios Primetime se mantiene vivo<br>64: Inicio del anuncio del flujo de medios Primetime<br>65: Cierre del anuncio del flujo de medios Primetime<br>66: Limpieza del anuncio de flujo de medios Primetime | El mismo valor que `post_page_event` |
| Encuesta | 40: Cualquier llamada generada desde Survey | 80: Cualquier llamada generada desde Survey |
| Analytics para Target | 70: La visita incluye datos de actividad de Target | El mismo valor que `post_page_event` |
