---
title: Tabla dividida
linktitle: Tabla dividida
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a dividir una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/split-table/
---

En este tutorial, vamos a aprender cómo dividir una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá dividir una tabla de una determinada fila en sus documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento
Para iniciar el procesamiento de textos con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "Tables.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: Dividir la mesa
A continuación, dividiremos la tabla de una determinada fila. Usa el siguiente código:

```csharp
// Recuperar la primera tabla
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Determinación de la línea a partir de la cual dividir la tabla
Row row = firstTable.Rows[2];

// Crear un nuevo contenedor para la tabla dividida
Table table = (Table)firstTable.Clone(false);

// Inserte el contenedor después de la mesa original
firstTable.ParentNode.InsertAfter(table, firstTable);

// Agregue un párrafo de búfer para mantener una distancia entre las tablas
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Mover filas de la tabla original a la tabla dividida
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Aquí usamos el documento para recuperar la primera tabla del nodo del documento. Luego determinamos la fila de la que queremos dividir la tabla, en este ejemplo es la tercera fila (índice 2). Luego creamos un nuevo contenedor clonando la tabla original y luego lo insertamos después de la tabla original. También agregamos un párrafo de búfer para mantener una distancia entre las dos tablas. Luego, movemos las filas de la tabla original a la tabla dividida mediante un bucle do-while hasta llegar a la fila especificada.

## Paso 4: Guardar el documento modificado
Finalmente, tenemos que guardar el

  documento modificado con la tabla dividida. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para Split Table usando Aspose.Words para .NET 

```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Dividiremos la tabla en la tercera fila (inclusive).
Row row = firstTable.Rows[2];
// Cree un nuevo contenedor para la tabla dividida.
Table table = (Table) firstTable.Clone(false);
// Inserte el contenedor después del original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Agregue un párrafo intermedio para asegurarse de que las tablas se mantengan separadas.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusión
En este tutorial, aprendimos a dividir una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# proporcionado, puede dividir fácilmente las tablas de una determinada línea en sus documentos de Word.