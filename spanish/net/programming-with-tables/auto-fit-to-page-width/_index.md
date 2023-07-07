---
title: Ajuste automático al ancho de la página
linktitle: Ajuste automático al ancho de la página
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a ajustar automáticamente una tabla al ancho de página en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/auto-fit-to-page-width/
---

En este tutorial, aprenderemos a usar Aspose.Words para .NET para ajustar automáticamente una tabla al ancho de página en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá manipular tablas en documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación y configuración del documento
Para comenzar a trabajar con la tabla, necesitamos crear un documento y configurar el generador de documentos. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Crear el documento y el generador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Inserción y configuración de la mesa
A continuación, insertaremos una tabla en el documento con un ancho que ocupe la mitad del ancho de la página. Usa el siguiente código:

```csharp
// Inserta la tabla y configura su ancho
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Aquí usamos el generador de documentos para comenzar a crear la tabla, insertar celdas y establecer el ancho preferido de la tabla al 50% del ancho de la página. Luego agregamos texto en cada celda.

## Paso 4: Guardar el documento modificado
Finalmente, debemos guardar el documento modificado con la tabla ajustada al ancho de la página. Usa el siguiente código:

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.
  
### Ejemplo de código fuente para Ajuste automático al ancho de la página usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserte una tabla con un ancho que ocupe la mitad del ancho de la página.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusión
En este tutorial, aprendimos cómo ajustar automáticamente una tabla al ancho de página en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# proporcionado, puede manipular tablas en sus documentos de Word mediante programación. Esta función le permite adaptar dinámicamente el ancho de la tabla según la página, ofreciendo así un documento profesional y visualmente atractivo.