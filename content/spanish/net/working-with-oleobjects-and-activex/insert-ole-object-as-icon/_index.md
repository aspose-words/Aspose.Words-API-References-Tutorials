---
title: Insertar objeto antiguo en documento de Word como icono
linktitle: Insertar objeto antiguo en documento de Word como icono
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un objeto OLE en un documento de Word como icono con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo insertar un objeto OLE en un documento de Word como icono usando Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Paso 2: Crear un nuevo documento y generador de documentos
 En este paso, crearemos un nuevo documento usando el`Document` clase y un generador de documentos usando el`DocumentBuilder` clase.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte un objeto OLE como un icono
 Utilice el Creador de documentos`InsertOleObjectAsIcon` método para insertar un objeto OLE como un icono en el documento. Especifique la ruta del archivo OLE, el indicador de visualización, la ruta del icono y el nombre del objeto incrustado.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Paso 4: Guarde el documento
 Usa el documento`Save` para guardar el documento en un archivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Ejemplo de código fuente para insertar un objeto OLE como icono con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Este es un ejemplo de código completo para insertar un objeto OLE como un icono con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.

## Conclusión

En conclusión, exploramos una guía paso a paso para insertar un objeto OLE como icono en un documento de Word utilizando Aspose.Words para .NET.

Siguiendo estos pasos, podrá insertar con éxito un objeto OLE como un icono en sus documentos de Word usando Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga las instrucciones cuidadosamente para obtener los resultados deseados.

### Preguntas frecuentes para insertar un objeto ole en un documento de Word como icono

#### P. ¿Qué referencias se necesitan para insertar un objeto OLE como icono en un documento de Word utilizando Aspose.Words para .NET?

R: Debe importar las siguientes referencias a su proyecto para usar Aspose.Words para .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P. ¿Cómo crear un nuevo documento y un generador de documentos en Aspose.Words para .NET?

 R: Puede crear un nuevo documento usando el`Document` clase y un generador de documentos usando el`DocumentBuilder`clase. Aquí hay un ejemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. ¿Cómo insertar un objeto OLE como icono en el documento?

 R: Utilice el Creador de documentos`InsertOleObjectAsIcon` método para insertar un objeto OLE como un icono. Especifique la ruta del archivo OLE, el indicador de visualización, la ruta del icono y el nombre del objeto incrustado. Aquí hay un ejemplo :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### P. ¿Cómo guardar el documento con el objeto OLE insertado como icono?

 R: Usa el documento`Save`para guardar el documento en un archivo. Aquí hay un ejemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```