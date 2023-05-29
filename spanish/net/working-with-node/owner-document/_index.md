---
title: Documento de propietario
linktitle: Documento de propietario
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar el documento de propietario en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-node/owner-document/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo usar la funcionalidad de documentos patentados con Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Paso 2: Crear un nuevo documento
 En este paso, crearemos un nuevo documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: crea un nodo con el documento propietario
 Cuando crea un nuevo nodo de cualquier tipo, debe pasar el documento al constructor. En este ejemplo, estamos creando un nuevo nodo de párrafo usando el documento`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Paso 4: verificar el nodo principal y el documento del propietario
 Ahora que hemos creado el nodo de párrafo, podemos verificar si tiene un nodo principal y si el documento propietario es el mismo que`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Paso 5: modificar las propiedades del nodo con los datos del documento
La relación entre un nodo y un documento permite el acceso y modificación de propiedades que hacen referencia a datos específicos del documento, como estilos o listas. En este ejemplo, estamos configurando el nombre del estilo de párrafo como "Título 1".

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Paso 6: Agregue el párrafo al documento
Ahora podemos agregar el nodo de párrafo a la sección principal del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Paso 7: verificar el nodo principal después de agregar
Después de agregar el párrafo al documento, verificamos nuevamente si ahora tiene un nodo principal.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Ejemplo de código fuente para el documento del propietario con Aspose.Words para .NET

```csharp
Document doc = new Document();

// La creación de un nuevo nodo de cualquier tipo requiere que se pase un documento al constructor.
Paragraph para = new Paragraph(doc);

// El nuevo nodo de párrafo aún no tiene un padre.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// Pero el nodo de párrafo conoce su documento.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// El hecho de que un nodo pertenezca siempre a un documento nos permite acceder y modificar
// propiedades que hacen referencia a los datos de todo el documento, como estilos o listas.
para.ParagraphFormat.StyleName = "Heading 1";

// Ahora agregue el párrafo al texto principal de la primera sección.
doc.FirstSection.Body.AppendChild(para);

//El nodo de párrafo ahora es un elemento secundario del nodo Cuerpo.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```



