---
title: Obtener posición en la mesa
linktitle: Obtener posición en la mesa
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a obtener la posición de una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/get-table-position/
---

En este tutorial, vamos a aprender cómo obtener la posición de una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá obtener propiedades de posicionamiento de tablas en sus documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento y acceder a la tabla
Para iniciar el procesamiento de textos con la tabla, necesitamos cargar el documento que la contiene y acceder a ella. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "Tables.docx");

// Acceso a la matriz
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga la tabla cuya posición desea obtener.

## Paso 3: obtener las propiedades de posicionamiento de la matriz
A continuación, comprobaremos el tipo de posicionamiento de la matriz y obtendremos las propiedades de posicionamiento adecuadas. Usa el siguiente código:

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

 Aquí usamos una condición para verificar si la matriz es de tipo flotante. Si es así, imprimimos el`RelativeHorizontalAlignment` y`RelativeVerticalAlignment` properties para obtener la alineación horizontal y vertical relativa de la tabla. De lo contrario, imprimimos el`Alignment` propiedad para obtener la alineación de la matriz.

### Ejemplo de código fuente para obtener la posición de la tabla con Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
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
En este tutorial, aprendimos cómo obtener la posición de una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede obtener propiedades de posicionamiento de tablas en sus documentos de Word mediante programación. Esta función le permite analizar y manipular matrices según sus posiciones específicas.