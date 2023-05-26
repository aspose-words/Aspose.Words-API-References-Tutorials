---
title: Permitir solo protección de campos de formulario
linktitle: Permitir solo protección de campos de formulario
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar Aspose.Words para .NET para proteger documentos y solo permitir la edición de campos de formulario.
type: docs
weight: 10
url: /es/net/document-protection/allow-only-form-fields-protect/
---

La protección de documentos es una característica esencial cuando se trabaja con archivos dentro de su aplicación C#. Con la biblioteca Aspose.Words para .NET, puede proteger fácilmente sus documentos y solo permitir que se editen los campos de formulario. En esta guía paso a paso, lo guiaremos a través de cómo usar el código fuente de C# para permitir que solo los campos de formulario se editen usando la función Permitir solo protección de campos de formulario de Aspose.Words para .NET.

## Paso 1: Configuración del directorio de documentos

El primer paso es definir el directorio de su documento. Debe especificar la ruta donde desea guardar el documento protegido. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: Inserción de secciones y texto

continuación, debe insertar secciones y texto en su documento. Utilice la clase DocumentBuilder proporcionada por Aspose.Words para crear el contenido de su documento. Aquí hay un ejemplo simple:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

En este ejemplo, creamos un nuevo documento en blanco y luego usamos DocumentBuilder para agregar una línea de texto.

## Paso 3: habilitar la protección de documentos

 La protección de documentos solo funciona cuando la protección de documentos está habilitada. Puede habilitar la protección de documentos utilizando el`Protect` método de la clase Documento. Así es cómo:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

En este ejemplo, habilitamos la protección de documentos especificando el tipo de protección `

AllowOnlyFormFields` y establecer una contraseña.

## Paso 4: Permitir solo campos de formulario

Ahora que la protección de documentos está habilitada, debemos especificar que solo se permite la edición de campos de formulario. Esto garantiza que los usuarios solo puedan editar partes del documento que son campos de formulario. Así es cómo:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Asegúrese de reemplazar "contraseña" con la contraseña que configuró anteriormente.

## Paso 5: Guardar el Documento Protegido

Finalmente, puede guardar el documento protegido usando el`Save` método de la clase Documento. Especifique la ruta completa del archivo y el nombre de archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Asegúrese de reemplazar "dataDir" con la ruta a su directorio de documentos.

### Ejemplo de código fuente para la función Permitir solo protección de campos de formulario con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inserta dos secciones con algo de texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// La protección de un documento solo funciona cuando la protección del documento está activada y solo se permite la edición en los campos del formulario.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Guarde el documento protegido.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusión

En esta guía, exploramos cómo usar la biblioteca Aspose.Words para .NET para proteger un documento y solo permitir que se editen los campos del formulario. Siguiendo los pasos proporcionados, puede implementar fácilmente esta funcionalidad en su aplicación C#. La protección de documentos es esencial para garantizar la seguridad y confidencialidad de sus documentos.
