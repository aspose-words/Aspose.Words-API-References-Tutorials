---
title: Construir tabla
linktitle: Construir tabla
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/build-table/
---

En este tutorial paso a paso, aprenderá a crear una tabla en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá crear una tabla con formato y contenido personalizados utilizando la clase DocumentBuilder.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Crear un nuevo documento
Para comenzar, crea un nuevo documento usando la clase Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Inicie la Mesa
A continuación, utilice el método StartTable de la clase DocumentBuilder para comenzar a construir la tabla:

```csharp
Table table = builder.StartTable();
```

## Paso 3: Insertar celdas y agregar contenido
Ahora, puede insertar celdas en la tabla y agregarles contenido utilizando los métodos InsertCell y Write de la clase DocumentBuilder. Personaliza el formato de celda según sea necesario:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Paso 4: terminar la fila
Después de agregar contenido a las celdas de la primera fila, use el método EndRow de la clase DocumentBuilder para finalizar la fila:

```csharp
builder.EndRow();
```

## Paso 5: personalizar el formato de fila
Puede personalizar el formato de una fila configurando las propiedades de los objetos RowFormat y CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Paso 6: terminar la mesa
Para completar la tabla, utilice el método EndTable de la clase DocumentBuilder:

```csharp
builder.EndTable();
```

### Código fuente de ejemplo para construir una tabla usando Aspose.Words para .NET
Aquí está el código fuente completo para construir una tabla usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo crear una tabla en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede crear tablas con formato personalizado.