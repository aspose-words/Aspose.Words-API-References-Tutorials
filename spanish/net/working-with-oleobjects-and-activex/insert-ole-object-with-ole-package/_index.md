---
title: Insertar objeto Ole en Word con paquete Ole
linktitle: Insertar objeto Ole en Word con paquete Ole
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un objeto OLE con un paquete OLE en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo insertar un objeto OLE en Word con un paquete OLE usando Aspose.Words para .NET.

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

## Paso 3: Inserte un objeto OLE con un paquete OLE
 Utilice el generador de documentos`InsertOleObject`método para insertar un objeto OLE con un paquete OLE en el documento. Especifique el flujo de datos, el tipo de objeto, las opciones de visualización y otras configuraciones necesarias.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Paso 4: Guarde el documento
 Usa el documento`Save` para guardar el documento en un archivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Ejemplo de código fuente para insertar un objeto OLE con un paquete OLE con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Este es un ejemplo de código completo para insertar un objeto OLE con un paquete OLE con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.

## Conclusión

En conclusión, hemos repasado una guía paso a paso para insertar un objeto OLE en un documento de Word con un paquete OLE utilizando Aspose.Words para .NET.

Siguiendo estos pasos, podrá insertar con éxito objetos OLE con paquetes OLE en sus documentos de Word usando Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga las instrucciones cuidadosamente para obtener los resultados deseados.

### Preguntas frecuentes para insertar un objeto ole en Word con un paquete ole

#### P: ¿Qué credenciales necesito importar para usar Aspose.Words para .NET?

R: Para usar Aspose.Words para .NET, debe importar las siguientes referencias:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### P: ¿Cómo crear un nuevo documento y un generador de documentos?

 R: Puede crear un nuevo documento usando el`Document` clase y un generador de documentos usando el`DocumentBuilder` clase, como se muestra a continuación:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: ¿Cómo insertar un objeto OLE con un paquete OLE en el documento?

 R: Usa el`InsertOleObject` método del generador de documentos (`DocumentBuilder`) para insertar un objeto OLE con un paquete OLE en el documento. Especifique el flujo de datos, el tipo de objeto, las opciones de visualización y otras configuraciones necesarias. Aquí hay un ejemplo :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### P: ¿Cómo guardar el documento?

 R: Usa el documento`Save`para guardar el documento en un archivo. Aquí hay un ejemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### P: ¿Puede proporcionar un ejemplo completo de cómo insertar un objeto OLE con un paquete OLE con Aspose.Words para .NET?

R: Aquí hay un código de muestra completo para insertar un objeto OLE con un paquete OLE usando Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Esto concluye nuestro tutorial sobre cómo insertar un objeto OLE con un paquete OLE en un documento de Word utilizando Aspose.Words para .NET. Siéntase libre de importar las referencias necesarias y siga los pasos descritos para integrar este código en su proyecto. Si tiene más preguntas, no dude en ponerse en contacto con nosotros.