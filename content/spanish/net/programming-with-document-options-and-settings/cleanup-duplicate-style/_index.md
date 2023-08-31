---
title: Limpieza de estilo duplicado
linktitle: Limpieza de estilo duplicado
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para limpiar estilos duplicados en un documento usando Aspose.Words para .NET. Código fuente completo incluido.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

En este tutorial, lo guiaremos paso a paso el código fuente de C# para limpiar estilos duplicados con Aspose.Words para .NET. Esta función ayuda a eliminar estilos duplicados de un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word que queremos limpiar. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Cuente los estilos antes de limpiar

Antes de proceder con la limpieza, contaremos el número de estilos presentes en el documento. Utilice el siguiente código para mostrar el recuento de estilos:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Esta declaración muestra la cantidad de estilos presentes en el documento.

## Paso 4: Limpiar estilos duplicados

Ahora limpiemos los estilos duplicados del documento. Utilice el siguiente código para realizar la limpieza:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Este código limpia estilos duplicados del documento utilizando las opciones especificadas. En este ejemplo, habilitamos el`DuplicateStyle` Opción para limpiar estilos duplicados.

## Paso 5: Cuente los estilos después de la limpieza

Después de hacer la limpieza, volveremos a contar el número de estilos para comprobar si ha disminuido. Utilice el siguiente código para mostrar el recuento de nuevos estilos:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Esta declaración muestra la cantidad de estilos que quedan después de la limpieza.

### Código fuente de ejemplo para limpieza de estilos duplicados usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Recuento de estilos antes de la limpieza.
	Console.WriteLine(doc.Styles.Count);

	// Limpia estilos duplicados del documento.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Se redujo el recuento de estilos después de la limpieza.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```