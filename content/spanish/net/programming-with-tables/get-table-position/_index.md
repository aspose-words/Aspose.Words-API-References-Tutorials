---
title: Obtener posición en la mesa
linktitle: Obtener posición en la mesa
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo obtener la posición de una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/get-table-position/
---

En este tutorial, aprenderemos cómo obtener la posición de una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá obtener propiedades de posicionamiento de tablas en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento y acceder a la tabla
Para iniciar el procesamiento de textos con la tabla, debemos cargar el documento que la contiene y acceder a ella. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Tables.docx");

// Acceso a la matriz
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga la tabla cuya posición desea obtener.

## Paso 3: Obtener las propiedades de posicionamiento de la matriz
A continuación, comprobaremos el tipo de posicionamiento de la matriz y obtendremos las propiedades de posicionamiento adecuadas. Utilice el siguiente código:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Aquí usamos una condición para verificar si la matriz es de tipo flotante. Si es así, imprimimos el`RelativeHorizontalAlignment` y`RelativeVerticalAlignment` propiedades para obtener la alineación horizontal y vertical relativa de la tabla. De lo contrario, imprimimos el`Alignment` propiedad para obtener la alineación de la matriz.

### Código fuente de muestra para Obtener posición de tabla usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusión
En este tutorial, aprendimos cómo obtener la posición de una tabla en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede obtener propiedades de posicionamiento de tablas en sus documentos de Word mediante programación. Esta característica le permite analizar y manipular matrices según sus posiciones específicas.