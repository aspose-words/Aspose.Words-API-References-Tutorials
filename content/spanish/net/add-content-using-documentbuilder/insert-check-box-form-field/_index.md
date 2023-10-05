---
title: Insertar campo de formulario de casilla de verificación en un documento de Word
linktitle: Insertar campo de formulario de casilla de verificación en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar campos de formulario con casillas de verificación en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
En este completo tutorial, aprenderá cómo insertar un campo de formulario con casilla de verificación en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar campos de formulario de casillas de verificación con propiedades personalizables a sus documentos.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Documento e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Inserte un campo de formulario con casilla de verificación
A continuación, utilice el método InsertCheckBox de la clase DocumentBuilder para insertar un campo de formulario de casilla de verificación. Proporcione los parámetros nombre, estado marcado, estado predeterminado y tamaño como argumentos:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Paso 3: guarde el documento
Después de insertar el campo del formulario de casilla de verificación, guarde el documento en un archivo usando el método Guardar de la clase Documento:

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
¡Felicidades! Ha aprendido con éxito cómo insertar un campo de formulario de casilla de verificación en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede mejorar sus documentos con campos de formulario de casilla de verificación interactivos.

### Preguntas frecuentes

#### P: ¿Puedo insertar varios campos de formulario con casillas de verificación en un solo documento?

R: ¡Absolutamente! Puede insertar tantos campos de formulario de casilla de verificación como sea necesario en un documento de Word utilizando Aspose.Words para .NET. Simplemente repita el proceso de inserción para agregar varias casillas de verificación interactivas.

#### P: ¿Puedo establecer el estado inicial (marcado o no marcado) del campo del formulario de casilla de verificación?

R: Sí, usted tiene control total sobre el estado inicial del campo del formulario de casilla de verificación. Al establecer el parámetro de estado marcado en verdadero o falso, puede definir si la casilla de verificación está inicialmente marcada o desmarcada.

#### P: ¿Los campos del formulario de casilla de verificación son compatibles con otros formatos de archivo, como PDF?

R: Sí, los campos de formulario de casilla de verificación insertados con Aspose.Words para .NET son compatibles con varios formatos de archivo, incluidos DOCX y PDF. Esto le permite exportar sus documentos en diferentes formatos manteniendo las casillas de verificación interactivas.

#### P: ¿Puedo ajustar el tamaño del campo del formulario de casilla de verificación?

R: ¡Ciertamente! Puede especificar el tamaño del campo del formulario de la casilla de verificación utilizando el parámetro de tamaño en el método InsertCheckBox. Esto le permite controlar las dimensiones de la casilla de verificación según sus preferencias de diseño.

#### P: ¿Aspose.Words para .NET es adecuado tanto para aplicaciones web como de escritorio?

R: Sí, Aspose.Words para .NET es una biblioteca versátil adecuada tanto para aplicaciones web como de escritorio. Ya sea que esté creando una aplicación de Windows o un sistema basado en web, puede integrar la biblioteca sin esfuerzo.