---
title: Insertar objeto antiguo en documento de Word
linktitle: Insertar objeto antiguo en documento de Word
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un objeto OLE en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo insertar un objeto OLE en un documento de Word usando Aspose.Words para .NET.

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

## Paso 3: Insertar un objeto OLE
 Utilice el Creador de documentos`InsertOleObject`para insertar un objeto OLE en el documento. Especifique la URL del objeto OLE, el tipo de objeto, las opciones de visualización y otras configuraciones necesarias.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", verdadero, verdadero, nulo);
```

## Paso 4: Guarde el documento
 Usa el documento`Save` para guardar el documento en un archivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Ejemplo de código fuente para insertar un objeto OLE con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", verdadero, verdadero, nulo);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Este es un ejemplo de código completo para insertar un objeto OLE con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.

## Conclusión

En conclusión, la inserción de objetos OLE en un documento de Word es una característica poderosa que ofrece Aspose.Words para .NET. Con esta biblioteca, puede incrustar fácilmente objetos OLE, como archivos HTML, hojas de cálculo de Excel, presentaciones de PowerPoint, etc., en sus documentos de Word.

En este artículo, hemos repasado una guía paso a paso para explicar el código fuente en C# que ilustra cómo insertar un objeto OLE en un documento de Word. Cubrimos las referencias necesarias, la creación de un nuevo documento y un generador de documentos, y los pasos para insertar un objeto OLE y guardar el documento.

### Preguntas frecuentes para insertar un objeto OLE en un documento de Word

#### P: ¿Qué credenciales necesito importar para usar Aspose.Words para .NET?

R: Para usar Aspose.Words para .NET, debe importar las siguientes referencias:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P: ¿Cómo crear un nuevo documento y un generador de documentos?

 R: Puede crear un nuevo documento usando el`Document` clase y un generador de documentos usando el`DocumentBuilder` clase, como se muestra a continuación:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: ¿Cómo insertar un objeto OLE en el documento?

 R: Usa el`InsertOleObject` método del generador de documentos (`DocumentBuilder`) para insertar un objeto OLE en el documento. Especifique la URL del objeto OLE, el tipo de objeto, las opciones de visualización y otras configuraciones necesarias. Aquí hay un ejemplo :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", verdadero, verdadero, nulo);
```

#### P: ¿Cómo guardar el documento?

 R: Usa el documento`Save`para guardar el documento en un archivo. Aquí hay un ejemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### P: ¿Puede proporcionar un ejemplo completo de cómo insertar un objeto OLE con Aspose.Words para .NET?

R: Aquí hay un código de muestra completo para insertar un objeto OLE con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", verdadero, verdadero, nulo);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
