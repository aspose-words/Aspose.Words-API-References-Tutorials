---
title: Permitir que solo los campos de formulario se protejan en un documento de Word
linktitle: Permitir que solo los campos de formulario se protejan en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar Aspose.Words para .NET para proteger documentos de Word y permitir que solo se editen campos de formulario.
type: docs
weight: 10
url: /es/net/document-protection/allow-only-form-fields-protect/
---
La protección de documentos es una característica esencial cuando se procesan palabras con archivos dentro de su aplicación C#. Con la biblioteca Aspose.Words para .NET, puede proteger fácilmente sus documentos y permitir que solo se editen los campos del formulario. En esta guía paso a paso, le explicaremos cómo utilizar el código fuente de C# para permitir que solo se editen campos de formulario utilizando la función Permitir solo protección de campos de formulario de Aspose.Words para .NET.

## Paso 1: configurar el directorio de documentos

El primer paso es definir el directorio de su documento. Debe especificar la ruta donde desea guardar el documento protegido. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: insertar secciones y texto

A continuación, debe insertar secciones y texto en su documento. Utilice la clase DocumentBuilder proporcionada por Aspose.Words para crear el contenido de su documento. Aquí hay un ejemplo simple:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

En este ejemplo, creamos un nuevo documento en blanco y luego usamos DocumentBuilder para agregar una línea de texto.

## Paso 3: Habilitar la protección de documentos

 La protección de documentos solo funciona cuando la protección de documentos está habilitada. Puede habilitar la protección de documentos usando el`Protect` método de la clase Documento. Así es cómo:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

En este ejemplo, habilitamos la protección de documentos especificando el tipo de protección `

AllowOnlyFormFields` y estableciendo una contraseña.

## Paso 4: Permitir solo campos de formulario

Ahora que la protección de documentos está habilitada, debemos especificar que solo se permite la edición de campos de formulario. Esto garantiza que los usuarios solo puedan editar partes del documento que sean campos de formulario. Así es cómo:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Asegúrese de reemplazar "contraseña" con la contraseña que estableció anteriormente.

## Paso 5: guardar el documento protegido

 Finalmente, puede guardar el documento protegido usando el`Save` método de la clase Documento. Especifique la ruta completa del archivo y el nombre del archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Asegúrese de reemplazar "dataDir" con la ruta a su directorio de documentos.

### Código fuente de ejemplo para la función Permitir solo proteger campos de formulario usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inserte dos secciones con algo de texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// La protección de un documento solo funciona cuando la protección del documento está activada y solo se permite la edición en los campos del formulario.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Guarde el documento protegido.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusión

En esta guía, exploramos cómo usar la biblioteca Aspose.Words para .NET para proteger un documento y permitir que solo se editen campos de formulario. Si sigue los pasos proporcionados, podrá implementar fácilmente esta funcionalidad en su aplicación C#. La protección de documentos es esencial para garantizar la seguridad y confidencialidad de sus documentos.

### Preguntas frecuentes para permitir que solo los campos de formulario se protejan en un documento de Word

#### P: ¿Qué es la protección de documentos en Aspose.Words para .NET?

R: La protección de documentos en Aspose.Words para .NET es una característica que le permite proteger sus documentos restringiendo ciertas acciones, como editar, formatear o modificar el contenido. Ayuda a mantener la integridad y confidencialidad de sus documentos al evitar cambios no autorizados.

#### P: ¿Cómo puedo proteger un documento y permitir que solo se editen campos de formulario usando Aspose.Words para .NET?

R: Para proteger un documento y permitir que solo se editen campos de formulario usando Aspose.Words para .NET, puede seguir estos pasos:
1. Defina la ruta del directorio para su documento.
2.  Inserte secciones y texto en su documento usando el`DocumentBuilder` clase.
3.  Habilite la protección de documentos usando el`Protect` método de la`Document` clase, especificando el tipo de protección como`AllowOnlyFormFields` y proporcionando una contraseña.
4.  Guarde el documento protegido utilizando el`Save` método de la`Document` clase.

#### P: ¿Puedo insertar campos de formulario en un documento protegido usando Aspose.Words para .NET?

R: Sí, puede insertar campos de formulario en un documento protegido usando Aspose.Words para .NET. La protección del documento con el`AllowOnlyFormFields` El tipo permite a los usuarios editar solo los campos del formulario mientras protege el resto del contenido del documento. Puedes usar el`DocumentBuilder` clase para insertar campos de formulario en el documento antes de habilitar la protección.

#### P: ¿Puedo eliminar la protección de un documento protegido?

 R: Sí, puede eliminar la protección de un documento protegido utilizando Aspose.Words para .NET. Para eliminar la protección, puede utilizar el`Unprotect` método de la`Document` clase y proporcione la contraseña correcta. Esto eliminará la protección y permitirá la edición sin restricciones del documento.

#### P: ¿Es posible proteger un documento con múltiples tipos de protección?

 R: No, Aspose.Words para .NET permite aplicar solo un tipo de protección a un documento a la vez. sin embargo, el`AllowOnlyFormFields` El tipo de protección puede restringir efectivamente la edición de campos de formulario y al mismo tiempo permitir otros tipos de protección, como`AllowOnlyComments` o`AllowOnlyRevisions`para combinar con la protección de campos de formulario.

#### P: ¿Puedo establecer contraseñas diferentes para diferentes tipos de protección en un documento?

R: No, Aspose.Words para .NET le permite establecer una contraseña única para la protección de documentos, independientemente del tipo de protección. Se utilizará la misma contraseña para habilitar y deshabilitar la protección de documentos.