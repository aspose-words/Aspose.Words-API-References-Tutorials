---
title: Aplicar borde de contorno
linktitle: Aplicar borde de contorno
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para aplicar un borde de contorno a una tabla usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para aplicar un borde de contorno a una tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, comprenderá claramente cómo manipular los bordes de las tablas en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se almacena su documento de Word. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Sube el documento
 A continuación, debe cargar el documento de Word en una instancia del`Document` clase.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 3: Accede a la tabla
 Para aplicar un borde de contorno, necesitamos acceder a la tabla en el documento. El`Table` class representa una tabla en Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Paso 4: Alinee la tabla al centro de la página
 Ahora podemos alinear la tabla al centro de la página usando el`Alignment` propiedad de la tabla.

```csharp
table. Alignment = Table Alignment. Center;
```

## Paso 5: borre los bordes de la tabla existente
Para comenzar con un nuevo borde de contorno, primero debemos borrar todos los bordes existentes de la tabla. Esto se puede hacer usando el`ClearBorders()` método.

```csharp
table. ClearBorders();
```

## Paso 6: Defina un borde verde alrededor de la mesa
 Ahora podemos establecer un borde verde alrededor de la mesa usando el`SetBorder()` método para cada lado de la mesa. En este ejemplo, estamos utilizando un borde de tipo "Único" con un grosor de 1,5 puntos y un color verde.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Paso 7: Rellena las celdas con un color de fondo
Para mejorar la presentación visual de la tabla, podemos rellenar las celdas con un color de fondo de fondo

idea. En este ejemplo, estamos usando un color verde claro.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Paso 8: Guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

¡Felicidades! Ahora ha aplicado un borde de contorno a una tabla usando Aspose.Words para .NET.

### Ejemplo de código fuente para Aplicar contorno de borde usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Alinee la tabla al centro de la página.
	table.Alignment = TableAlignment.Center;
	//Borre cualquier borde existente de la tabla.
	table.ClearBorders();
	// Coloca un borde verde alrededor de la mesa pero no adentro.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Rellene las celdas con un color sólido verde claro.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusión
En este tutorial, aprendimos cómo aplicar un borde de contorno a una tabla usando Aspose.Words para .NET. Al seguir esta guía paso a paso, puede integrar fácilmente esta funcionalidad en sus proyectos de C#. La manipulación del formato de tablas es un aspecto esencial del procesamiento de documentos y Aspose.Words ofrece una API potente y flexible para lograrlo. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y cumplir requisitos específicos.