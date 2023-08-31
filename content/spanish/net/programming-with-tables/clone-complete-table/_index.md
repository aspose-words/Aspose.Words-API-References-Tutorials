---
title: Clonar tabla completa
linktitle: Clonar tabla completa
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a clonar una tabla completa en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/clone-complete-table/
---

En este tutorial, aprenderemos cómo usar Aspose.Words para .NET para clonar una tabla completa en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá clonar tablas en sus documentos de Word mediante programación.

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

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: clonación de matriz completa
A continuación, clonaremos toda la tabla y la insertaremos en el documento después del original. Utilice el siguiente código:

```csharp
// Clonar la matriz
Table tableClone = (Table)table.Clone(true);

// Inserte la tabla clonada en el documento después del original.
table.ParentNode.InsertAfter(tableClone, table);

// Insertar un párrafo vacío entre las dos tablas.
// De lo contrario, se combinarán en uno al guardar (esto se debe a la validación del documento)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Aquí estamos usando el`Clone` método para crear una copia completa de la matriz. Entonces usamos`InsertAfter` para insertar la tabla clonada en el documento, después de la tabla original. También agregamos un párrafo vacío entre las dos tablas para evitar que se fusionen al guardar.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la tabla clonada. Utilice el siguiente código:

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.
  
### Código fuente de muestra para Clonar tabla completa usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Clona la tabla e insértala en el documento después del original.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Inserte un párrafo vacío entre las dos tablas,
	// o sino se combinarán en uno solo al guardar esto tiene que ver con la validación del documento.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusión
En este tutorial, aprendimos cómo clonar una tabla completa en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede clonar tablas en sus documentos de Word mediante programación. Esta característica le permite realizar manipulaciones avanzadas en matrices para satisfacer sus necesidades específicas.