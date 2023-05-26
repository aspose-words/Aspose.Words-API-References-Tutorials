---
title: Reemplazar hipervínculos
linktitle: Reemplazar hipervínculos
second_title: Referencia de API de Aspose.Words para .NET
description: Reemplace hipervínculos en documentos de Word usando Aspose.Words para .NET. Instrucciones paso a paso para reemplazar hipervínculos.
type: docs
weight: 10
url: /es/net/working-with-fields/replace-hyperlinks/
---

Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# para reemplazar hipervínculos usando Aspose.Words para la funcionalidad .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio del documento

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Asegúrese de especificar la ruta correcta a su directorio de documentos que contiene el`Hyperlinks.docx` archivo.

## Paso 2: Cargue el documento que contiene los hipervínculos

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Aquí estamos creando una instancia de la`Document` clase del archivo especificado.

## Paso 3: Explore los campos para encontrar hipervínculos

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Algunos hipervínculos pueden ser locales (enlaces a marcadores dentro del documento), los ignoramos.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Este bucle recorre todos los campos del documento en busca de campos de tipo`FieldType.FieldHyperlink` . Una vez que se encuentra un campo de este tipo, comprobamos si es un enlace local comprobando el`SubAddress` propiedad. Si no, reemplazamos la dirección del enlace con`"http://www.aspose.com"` el resultado con`"Aspose - The .NET & Java Component Editor"`.

## Paso 4: Guarde el documento modificado

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Finalmente, guardamos el documento modificado con los hipervínculos reemplazados en un archivo específico.

### Ejemplo de código fuente para reemplazar hipervínculos con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Algunos hipervínculos pueden ser locales (enlaces a marcadores dentro del documento), los ignoramos.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Este es un código fuente de muestra para reemplazar hipervínculos en un documento usando Aspose.Words para .NET.