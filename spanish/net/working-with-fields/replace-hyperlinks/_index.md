---
title: Reemplazar hipervínculos
linktitle: Reemplazar hipervínculos
second_title: API de procesamiento de documentos de Aspose.Words
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

 Este bucle recorre todos los campos del documento en busca de campos de tipo`FieldType.FieldHyperlink` . Una vez que se encuentra un campo de este tipo, comprobamos si es un enlace local comprobando el`SubAddress` propiedad. Si no, reemplazamos la dirección del enlace con`"http://www.aspose.com"` y el resultado con`"Aspose - The .NET & Java Component Editor"`.

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

### Preguntas frecuentes

#### P: ¿Cómo puedo reemplazar hipervínculos en un documento de Word usando Aspose.Words para .NET?

 R: Para reemplazar hipervínculos en un documento de Word usando Aspose.Words para .NET, puede usar el`Document.Range.Replace`método que especifica el texto a buscar y el texto de reemplazo. Asegúrese de utilizar las opciones adecuadas para establecer los parámetros de búsqueda y reemplazo.

#### P: ¿Es posible reemplazar solo ciertos hipervínculos en un documento de Word con Aspose.Words para .NET?

R: Sí, es posible reemplazar solo ciertos hipervínculos en un documento de Word con Aspose.Words para .NET. Puede filtrar los hipervínculos que se reemplazarán utilizando criterios específicos, como la URL del enlace, el texto del enlace o cualquier otra propiedad relevante. Luego puede aplicar el reemplazo solo a los hipervínculos coincidentes.

#### P: ¿Cómo puedo ignorar los hipervínculos en encabezados, pies de página o notas al pie cuando los reemplazo con Aspose.Words para .NET?

R: Para ignorar los hipervínculos en encabezados, pies de página o notas al pie de página al reemplazarlos con Aspose.Words para .NET, puede usar las opciones de búsqueda avanzada y especificar los límites de búsqueda apropiados. Por ejemplo, puede limitar la búsqueda a las secciones principales del documento y excluir encabezados, pies de página o notas al pie.

#### P: ¿Es posible reemplazar hipervínculos con enlaces internos a otras partes del documento?

 R: Sí, es posible reemplazar hipervínculos con enlaces internos a otras partes del documento con Aspose.Words para .NET. Puede usar anclas o identificadores de texto para crear enlaces internos y luego reemplazarlos usando el`Document.Range.Replace` método con las opciones apropiadas.

#### P: ¿Reemplazar los hipervínculos con Aspose.Words para .NET conserva las propiedades de los vínculos, como colores o estilos?

R: Sí, al reemplazar los hipervínculos con Aspose.Words para .NET, se conservan las propiedades de los enlaces, como colores o estilos. Puede especificar las mismas propiedades de formato en el texto de reemplazo para lograr un resultado consistente.