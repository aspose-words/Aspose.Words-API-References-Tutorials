---
title: Mover a la celda de la tabla
linktitle: Mover a la celda de la tabla
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para usar Move To Table Cell en Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-table-cell/
---

En este ejemplo, lo guiaremos a través de cómo usar la función Mover a la celda de la tabla de Aspose.Words para .NET usando el código fuente de C# proporcionado paso a paso. Esta característica le permite navegar y manipular celdas específicas dentro de una tabla en un documento de Word. Siga los pasos a continuación para integrar esta funcionalidad en su aplicación.

## Paso 1: Cargue el documento que contiene la tabla

Primero, necesitamos cargar el documento que contiene la tabla a la que queremos mover la celda. Utilice el siguiente código para realizar este paso:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Este código carga el documento especificado (reemplace "MyDir + "Tables.docx"" con la ruta real de su documento que contiene la tabla).

## Paso 2: Mueva DocumentBuilder a una celda de tabla específica

A continuación, moveremos DocumentBuilder a una celda de tabla específica. Use el siguiente código para realizar este paso:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 Este código crea un DocumentBuilder a partir del documento existente y luego mueve el cursor del DocumentBuilder a la celda de la tabla especificada. Finalmente, agrega contenido a esa celda usando el DocumentBuilder`Write()` método.

## Paso 3: Comprueba el resultado

Ahora puede verificar que el movimiento a la celda de la tabla fue exitoso. Utilice el siguiente código para realizar este paso:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Este código verifica que la celda especificada sea de hecho la celda actual de DocumentBuilder. También verifica que el contenido agregado por DocumentBuilder se haya guardado correctamente en la celda de la tabla.

Eso es todo ! Ahora ha entendido cómo usar la funcionalidad de mover a la celda de la tabla de Aspose.Words para .NET usando el código fuente proporcionado. Ahora puede integrar esta funcionalidad en su propia aplicación y manipular celdas de tabla específicas en documentos de Word.


### Ejemplo de código fuente para moverse a una celda de tabla usando Aspose.Words para .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Mueva el generador a la fila 3, celda 4 de la primera tabla.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```
