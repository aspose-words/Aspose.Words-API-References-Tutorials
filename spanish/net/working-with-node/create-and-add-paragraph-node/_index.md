---
title: Crear y agregar nodo de párrafo
linktitle: Crear y agregar nodo de párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Cree y agregue un nodo de párrafo a sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-node/create-and-add-paragraph-node/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo crear y agregar un nodo de párrafo usando Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
```

## Paso 2: Crear un nuevo documento
 En este paso, crearemos un nuevo documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: crea un nodo de párrafo
 Ahora crearemos un nodo de párrafo usando el`Paragraph` class y pasando el documento como parámetro.

```csharp
Paragraph para = new Paragraph(doc);
```

## Paso 4: Accede a la sección de documentos
 Para agregar el párrafo al documento, necesitamos acceder a la última sección del documento usando el`LastSection` propiedad.

```csharp
Section section = doc.LastSection;
```

## Paso 5: agregue el nodo de párrafo al documento
 Ahora que tenemos la sección del documento, podemos agregar el nodo de párrafo a la sección usando el`AppendChild` método en la sección`Body` propiedad.

```csharp
section.Body.AppendChild(para);
```

## Paso 6: Guarde el documento
 Finalmente, para guardar el documento, puede utilizar el`Save` especificando el formato de salida deseado, como el formato DOCX.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Ejemplo de código fuente para crear y agregar un nodo de párrafo con Aspose.Words para .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

Este es un ejemplo de código completo para crear y agregar un nodo de párrafo usando Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.