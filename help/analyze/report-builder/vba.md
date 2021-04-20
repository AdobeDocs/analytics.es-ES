---
title: Macros de Visual Basic en Report Builder
description: Expanda la funcionalidad de los libros y Report Builder de Excel mediante VBA.
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 98%

---


# Macros de Visual Basic en Report Builder

Las macros de VBA, también conocidas como macros de Visual Basic, permiten manipular libros de formas que Microsoft Excel no puede. Visual Basic tiene acceso al libro, Excel e incluso Windows.

Adobe admite tres métodos de API de Report Builder. Asegúrese de que está instalada la versión más reciente del creador de informes e inicie sesión antes de ejecutar cualquier macro.

>[!IMPORTANT]
>
>Por motivos de seguridad, no se puede programar un libro que contenga una macro.

## `RefreshAllReportBuilderRequests()`

La macro `RefreshAllReportBuilderRequests()` actualiza todas las solicitudes del Report Builder del libro activo. Se inicia llamando al complemento COM del Report Builder a través de su ID de producto y, a continuación, llama al comando API `RefreshAllRequests()`:

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

La macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` actualiza todas las solicitudes del Report Builder de la hoja de cálculo activa. La llamada de API `RefreshWorksheetRequests()` toma un objeto de hoja de cálculo como argumento. Puede utilizar esta llamada para cualquier hoja de cálculo que contenga solicitudes de Report Builder:

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

La macro `RefreshAllReportBuilderRequestsInCellsRange()` actualiza todas las solicitudes del Report Builder cuyas salidas de celda forman intersecciones con un intervalo de celdas específico. El rango de celdas utilizado en este ejemplo apunta al rango `B1:B54` de la hoja de cálculo “Datos” dentro del libro activo. La expresión de rango admite todas las expresiones de rango de Excel admitidas:

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
