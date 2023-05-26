---
title: Limpiar estilos y listas no utilizados
linktitle: Limpiar estilos y listas no utilizados
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para limpiar estilos y listas no utilizados en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

En este tutorial, lo guiaremos a través del código fuente de C# para limpiar estilos y listas no utilizados con Aspose.Words para .NET. Esta función le permite eliminar estilos y listas que no se utilizan en un documento.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso, cargaremos el documento de Word que contiene los estilos y listas no utilizados que queremos limpiar. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Cuente estilos y listas antes de limpiar

Antes de limpiar, contaremos el número de estilos y listas presentes en el documento. Utilice el siguiente código para mostrar los contadores:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Estas instrucciones muestran la cantidad de estilos y listas presentes en el documento antes de limpiarlo.

## Paso 4: Limpie estilos y listas no utilizados

Ahora vamos a limpiar estilos y listas no utilizados del documento. Use el siguiente código para realizar la limpieza:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Este código limpia estilos y listas no utilizados del documento utilizando las opciones especificadas. En este ejemplo, habilitamos el`UnusedStyles` opción para eliminar estilos no utilizados y deshabilitar la`UnusedLists` opción de mantener las listas aunque no se utilicen.

## Paso 5: Contar estilos y listas después de la limpieza

Después de realizar la limpieza, volveremos a contar los estilos y las listas para comprobar si se han colapsado. Utilice el siguiente código para mostrar los nuevos contadores:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Estas instrucciones muestran la cantidad de estilos y listas que quedan después de la limpieza.

### Ejemplo de código fuente para limpiar estilos y listas no utilizados usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Combinado con los estilos incorporados, el documento ahora tiene ocho estilos.
	// Un estilo personalizado se marca como "usado" mientras haya texto en el documento
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

Ahora ha aprendido a limpiar estilos y listas no utilizados de un documento mediante Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede aplicar fácilmente esta característica a sus propios documentos.

