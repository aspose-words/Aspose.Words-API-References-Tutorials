---
title: Insertar imagen flotante
linktitle: Insertar imagen flotante
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar imágenes flotantes en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-floating-image/
---

En este completo ejemplo, aprenderá a insertar una imagen flotante en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar imágenes con posicionamiento personalizable y opciones de ajuste a sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserta una imagen flotante
continuación, utilice el método InsertImage de la clase DocumentBuilder para insertar una imagen flotante. Proporcione la ruta del archivo de imagen, la posición horizontal y vertical relativa, el ancho, el alto y las opciones de ajuste como parámetros:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Paso 3: Guarde el documento
Después de insertar la imagen flotante, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Ejemplo de código fuente para insertar imagen flotante usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una imagen flotante usando Aspose.Words para .NET:
Las imágenes flotantes son útiles para varios escenarios, como agregar logotipos, ilustraciones o elementos decorativos que se pueden colocar independientemente del texto del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos, incluida la ruta del archivo de imagen y las opciones de colocación y ajuste deseadas.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar una imagen flotante en un documento de Word usando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede mejorar sus documentos con imágenes flotantes visualmente atractivas y personalizables.

