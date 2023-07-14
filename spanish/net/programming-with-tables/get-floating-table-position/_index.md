---
title: Obtener posición de mesa flotante
linktitle: Obtener posición de mesa flotante
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a obtener la posición de las tablas flotantes en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/get-floating-table-position/
---

En este tutorial, aprenderemos cómo obtener la posición de una tabla flotante en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá obtener las propiedades de posicionamiento de una tabla flotante en sus documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento y acceder a las tablas
Para iniciar el procesamiento de textos con tablas, necesitamos cargar el documento que las contiene y acceder a ellas. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga tablas flotantes.

## Paso 3: obtener las propiedades de posicionamiento de la tabla flotante
A continuación, recorreremos todas las tablas del documento y obtendremos las propiedades de posicionamiento de la tabla flotante. Usa el siguiente código:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Si la matriz es de tipo flotante, imprima sus propiedades de posicionamiento.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Aquí estamos usando un`foreach` bucle para recorrer todas las matrices del documento. Comprobamos si la matriz es de tipo flotante comprobando el`TextWrapping` propiedad. Si es así, imprimimos las propiedades de posicionamiento de la tabla, como el anclaje horizontal, el anclaje vertical, las distancias absolutas horizontal y vertical, el permiso de superposición, la distancia absoluta horizontal y la alineación vertical relativa.
 
### Ejemplo de código fuente para obtener la posición de la tabla flotante mediante Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Si la tabla es de tipo flotante, imprima sus propiedades de posicionamiento.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusión
En este tutorial, aprendimos cómo obtener la posición de una tabla flotante en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede obtener las propiedades de posicionamiento de las tablas flotantes en sus documentos de Word mediante programación. Esta función le permite analizar y manipular tablas flotantes según sus necesidades específicas.