---
title: Insertar campo de autor
linktitle: Insertar campo de autor
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo AUTOR en sus documentos de Word con Aspose.Words para .NET. Especifique el nombre del autor para personalizar sus documentos.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-author-field/
---


Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función "Insertar un campo de AUTOR" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creando el Documento y el Párrafo

Comenzamos creando un nuevo documento y recuperando el primer párrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Paso 3: Inserte el campo AUTOR

 usamos el`AppendField()` método para insertar un campo AUTOR en el párrafo.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Luego configuramos el campo`AuthorName` propiedad para especificar el nombre del autor.

```csharp
field. AuthorName = "Test1";
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo del código fuente para insertar un campo AUTOR con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo AUTOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo AUTOR, configuramos el nombre del autor y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Insertar campo AUTOR" con Aspose.Words para .NET.
