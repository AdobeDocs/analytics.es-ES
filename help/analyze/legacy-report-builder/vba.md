---
title: Cómo utilizar macros de Visual Basic en Report Builder
description: Obtenga información sobre cómo expandir la funcionalidad de los libros y Report Builder de Excel mediante macros de VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 64%

---

# Macros de Visual Basic en Report Builder

{{legacy-arb}}

Las macros de Visual Basic (VBA) proporcionan características que ayudan a actualizar los libros de Excel. Visual Basic tiene acceso al libro, Excel y Windows.

Debe ejecutar la última versión de Report Builder e iniciar sesión antes de ejecutar macros de VBA.

>[!IMPORTANT]
>
>Por motivos de seguridad, no se puede programar un libro que contenga una macro.

El Adobe admite tres métodos de API de Report Builder.

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
