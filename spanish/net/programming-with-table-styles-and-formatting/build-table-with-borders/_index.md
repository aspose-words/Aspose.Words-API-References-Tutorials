---
title: Construir mesa con bordes
linktitle: Construir mesa con bordes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para construir una tabla con bordes usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para crear una tabla con bordes usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo crear una tabla con bordes personalizados en sus documentos de Word utilizando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se almacena su documento de Word. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento existente
 A continuación, debe cargar el documento de Word existente en una instancia del`Document` clase.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 3: acceda a la tabla y elimine los bordes existentes
 Para comenzar a construir la tabla con bordes, debemos navegar hasta la tabla en el documento y eliminar los bordes existentes. El`ClearBorders()` El método elimina todos los bordes de la tabla.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Paso 4: establecer los bordes de la tabla
 Ahora podemos establecer los bordes de la tabla usando el`SetBorders()` método. En este ejemplo, estamos utilizando un borde de color verde con un grosor de 1,5 puntos.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## Paso 5: Guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

¡Felicidades! Ahora ha creado una tabla con bordes personalizados utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Build Table With Borders usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Borre cualquier borde existente de la tabla.
	table.ClearBorders();
	// Establece un borde verde alrededor y dentro de la mesa.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Conclusión
En este tutorial, aprendimos cómo construir una tabla con bordes usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede personalizar fácilmente los bordes de su tabla en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y satisfacer necesidades específicas.