---
title: Obtener grupos de revisión
linktitle: Obtener grupos de revisión
second_title: API de procesamiento de documentos Aspose.Words
description: Obtenga grupos de revisión en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-groups/
---

En esta guía paso a paso, le diremos cómo obtener los grupos de revisión en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

## Paso 1: cargar el documento

El primer paso es subir el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: Examinar grupos de revisión

continuación, recorreremos los grupos de revisión presentes en el documento y mostraremos sus detalles, como autor, tipo de revisión y texto revisado.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Código fuente de ejemplo para obtener grupos de revisión usando Aspose.Words para .NET

Aquí está el código fuente completo para obtener los grupos de revisión en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los grupos de revisión en un documento de Word usando Aspose.Words para .NET. Seguimos los pasos para cargar el documento y explorar los grupos de revisión, mostrando detalles como el autor y el tipo de revisión. Ahora puede aplicar este conocimiento para analizar revisiones de su propio documento de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Utilice el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo explorar grupos de revisión en un documento en Aspose.Words para .NET?

 R: Utilice el`Groups` propiedad del documento`Revisions`objeto para obtener la colección de grupos de revisión. Luego puede utilizar un bucle para recorrer cada grupo de revisión.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Procese cada grupo de revisión aquí
}
```

#### P: ¿Cómo obtener el autor de un grupo de revisión en Aspose.Words para .NET?

 R: Utilice el`Author` propiedad de la`RevisionGroup` objeto de obtener el autor del grupo de revisión.

```csharp
string author = group.Author;
```

#### P: ¿Cómo obtener el tipo de revisión de un grupo de revisión en Aspose.Words para .NET?

 R: Utilice el`RevisionType` propiedad de la`RevisionGroup` Objeto para obtener el tipo de revisión del grupo.

```csharp
string revisionType = group.RevisionType;
```