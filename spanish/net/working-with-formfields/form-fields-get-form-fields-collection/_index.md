---
title: Campos de formulario Obtener colección de campos de formulario
linktitle: Campos de formulario Obtener colección de campos de formulario
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recuperar y manipular la colección de campos de formulario en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-formfields/form-fields-get-form-fields-collection/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para recuperar la colección de campos de formulario de un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento de origen que contiene campos de formulario:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Paso 2: Recuperar la colección de campos de formulario

 A continuación, acceda a la`FormFields` propiedad de la`Range` objeto en el documento para recuperar la colección de campos de formulario:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Ahora, tiene la colección de campos de formulario del documento de Word almacenados en el`formFields` variable.

## Paso 3: Acceso y manipulación de los campos del formulario

Puede iterar a través de la colección de campos de formulario y realizar varias operaciones en cada campo de formulario, como obtener o establecer valores, modificar el formato o extraer información.

```csharp
foreach (FormField formField in formFields)
{
    // Acceda y manipule cada campo del formulario
    // ...
}
```

## Paso 4: Guardar el documento

Finalmente, guarde el documento modificado si es necesario:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

¡Eso es todo! Ha recuperado con éxito la colección de campos de formulario de un documento de Word utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para campos de formulario Obtenga la colección de campos de formulario usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Acceda y manipule los campos del formulario según sea necesario
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.