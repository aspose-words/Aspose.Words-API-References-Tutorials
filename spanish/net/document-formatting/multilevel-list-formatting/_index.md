---
title: Formato de lista multinivel
linktitle: Formato de lista multinivel
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear una lista de varios niveles y aplicar formato personalizado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/multilevel-list-formatting/
---

En este tutorial, le mostraremos cómo usar la función de formato de lista multinivel con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Dar formato a la lista multinivel

Ahora aplicaremos el formato de lista multinivel utilizando los métodos disponibles en el objeto DocumentBuilder. Así es cómo:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Ejemplo de código fuente para el formato de lista multinivel usando Aspose.Words para .NET

Aquí está el código fuente completo para la función de formato de lista multinivel con Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Con este código podrá crear una lista de varios niveles y aplicar el formato adecuado a cada nivel utilizando Aspose.Words para .NET.