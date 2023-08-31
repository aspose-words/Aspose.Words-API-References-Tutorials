---
title: Limpiar estilos y listas no utilizados
linktitle: Limpiar estilos y listas no utilizados
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para limpiar estilos y listas no utilizados en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

En este tutorial, lo guiaremos a través del código fuente de C# para limpiar listas y estilos no utilizados con Aspose.Words para .NET. Esta característica le permite eliminar estilos y listas que no se utilizan en un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word que contiene los estilos y listas no utilizados que queremos limpiar. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Cuente estilos y listas antes de limpiar

Antes de limpiar, contaremos la cantidad de estilos y listas presentes en el documento. Utilice el siguiente código para mostrar los contadores:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Estas instrucciones muestran la cantidad de estilos y listas presentes en el documento antes de la limpieza.

## Paso 4: Limpiar estilos y listas no utilizados

Ahora limpiemos los estilos y listas no utilizados del documento. Utilice el siguiente código para realizar la limpieza:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Este código limpia estilos y listas no utilizados del documento utilizando las opciones especificadas. En este ejemplo, habilitamos el`UnusedStyles` opción para eliminar estilos no utilizados y deshabilitó el`UnusedLists` Opción de conservar las listas incluso si no se utilizan.

## Paso 5: Cuente estilos y listas después de la limpieza

Después de realizar la limpieza, volveremos a contar los estilos y las listas para comprobar si se han contraído. Utilice el siguiente código para mostrar los nuevos contadores:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Estas instrucciones muestran la cantidad de estilos y listas que quedan después de la limpieza.

### Código fuente de ejemplo para limpiar estilos y listas no utilizados usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Combinado con los estilos integrados, el documento ahora tiene ocho estilos.
	// Un estilo personalizado se marca como "usado" mientras haya texto dentro del documento.
	// formateado en ese estilo. Esto significa que los 4 estilos que agregamos no se utilizan actualmente.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Limpia estilos y listas no utilizados del documento según las opciones de limpieza dadas.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo limpiar listas y estilos no utilizados de un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, podrá aplicar fácilmente esta función a sus propios documentos.

