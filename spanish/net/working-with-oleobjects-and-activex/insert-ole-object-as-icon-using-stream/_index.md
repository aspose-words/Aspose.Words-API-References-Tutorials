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

## Conclusión

La guía paso a paso anterior explica cómo insertar un objeto OLE como icono en un documento de Word utilizando un flujo con Aspose.Words para .NET. Siguiendo los pasos descritos, podrá integrar esta funcionalidad en su proyecto. Asegúrese de importar las referencias necesarias, cree un nuevo documento y un generador de documentos, inserte el objeto OLE como un icono de la secuencia y luego guarde el documento. Utilice el código de muestra proporcionado como punto de partida y personalícelo según sus necesidades.

### Preguntas frecuentes

#### P. ¿Cómo importar las referencias necesarias para usar Aspose.Words para .NET?

A. Para importar las referencias necesarias, debe seguir estos pasos:

 Agrega lo siguiente`using` declaraciones en la parte superior de su archivo fuente:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Asegúrese de haber agregado la biblioteca Aspose.Words a su proyecto.

#### P. ¿Cómo crear un nuevo documento y un generador de documentos usando Aspose.Words para .NET?

A. Para crear un nuevo documento y generador de documentos, puede seguir estos pasos:

 Utilizar el`Document` clase para crear un nuevo documento:

```csharp
Document doc = new Document();
```
 Utilizar el`DocumentBuilder` class para crear un generador de documentos asociado con el documento creado anteriormente:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. ¿Cómo insertar un objeto OLE como un ícono de una secuencia usando Aspose.Words para .NET?

A. Para insertar un objeto OLE como un icono de una secuencia, puede seguir estos pasos:

 Utilizar el`InsertOleObjectAsIcon` método del generador de documentos para insertar el objeto OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### P. ¿Cómo guardar el documento en un archivo?

A.  Para guardar el documento en un archivo, puede utilizar el`Save` método del documento que especifica la ruta de destino:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### P. ¿Cómo incrusto el código para insertar un objeto OLE como un icono de una secuencia en mi proyecto?

A. Para incrustar el código para insertar un objeto OLE como un icono de una secuencia en su proyecto, siga estos pasos:
- Importe las referencias necesarias agregando las correspondientes`using` declaraciones.
-  Cree un nuevo documento y un generador de documentos usando el`Document` y`DocumentBuilder` clases
- Utilice el código para insertar el objeto OLE como un icono de una secuencia.
-  Guarde el documento usando el`Save` método con la ruta de destino adecuada.

Al seguir estos pasos, podrá insertar con éxito un objeto OLE como un ícono de una secuencia usando Aspose.Words para .NET. Asegúrese de seguir las instrucciones e importar las referencias necesarias para obtener los resultados deseados.