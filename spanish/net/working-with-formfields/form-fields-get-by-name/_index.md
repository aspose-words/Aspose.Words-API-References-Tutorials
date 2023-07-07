---
title: Campos de formulario Obtener por nombre
linktitle: Campos de formulario Obtener por nombre
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recuperar y modificar campos de formulario por nombre en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-formfields/form-fields-get-by-name/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para recuperar campos de formulario por nombre de un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento de origen que contiene campos de formulario:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Paso 2: Recuperar campos de formulario

 A continuación, acceda a la`FormFields` propiedad de la`Range` objeto en el documento para recuperar todos los campos del formulario:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Puede recuperar campos de formulario por índice o por nombre. En este ejemplo, recuperamos un campo de formulario usando ambos métodos:

```csharp
FormField formField1 = documentFormFields[3]; //Recuperando por índice
FormField formField2 = documentFormFields["Text2"]; // Recuperando por nombre
```

## Paso 3: modificación de las propiedades de los campos de formulario

 Una vez que haya recuperado los campos del formulario, puede modificar sus propiedades según sea necesario. En este ejemplo, cambiamos el tamaño de fuente de`formField1` a 20 y el color de fuente de`formField2` a rojo:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Paso 4: Guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

¡Eso es todo! Recuperó correctamente los campos de formulario por nombre y modificó sus propiedades en un documento de Word utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Campos de formulario Obtener por nombre usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cómo puedo obtener un campo de formulario por nombre en Aspose.Words?

 R: Para obtener un campo de formulario por nombre en Aspose.Words, puede usar el`Document.Range.FormFields[name]` método. Este método devuelve el campo de formulario correspondiente al nombre especificado.

#### P: ¿Qué sucede si el campo de formulario con el nombre especificado no existe en el documento?

 R: Si el campo de formulario con el nombre especificado no existe en el documento, el`Document.Range.FormFields[name]` el método regresará`null`Puede verificar este resultado para manejar los casos en los que no se encuentra el campo de formulario.

#### P: ¿Cómo puedo modificar las propiedades de un campo de formulario encontrado?

R: Una vez que obtiene un campo de formulario por nombre, puede acceder a sus propiedades individuales para editarlas. Por ejemplo, puede cambiar el valor del campo, habilitar o deshabilitar su visibilidad o modificar otras propiedades según sea necesario.

#### P: ¿Puedo obtener varios campos de formulario con el mismo nombre en un documento?

 R: Sí, es posible tener varios campos de formulario con el mismo nombre en un documento. En este caso, el`Document.Range.FormFields[name]` devolverá el primer campo de formulario encontrado con el nombre especificado. Si tiene varios campos de formulario con el mismo nombre, deberá tener esto en cuenta al manipular los campos.

#### P: ¿Cómo puedo iterar sobre todos los campos de formulario en un documento?

 R: Para iterar sobre todos los campos de formulario en un documento, puede usar un`foreach` bucle en el`Document.Range.FormFields` recopilación. Esto le permitirá acceder a cada campo del formulario de forma individual y realizar operaciones en cada uno de ellos.