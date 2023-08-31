---
title: Eliminar la tabla de contenido en un documento de Word
linktitle: Eliminar la tabla de contenido en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a eliminar la tabla de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/remove-content/remove-table-of-contents/
---
En este tutorial, lo guiaremos a través de cómo eliminar la tabla de contenido en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La tabla de contenido a veces puede ser redundante o innecesaria, y este código lo ayudará a eliminarla de manera efectiva. Proporcionaremos una guía paso a paso para ayudarlo a comprender e implementar el código en su propio proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto
- Un documento de Word que contiene una tabla de contenido que desea eliminar

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Sube el documento
 A continuación, cargaremos el documento de Word en una instancia del`Document` clase usando el`Load` método.

```csharp
// Cargue el documento
Document doc = new Document(dataDir + "your-document.docx");
```

## Paso 3: Eliminar la tabla de contenido
 Para eliminar la tabla de contenido, recorreremos el tipo TOC (tabla de contenido)`FieldStart` nodos en el documento. Almacenaremos estos nodos para que podamos acceder a ellos rápidamente y crear una lista de nodos para eliminar.

```csharp
// Almacene los nodos FieldStart de los campos TOC en el documento para un acceso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Esta es una lista para almacenar los nodos que se encuentran dentro del TOC especificado. Se eliminarán al final de este método.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Compruebe si existe el índice TOC especificado.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Es más seguro almacenar estos nodos y eliminarlos todos al final.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Cuando nos encontramos con un nodo FieldEnd de tipo FieldTOC,
     //sabemos que estamos al final del TOC actual y nos detenemos aquí.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Ejemplo de código fuente para eliminar la tabla de contenido usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Cargue el documento
Document doc = new Document(dataDir + "your-document.docx");

// Almacene los nodos FieldStart de los campos TOC en el documento para un acceso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Esta es una lista para almacenar los nodos que se encuentran dentro del TOC especificado. Se eliminarán al final de este método.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Asegúrese de que exista la TOC especificada por el índice pasado.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Es más seguro almacenar estos nodos y luego eliminarlos todos a la vez.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Una vez que encontramos un nodo FieldEnd de tipo FieldTOC,
	// sabemos que estamos al final del TOC actual y nos detenemos aquí.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Conclusión
En este tutorial, presentamos una guía paso a paso para eliminar la tabla de contenido de un documento de Word utilizando la biblioteca Aspose.Words para .NET. Siguiendo el código y las instrucciones provistos, puede eliminar fácilmente la tabla de contenido y mejorar el diseño de su documento. Recuerde adaptar la ruta del directorio y los nombres de archivo para satisfacer sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Por qué debo usar Aspose.Words para eliminar la tabla de contenido en un documento de Word?

R: Aspose.Words es una biblioteca de clases poderosa y versátil para manipular documentos de Word en aplicaciones .NET. Al usar Aspose.Words, puede eliminar de manera efectiva la tabla de contenido de sus documentos, lo que puede ser útil si la tabla de contenido es redundante o innecesaria. Esto le permite personalizar el contenido de su documento y mejorar su presentación general.

#### P: ¿Cómo cargo un documento en Aspose.Words para .NET?

R: Para eliminar la tabla de contenido de un documento de Word, primero debe cargar el documento en la memoria mediante el método Load() de Aspose.Words. Aquí hay un código de muestra para cargar un documento desde un directorio específico:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "your-document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su documento.

#### P: ¿Cómo elimino la tabla de contenido de un documento usando Aspose.Words?

 R: Para eliminar la tabla de contenido, debe iterar a través de la`FieldStart` escriba los nodos de la TOC en el documento. Puede almacenar estos nodos para un acceso rápido y crear una lista de nodos para eliminar. Aquí hay un código de muestra:

```csharp
// Almacene los nodos FieldStart de los campos TOC en el documento para un acceso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Esta es una lista para almacenar los nodos que se encuentran dentro del TOC especificado. Se eliminarán al final de este método.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Compruebe si existe el índice de tabla de contenido especificado.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Es más seguro almacenar estos nodos y eliminarlos todos al final.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Cuando nos encontramos con un nodo FieldEnd de tipo FieldTOC,
//sabemos que estamos al final del TOC actual y nos detenemos aquí.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### P: ¿Cómo guardar un documento editado en Aspose.Words para .NET?

R: Después de eliminar la tabla de contenido, debe guardar el documento modificado utilizando el método Save(). Especifique la ruta y el formato del archivo de salida deseado (p. ej., DOCX) para el documento editado. Aquí hay un código de muestra:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```