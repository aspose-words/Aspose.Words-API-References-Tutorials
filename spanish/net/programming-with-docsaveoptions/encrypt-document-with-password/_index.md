---
title: Cifrar documento con contraseña
linktitle: Cifrar documento con contraseña
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cifrar documentos con una contraseña utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
La seguridad de los documentos es esencial cuando se trabaja con archivos en una aplicación C#. Con la biblioteca Aspose.Words para .NET, puede proteger fácilmente sus documentos cifrándolos con una contraseña. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para encriptar un documento usando las opciones de guardado de DocSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Paso 1: Definición del directorio de documentos

El primer paso es configurar el directorio donde desea guardar el documento cifrado. Debe especificar la ruta completa del directorio. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: Crear y editar un documento

Luego puede crear un documento y agregarle contenido. Utilice la clase DocumentBuilder proporcionada por Aspose.Words para crear el contenido de su documento. Por ejemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

En este ejemplo, creamos un nuevo documento en blanco y luego usamos DocumentBuilder para escribir el texto "¡Hola mundo!".

## Paso 3: Configure las opciones de grabación

Ahora vamos a configurar las opciones de guardado de nuestro documento. Utilice la clase DocSaveOptions para especificar la configuración de guardado. Por ejemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

En este ejemplo, creamos un nuevo objeto DocSaveOptions y establecemos la propiedad Contraseña en "contraseña" para cifrar el documento con esta contraseña.

## Paso 4: Habilitación de la función "Cifrar documento con contraseña"

Ya hemos configurado las opciones para

registro con la contraseña especificada, que activa automáticamente la función "Cifrar documento con contraseña". Esto asegura que el documento esté encriptado con la contraseña especificada cuando se guardó.

## Paso 5: Guardar el documento

Finalmente, puede guardar el documento utilizando el método Guardar de la clase Documento. Especifique la ruta completa al archivo y el nombre de archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Asegúrese de reemplazar "dataDir" con la ruta del directorio a sus documentos.

### Ejemplo de código fuente para las opciones de guardado de DocSaveOptions con la funcionalidad "Cifrar documento con contraseña" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear y editar un documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configure las opciones de guardado con la función "Cifrar documento con contraseña"
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Guarde el documento con las opciones especificadas
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusión

En esta guía, explicamos cómo usar la biblioteca Aspose.Words para .NET para cifrar un documento con una contraseña usando las opciones de guardado de DocSaveOptions. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. Cifrar el documento con una contraseña garantiza su confidencialidad y seguridad en el manejo del mismo.