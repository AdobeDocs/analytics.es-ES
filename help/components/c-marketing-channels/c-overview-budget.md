---
description: Aprenda a asignar importes de coste y presupuesto a los canales.
subtopic: Marketing channels
title: Costes y presupuestos
topic: Reports and analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Costes y presupuestos

Aprenda a asignar importes de coste y presupuesto a los canales.

El costo representa lo que gasta en el canal. El presupuesto representa el importe que se puede gastar.

Una manera práctica de ver el ROI es crear una métrica calculada que muestre los ingresos menos los costos. También se puede crear una que muestre el costo total junto con un desglose del costo por cada nuevo compromiso. Por ejemplo, puede ejecutar un informe de [!UICONTROL canal de primer toque] que muestre los compromisos nuevos; luego, puede agregar la métrica Costo de primer toque, que muestre el costo por cada nuevo compromiso, creando una métrica calculada.

Consulte [Informes de canales de marketing usados en métricas calculadas](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

Puede asignar costos y presupuestos solamente a los canales. A cada costo se le asigna un intervalo de tiempo durante el que se aplican a los informes. Cuando los costos se asocian con un canal directamente, se elige una métrica de asignación para mostrar el desglose de los costos en las campañas de un canal.

Después de agregar costos y elementos de presupuesto, puede exportar los datos de la tabla a un archivo CSV. También puede importar un archivo CSV a la página Costos de canal de mercadotecnia.

## Adición de elementos de costo y presupuesto {#add-cost-and-budget}

Agregue elementos de coste y presupuesto a los canales de mercadotecnia.

1. Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Grupo de informes]**.
1. En la página [!UICONTROL Administrador del grupo de informes], seleccione un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Canales de marketing]** &gt; **[!UICONTROL Costes del canal de marketing]**.
1. En la página [!UICONTROL Costos de canal de mercadotecnia]**, haga clic en[!UICONTROL Agregar elemento de costo]** o en **[!UICONTROL Agregar elemento de presupuesto]**.
1. Haga clic en **[!UICONTROL Guardar.]**

   Para continuar agregando elementos de costo, haga clic en **[!UICONTROL Guardar y agregar otro]**.

1. (Opcional) Para exportar o importar archivos CSV, acceda a la página [!UICONTROL Costes de canal de marketing], haga clic en **[!UICONTROL Exportar archivo]** o **[!UICONTROL Importar archivo]**, y siga los mensajes que se muestran.

## Costes de canal de marketing: Definiciones {#mktg-channel-costs}

Definiciones de los campos de costos o presupuestos de canal de mercadotecnia.

| Campo | Definición |
|--- |--- |
| Nombre | El nombre del elemento de costo o presupuesto. (Este valor es el valor de la clave si utiliza SAINT.) |
| Canal | El canal al que desea asociar este importe. Especifique si el costo o el presupuesto se aplica a un canal de primer toque o a un canal de último toque. La cantidad del costo de primer toque es como un nuevo compromiso único. La cantidad del costo de último toque es para las pulsaciones. |
| Intervalo de fechas | El tiempo que desee utilizar para este importe. |
| Tipo | El tipo de costo o presupuesto, ya sea una Tarifa o un Costo único. La Tarifa indica un costo constante como, por ejemplo, un importe por clic. El Costo único permite especificar un importe de Distribuir por. Por ejemplo, si distribuye el costo por clics, se atribuye el 60% del costo total al afiliado con el 60% del total de clics. El valor de Distribuido por es la métrica que se usa cuando se desglosan clasificaciones numéricas. |
| Exportar archivo | Permite exportar los datos de la tabla a un archivo CSV. |
| Importar archivo | Permite importar un archivo CSV a la página Costos de canal de mercadotecnia. |
