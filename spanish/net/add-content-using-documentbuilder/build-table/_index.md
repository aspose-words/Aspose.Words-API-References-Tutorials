---
title: Crear tabla en documento de Word
linktitle: Crear tabla en documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/build-table/
---
En este tutorial paso a paso, aprenderá a crear una tabla en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá crear una tabla con formato y contenido personalizados utilizando la clase DocumentBuilder.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Crear un nuevo documento
Para comenzar, crea un nuevo documento usando la clase Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Inicie la Mesa
continuación, utilice el método StartTable de la clase DocumentBuilder para comenzar a construir la tabla:

```csharp
Table table = builder.StartTable();
```

## Paso 3: Insertar celdas y agregar contenido
Ahora, puede insertar celdas en la tabla y agregarles contenido utilizando los métodos InsertCell y Write de la clase DocumentBuilder. Personaliza el formato de celda según sea necesario:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Paso 4: terminar la fila
Después de agregar contenido a las celdas de la primera fila, use el método EndRow de la clase DocumentBuilder para finalizar la fila:

```csharp
builder.EndRow();
```

## Paso 5: personalizar el formato de fila
Puede personalizar el formato de una fila configurando las propiedades de los objetos RowFormat y CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Paso 6: terminar la mesa
Para completar la tabla, utilice el método EndTable de la clase DocumentBuilder:

```csharp
builder.EndTable();
```

### Código fuente de ejemplo para construir una tabla usando Aspose.Words para .NET
Aquí está el código fuente completo para construir una tabla usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo crear una tabla en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede crear tablas con formato personalizado.

### Preguntas frecuentes sobre la tabla de creación en un documento de Word

#### P: ¿Qué es Aspose.Words para .NET?

R: Aspose.Words para .NET es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, leer, editar y convertir documentos de Microsoft Word mediante programación en aplicaciones .NET. Proporciona una amplia gama de funciones para trabajar con documentos de Word, como manipulación de texto, creación de tablas, protección de documentos, formateo y más.

#### P: ¿Cómo puedo crear una tabla en un documento de Word usando Aspose.Words para .NET?

R: Para crear una tabla en un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto.
2.  Utilizar el`StartTable` metodo de la`DocumentBuilder` clase para empezar a construir la mesa.
3. Inserte celdas en la tabla y agregue contenido usando el`InsertCell` y`Write` métodos de la`DocumentBuilder` clase.
4.  Terminar la fila usando el`EndRow` metodo de la`DocumentBuilder` clase.
5.  Personalice el formato de fila configurando las propiedades del`RowFormat` y`CellFormat` objetos.
6.  Terminar la mesa usando el`EndTable` metodo de la`DocumentBuilder` clase.
7. Guarde el documento.

#### P: ¿Cómo puedo personalizar el formato de la tabla y sus celdas?

 R: Puede personalizar el formato de la tabla y sus celdas configurando varias propiedades del`RowFormat` y`CellFormat` objetos. Por ejemplo, puede ajustar la alineación de las celdas, la orientación del texto vertical y horizontal, la altura de las celdas, la altura de las filas y más. Al usar estas propiedades, puede lograr la apariencia deseada para la tabla y su contenido.

#### P: ¿Puedo crear tablas complejas con celdas combinadas y otras funciones avanzadas?

 R: Sí, Aspose.Words para .NET ofrece funciones avanzadas para crear tablas complejas, incluida la compatibilidad con celdas combinadas, tablas anidadas y diseños de tablas complejos. Puedes usar el`MergeCells` método para fusionar celdas,`StartTable`método para crear tablas anidadas y otros métodos para lograr la estructura de tabla deseada.

#### P: ¿Es Aspose.Words para .NET compatible con diferentes formatos de documentos de Word?

R: Sí, Aspose.Words para .NET es compatible con varios formatos de documentos de Word, incluidos DOC, DOCX, RTF y más. Admite formatos heredados (DOC) y formatos modernos basados en XML (DOCX) y le permite trabajar con documentos en diferentes formatos sin ningún problema.

#### P: ¿Dónde puedo encontrar más información y documentación sobre Aspose.Words para .NET?

 R: Puede encontrar documentación completa y ejemplos de código en[Referencias de API](https://reference.aspose.com/words/net/). La documentación proporcionará información detallada sobre las funciones de la biblioteca y cómo usarlas en sus aplicaciones .NET.