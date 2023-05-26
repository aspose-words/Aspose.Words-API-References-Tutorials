---
title: Recuperar tipo de ancho preferido
linktitle: Recuperar tipo de ancho preferido
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recuperar el tipo y el valor de ancho preferido de una celda en una tabla de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/retrieve-preferred-width-type/
---

En este tutorial, aprenderemos cómo recuperar el tipo de ancho preferido y su valor de una celda de tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá recuperar el tipo de ancho preferido (absoluto, relativo o automático) y su valor para una celda específica en las tablas de su documento de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento
Para comenzar a trabajar con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento
Document doc = new Document(dataDir + "Tables.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: Recuperar el tipo y valor de ancho preferido
A continuación, recuperaremos el tipo de ancho preferido y su valor para una celda de tabla específica. Usa el siguiente código:

```csharp
// recuperar la mesa
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Activar el ajuste automático de la mesa
table. AllowAutoFit = true;

// Recuperar la primera celda de la primera fila
Cell firstCell = table.FirstRow.FirstCell;

// Recuperar el tipo de ancho preferido y su valor
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Aquí usamos el documento para obtener la primera tabla, luego habilitamos el ajuste automático de la tabla con el`AllowAutoFit` propiedad. Luego recuperamos la primera celda de la primera fila de la tabla. Desde esta celda, podemos recuperar el tipo de ancho preferido con el`PreferredWidth.Type` propiedad y su valor con el`PreferredWidth.Value` propiedad.

### Ejemplo de código fuente para recuperar el tipo de ancho preferido mediante Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusión
En este tutorial, aprendimos cómo recuperar el tipo de ancho preferido y su valor de una celda de tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede recuperar esta información para celdas específicas en las tablas de su documento de Word.