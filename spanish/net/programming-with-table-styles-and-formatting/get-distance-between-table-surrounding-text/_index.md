---
title: Obtener la distancia entre el texto que rodea la tabla
linktitle: Obtener la distancia entre el texto que rodea la tabla
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para obtener la distancia entre el texto y una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para obtener la distancia entre el texto circundante en una tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo acceder a las distintas distancias entre una tabla y el texto que la rodea en sus documentos de Word utilizando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se encuentra su documento de Word. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento existente
 A continuación, debe cargar el documento de Word existente en una instancia del`Document` clase.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 3: obtenga la distancia entre la tabla y el texto circundante
 Para obtener la distancia entre la tabla y el texto que la rodea, necesitamos acceder a la tabla en el documento usando el`GetChild()` método y el`NodeType.Table` propiedad. Luego podemos mostrar las diferentes distancias usando las propiedades de la matriz`DistanceTop`, `DistanceBottom`, `DistanceRight` y`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Ejemplo de código fuente para obtener la distancia entre el texto que rodea la tabla usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusión
En este tutorial, aprendimos cómo obtener la distancia entre el texto circundante en una tabla usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede acceder fácilmente a las distintas distancias entre una tabla y el texto que la rodea en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede analizar el diseño de sus tablas en relación con el texto y satisfacer necesidades específicas.