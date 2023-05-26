---
title: Cargar documento cifrado
linktitle: Cargar documento cifrado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cargar y guardar documentos cifrados con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/load-encrypted-document/
---

Cuando se trabaja con documentos cifrados en una aplicación de C#, es importante poder cargarlos correctamente proporcionando la contraseña correcta. Con la biblioteca Aspose.Words para .NET, puede cargar fácilmente documentos cifrados utilizando las opciones de carga adecuadas. En esta guía paso a paso, le mostraremos cómo utilizar el código fuente de C# de Aspose.Words para .NET para cargar un documento cifrado mediante las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Cargando un documento encriptado

El primer paso es cargar un documento encriptado utilizando las opciones de carga adecuadas. En nuestro caso, usamos la clase Document para cargar el documento especificando la ruta y la contraseña del documento. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

En este ejemplo, cargamos el documento "Encrypted.docx" ubicado en el directorio de documentos usando la contraseña "contraseña".

## Guardar un documento encriptado

Después de cargar un documento cifrado, también puede guardarlo especificando una nueva contraseña para el archivo de salida. En nuestro ejemplo, usamos la clase OdtSaveOptions para guardar el documento en formato ODT con una nueva contraseña. Aquí está cómo hacerlo:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

En este ejemplo, guardamos el documento con el nombre "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" especificando la nueva contraseña "newpassword".

### Ejemplo de código fuente para LoadOptions con la funcionalidad "Cargar documento cifrado" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue un documento encriptado con la contraseña especificada
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//Guardar un documento encriptado con una nueva contraseña
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Conclusión

En esta guía, explicamos cómo cargar y guardar documentos cifrados utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. La carga de documentos cifrados mantiene sus datos seguros y le permite trabajar con documentos protegidos en Aspose.Words.