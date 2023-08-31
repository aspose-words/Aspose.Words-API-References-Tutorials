---
title: Insertar campo Incluir texto sin Generador de documentos
linktitle: Insertar FieldIncludeText sin el Generador de documentos
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un campo FieldIncludeText en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la funcionalidad "Insertar un campo FieldIncludeText" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creando el Documento y el Párrafo

Comenzamos creando un nuevo documento e inicializando un párrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Paso 3: Insertar el campo FieldIncludeText

 usamos el`AppendField()` para insertar un campo FieldIncludeText en el párrafo.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Luego configuramos las propiedades del campo FieldIncludeText especificando el nombre del marcador y el nombre del archivo fuente.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

A continuación, añadimos el párrafo al cuerpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
fieldIncludeText.Update();
```

### Ejemplo del código fuente para insertar un campo FieldIncludeText con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el párrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insertar campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un párrafo, insertamos un FieldIncludeTexten especificando el nombre del marcador y el nombre del archivo de origen, y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Insertar un campo incluido en el texto" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo puedo especificar el archivo de origen para el campo de inclusión de texto en Aspose.Words para .NET?

 R: Para especificar el archivo fuente para el campo de inclusión de texto en Aspose.Words para .NET, puede usar el`FieldIncludeText.SourceFullName`propiedad para establecer la ruta completa del archivo de origen. Asegúrese de que se pueda acceder al archivo de origen y que contenga el contenido que desea incluir en el campo de inclusión de texto.

#### P: ¿Puedo incluir texto de una macro en el campo de inclusión de texto con Aspose.Words para .NET?

 R: Sí, puede incluir texto de una macro en el campo de inclusión de texto con Aspose.Words para .NET. Puedes usar el`FieldIncludeText.IncludeText` propiedad para especificar el nombre de la macro cuyo contenido debe incluirse en el campo.

#### P: ¿La inserción de un campo de inclusión de texto sin el generador de documentos afecta la estructura del documento de Word con Aspose.Words para .NET?

R: Insertar un campo de inclusión de texto sin el generador de documentos no afecta directamente la estructura del documento de Word. Sin embargo, agrega un nuevo elemento de campo al contenido del documento. Puede manipular la estructura del documento agregando, eliminando o modificando los elementos existentes según sus necesidades.

#### P: ¿Puedo personalizar la apariencia del campo de inclusión de texto en un documento de Word con Aspose.Words para .NET?

R: El campo de inclusión de texto no personaliza directamente su apariencia en un documento de Word. Sin embargo, puede dar formato al texto incluido utilizando las propiedades de párrafo, las propiedades de fuente y otros objetos de formato disponibles en Aspose.Words para .NET.