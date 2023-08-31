---
title: Tabla dividida
linktitle: Tabla dividida
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a dividir una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/split-table/
---

En este tutorial, aprenderemos cómo dividir una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá dividir una tabla de una fila determinada en sus documentos de Word.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento
Para iniciar el procesamiento de textos con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Tables.docx");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos y proporcione el nombre de archivo correcto.

## Paso 3: dividir la mesa
A continuación dividiremos la tabla de una fila determinada. Utilice el siguiente código:

```csharp
// Recuperar la primera tabla
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Determinación de la línea por la que dividir la mesa.
Row row = firstTable.Rows[2];

// Crear un nuevo contenedor para la tabla dividida
Table table = (Table)firstTable.Clone(false);

// Inserte el contenedor después de la tabla original.
firstTable.ParentNode.InsertAfter(table, firstTable);

// Agregue un párrafo de zona de influencia para mantener una distancia entre las tablas
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Mover filas de la tabla original a la tabla dividida
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Aquí usamos el documento para recuperar la primera tabla del nodo del documento. Luego determinamos la fila de la cual queremos dividir la tabla, en este ejemplo es la tercera fila (índice 2). Luego creamos un nuevo contenedor clonando la tabla original y luego lo insertamos después de la tabla original. También agregamos un párrafo de zona de influencia para mantener una distancia entre las dos tablas. Luego movemos filas de la tabla original a la tabla dividida usando un bucle do- while hasta llegar a la fila especificada.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos salvar el

  documento modificado con la tabla dividida. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para Split Table usando Aspose.Words para .NET 

```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Dividiremos la mesa en la tercera fila (inclusive).
Row row = firstTable.Rows[2];
// Cree un nuevo contenedor para la tabla dividida.
Table table = (Table) firstTable.Clone(false);
// Inserte el contenedor después del original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Agregue un párrafo de zona de influencia para garantizar que las tablas permanezcan separadas.
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
En este tutorial, aprendimos cómo dividir una tabla en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede dividir fácilmente tablas de una determinada línea en sus documentos de Word.