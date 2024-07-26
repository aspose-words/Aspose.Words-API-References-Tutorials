---
title: Obtener detalles del grupo de revisión
linktitle: Obtener detalles del grupo de revisión
second_title: API de procesamiento de documentos Aspose.Words
description: Obtenga detalles del grupo de revisión en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-group-details/
---

En esta guía paso a paso, le mostraremos cómo obtener los detalles de un grupo de revisiones en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

## Paso 1: cargar el documento

El primer paso es subir el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: buscar revisiones

continuación, recorreremos las revisiones presentes en el documento y mostraremos sus detalles, como tipo, autor, fecha y texto revisado.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Código fuente de ejemplo para obtener detalles del grupo de revisión usando Aspose.Words para .NET

Aquí está el código fuente completo para obtener los detalles de un grupo de revisiones en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los detalles de un grupo de revisiones en un documento de Word usando Aspose.Words para .NET. Al utilizar un bucle y las propiedades apropiadas, pudimos mostrar detalles como el tipo de revisión, el autor, la fecha y el texto revisado. Aspose.Words para .NET ofrece muchas funciones potentes para manipular documentos de Word, incluida la gestión de revisiones. Ahora puede utilizar este conocimiento para obtener detalles del grupo de revisión en sus propios documentos de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo cargo un documento con revisiones en Aspose.Words para .NET?

 R: Utilice el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo que contiene revisiones. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo obtengo los detalles de un grupo de revisión en Aspose.Words para .NET?

R: Revise las revisiones del documento mediante un bucle y acceda a las propiedades de cada revisión para obtener los detalles que desea. Puedes usar el`RevisionType`, `Author`, `DateTime`y`ParentNode` propiedades para obtener el tipo de revisión, autor, fecha y texto revisado respectivamente.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### P: ¿Cómo comprobar si una revisión pertenece a un grupo en Aspose.Words para .NET?

 R: Utilice el`Group` propiedad de la`Revision` Objeto para comprobar si una revisión pertenece a un grupo. Si el`Group` la propiedad es`null`, significa que la revisión no pertenece a ningún grupo.

```csharp
if (revision.Group != null)
{
      // La revisión pertenece a un grupo.
}
else
{
      // La revisión no pertenece a ningún grupo.
}
```