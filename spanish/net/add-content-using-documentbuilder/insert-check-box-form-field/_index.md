---
title: Insertar campo de formulario de casilla de verificación
linktitle: Insertar campo de formulario de casilla de verificación
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar campos de formulario de casilla de verificación en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

En este completo tutorial, aprenderá a insertar un campo de formulario de casilla de verificación en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar campos de formulario de casilla de verificación con propiedades personalizables a sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserte un campo de formulario de casilla de verificación
continuación, utilice el método InsertCheckBox de la clase DocumentBuilder para insertar un campo de formulario de casilla de verificación. Proporcione los parámetros de nombre, estado marcado, estado predeterminado y tamaño como argumentos:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Paso 3: Guarde el documento
Después de insertar el campo de formulario de la casilla de verificación, guarde el documento en un archivo utilizando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Ejemplo de código fuente para insertar campo de formulario de casilla de verificación usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar un campo de formulario de casilla de verificación usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar un campo de formulario de casilla de verificación en un documento de Word utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede mejorar sus documentos con campos de formulario de casilla de verificación interactivos.
