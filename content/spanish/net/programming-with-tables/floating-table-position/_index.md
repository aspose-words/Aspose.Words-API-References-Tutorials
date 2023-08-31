---
title: Posición de la mesa flotante
linktitle: Posición de la mesa flotante
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a colocar una tabla en posición flotante en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/floating-table-position/
---

En este tutorial, aprenderemos cómo usar Aspose.Words para .NET para colocar una tabla en una posición flotante en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá controlar la posición y alineación de las tablas flotantes en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento y acceder a la tabla
Para iniciar el procesamiento de textos con la tabla, debemos cargar el documento que la contiene y acceder a ella. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Acceso a la matriz
Table table = doc.FirstSection.Body.Tables[0];
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga una tabla que se colocará en una posición flotante.

## Paso 3: Colocar la tabla flotante
A continuación, colocaremos la tabla en una posición flotante usando las propiedades proporcionadas por Aspose.Words para .NET. Utilice el siguiente código:

```csharp
// Colocación de la mesa flotante
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Aquí utilizamos el`AbsoluteHorizontalDistance` Propiedad para establecer la distancia horizontal absoluta de la tabla desde el borde izquierdo de la página. También utilizamos el`RelativeVerticalAlignment` propiedad para establecer la alineación vertical relativa de la tabla con respecto al contenido circundante.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la tabla colocada en posición flotante. Utilice el siguiente código:

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para la posición de la tabla flotante usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Conclusión
En este tutorial, aprendimos cómo colocar una tabla en posición flotante en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede controlar la posición y alineación de las tablas flotantes en sus documentos de Word mediante programación.