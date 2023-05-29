---
title: Enumerar nodos secundarios
linktitle: Enumerar nodos secundarios
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a enumerar nodos secundarios en un párrafo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-node/enumerate-child-nodes/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo enumerar nodos secundarios usando Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Paso 2: Crear un nuevo documento
 En este paso, crearemos un nuevo documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: acceda al párrafo y sus nodos secundarios
 Para enumerar los nodos secundarios de un párrafo, primero debemos acceder al párrafo en sí. Utilizar el`GetChild` método con el`Paragraph` tipo de nodo para obtener el primer párrafo del documento.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

 continuación, recuperamos la colección de nodos secundarios del párrafo usando el`ChildNodes` propiedad.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Paso 4: Examine los nodos secundarios
 Ahora que tenemos la colección de nodos secundarios, podemos recorrerlos usando un`foreach` bucle. Verificamos el tipo de cada nodo secundario y realizamos operaciones específicas según el tipo.

```csharp
foreach (Node child in children)
{
     // Un párrafo puede contener elementos secundarios de diferentes tipos, como líneas, formas y otros.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 En este ejemplo, estamos comprobando si el nodo secundario es del tipo`Run` (por ejemplo, un fragmento de texto). Si es así, convertimos el nodo a`Run` y mostrar el texto usando`run.Text`.

## Código fuente de ejemplo para enumerar nodos secundarios con Aspose.Words para .NET


```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

NodeCollection children = paragraph.ChildNodes;
foreach (Node child in children)
{
	// Un párrafo puede contener elementos secundarios de varios tipos, como corridas, formas y otros.
	if (child.NodeType == NodeType.Run)
	{
		Run run = (Run) child;
		Console.WriteLine(run.Text);
	}
}
```

Este es un ejemplo de código completo para enumerar los nodos secundarios de un párrafo con Aspose.Words para .NET. Asegúrate de importar las referencias.

