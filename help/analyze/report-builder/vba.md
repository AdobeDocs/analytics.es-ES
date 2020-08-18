---
title: macros de Visual Basic en Report Builder
description: Expanda la funcionalidad de los libros y Report Builder de Excel mediante VBA.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# macros de Visual Basic en Report Builder

Las macros de VBA, también conocidas como macros de Visual Basic, permiten manipular libros de formas que Microsoft Excel no puede utilizar. Visual Basic tiene acceso al libro, Excel e incluso Windows.

Adobe admite tres métodos de API de Report Builder. Asegúrese de que está instalada la versión más reciente del creador de informes e inicie sesión antes de ejecutar macros.

>[!IMPORTANT]
>
>Por motivos de seguridad, no se puede programar un libro que contenga una macro.

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. Inicio llamando al Añada COM del Report Builder a través de su ID de producto y, a continuación, llama al comando `RefreshAllRequests()` API:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. La llamada de `RefreshWorksheetRequests()` API toma un objeto de hoja de cálculo como argumento. Puede utilizar esta llamada para cualquier hoja de cálculo que contenga solicitudes de Report Builder:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. El rango de celdas utilizado en este ejemplo apunta al rango `B1:B54` de la hoja de cálculo &quot;Datos&quot; dentro del libro activo. La expresión de rango admite todas las expresiones de rango de Excel admitidas:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
