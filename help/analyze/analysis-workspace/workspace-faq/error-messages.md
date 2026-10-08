---
description: Obtenga información acerca de los errores y solución de problemas de Analysis Workspace.
title: Errores y solución de problemas
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
TQID: 'https://experienceleague.adobe.com/Kr34CyT7YxRqKRdwpaLN-DZwHhLbaT663Gj-pc5Wd8s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 94%
---
# Errores y solución de problemas

Puedes encontrar errores al interactuar con Analysis Workspace que también afectarán a su funcionalidad o rendimiento. A continuación se enumeran los tipos de error más comunes, por qué se producen y las optimizaciones que se pueden realizar.

## Mensajes de error

Algunos mensajes de error comunes que puedes ver al utilizar Analysis Workspace:

| Mensaje de error | ¿Por qué se produce el error? | Optimización |
| --- | --- | --- |
| [!UICONTROL El grupo de informes está experimentando una creación de informes inusualmente alta. Inténtelo nuevamente más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en un grupo de informes específico. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones del grupo de informes de forma más uniforme durante todo el día.<p>Los administradores pueden usar el [Administrador de actividades de creación de informes para identificar y cancelar las solicitudes](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) que consumen capacidad de creación de informes.</p> |
| [!UICONTROL Este informe es demasiado complejo. Consulte las prácticas recomendadas para generar informes de Analysis Workspace.] | La solicitud de creación de informes es demasiado grande y no se puede ejecutar. Los factores que contribuyen a este error son los tiempos de espera debido a la complejidad de la solicitud. | Simplifica tu solicitud. Por ejemplo, acortar el intervalo de fechas, simplificar los criterios de segmento o quitar algunas columnas o filas de la tabla. O bien, considera la posibilidad de dividir la tabla en solicitudes independientes. |
| [!UICONTROL El grupo de informes supera actualmente su capacidad de creación de informes. Simplifique la solicitud o vuelva a intentarlo más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en un grupo de informes específico. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones del grupo de informes de forma más uniforme durante todo el día. |
| [!UICONTROL Se ha producido un error del sistema. Registre una solicitud del Servicio de atención al cliente en **[!UICONTROL Ayuda > Enviar ticket de asistencia técnica]** e incluya su código de error.] | Adobe está experimentando un problema que debe resolverse. | Envíe el código de error al Servicio de atención al cliente. |
| [!UICONTROL Error 500: No se pudo cargar la página] | Los problemas con la red local, como la [configuración del firewall](/help/technotes/ip-addresses.md) de la compañía, son un factor que contribuye a este error. Además, es posible que el Adobe esté experimentando un problema que debe resolverse. | Intente iniciar sesión nuevamente después de varios minutos. Si el problema persiste, envíe el código de ID de instancia de EIM al Servicio de atención al cliente. |
| [!UICONTROL Su solicitud falló como resultado de demasiadas columnas o filas preconfiguradas.] | La tabla tiene demasiadas celdas improvisadas (columnas de fila *). | Elimine columnas o filas de la tabla, o bien considere la posibilidad de dividir la tabla en solicitudes independientes. |


## Resolución de problemas

Al utilizar Analysis Workspace, puede utilizar la siguiente información para solucionar algunos problemas comunes.

| Problema | Pasos para solucionar los problemas |
|---|---|
| Cuando arrastro una métrica, dice *“Datos no válidos”*. | Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra. |
| Cuando arrastro una métrica, no veo ningún dato real, solo ceros. | Si ha creado correctamente un informe de Workspace pero no hay datos, puede comprobar algunas cosas:<ul><li>Si aplicó un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.</li><li>Comprueba el intervalo de fechas en la esquina superior derecha y comprueba que está establecido en un valor que esperabas.</li><li>Vaya a su sitio web y use [Adobe Experience Platform Debugger](https://experienceleague.adobe.com/es/docs/experience-platform/debugger/home) para validar que se están recopilando datos.</li></ul> |
