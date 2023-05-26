---
title: Insertar objeto ole como icono usando Stream
linktitle: Insertar objeto ole como icono usando Stream
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un objeto OLE como un icono usando una secuencia con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo insertar un objeto OLE como un ícono usando una secuencia con Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Paso 2: Crear un nuevo documento y generador de documentos
 En este paso, crearemos un nuevo documento usando el`Document` clase y un generador de documentos usando el`DocumentBuilder` clase.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte un objeto OLE como un icono de una secuencia
 Utilice el Creador de documentos`InsertOleObjectAsIcon` método para insertar un objeto OLE como un icono de una secuencia en el documento. Especifique el flujo de datos, el tipo de objeto, la ruta del icono y el nombre del objeto incrustado.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Paso 4: Guarde el documento
 Usa el documento`Save` para guardar el documento en un archivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Código fuente de ejemplo para insertar un objeto OLE como un icono utilizando una secuencia con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Este es un ejemplo de código completo para insertar un objeto OLE como un icono utilizando una secuencia con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.