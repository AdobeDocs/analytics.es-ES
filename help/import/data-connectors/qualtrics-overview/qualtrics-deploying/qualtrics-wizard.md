---
description: Para activar la integración debe completar el asistente de integración Qualtrics dentro de la interfaz de Data Connectors
seo-description: Para activar la integración debe completar el asistente de integración Qualtrics dentro de la interfaz de Data Connectors
seo-title: Finalización del Asistente para integración de Adobe
solution: Analytics
subtopic: Qualtrics
title: Finalización del Asistente para integración de Adobe
topic: Data Connectors
uuid: e 065 fba 4-1 fe 1-4 e 25-9 c 45-6 c 52 dc 20 f 81 e 81 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Para activar la integración debe completar el asistente de integración Qualtrics dentro de la interfaz de Data Connectors

1. Vaya a Conectores de datos e inicie el asistente de integración Qualtrics. ([Ayuda de Conectores de datos](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. Seleccione el grupo de informes que desee utilizar para esta integración y proporcione un nombre.

   Complete el asistente para integración, proporcionando la información descrita en los pasos siguientes. 1. **Paso 1 del Asistente**

   | Email Address | La dirección de correo electrónico de contacto principal. |
   |---|---|
   | Descripción | (Opcional) Descripción de esta configuración de integración. |
   | ID de organización de Qualtrics | [Buscar el ID de organización de Qualtrics](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Testigo de Adobe sitecatalyst | [Generación del testigo de Qualtrics Adobe Analytics](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. ** Asistente para el asistente 2 - Asignaciones de variables**

   | Lista de respuestas de Qualtrics | Seleccione una variable de lista disponible del grupo de informes. (Es posible que necesite habilitar una nueva listvar dentro del Administrador de grupos de informes). |
   |---|---|
   | ID de respuesta de Qualtrics | Seleccione una evar o prop disponible del grupo de informes. (Es posible que necesite habilitar una nueva listvar dentro del Administrador de grupos de informes). |
   | Servidor de seguimiento | Proporcione la configuración del servidor de seguimiento (dominio) que utiliza para rastrear datos de Adobe Analytics. Utilice el servidor `trackingServerSecure` de seguimiento si difiere de su configuración estándar del servidor de seguimiento. |
   | Qualtrics Survey Envíos | Seleccione un evento disponible del grupo de informes (es posible que necesite habilitar un nuevo evento desde el Administrador del grupo de informes). |

1. **Paso 3 del Asistente**: No se requiere nada, solo informativa.

   Resultado 1. ** Asistente para el asistente Paso 4 - Configuración de exportación**

   | eVar | Seleccione hasta cinco de las evars para exponer a Qualtrics. |
   |---|---|
   | Solicitud | Seleccione hasta cinco de los eventos personalizados para exponer a Qualtrics. |
   | Props | Seleccione hasta cinco de las Props para exponer a Qualtrics. |
   | Solicitudes de acceso | Marque la casilla de cualquiera de las métricas y dimensiones estándar que desee exportar a Qualtrics. Se `visitor_id` requiere de permitir que la exportación funcione correctamente. |

1. **Paso 5 del Asistente**: Revise la configuración y haga clic **[!UICONTROL en Activar ahora]**.
