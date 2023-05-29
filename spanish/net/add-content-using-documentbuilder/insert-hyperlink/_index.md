---
title: Insertar hipervínculo
linktitle: Insertar hipervínculo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar hipervínculos en documentos de Word usando Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-hyperlink/
---

En este completo tutorial, aprenderá a insertar hipervínculos en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar hipervínculos en los que se puede hacer clic a sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserte un hipervínculo
continuación, utilice el método Write de la clase DocumentBuilder para agregar texto y formatear el hipervínculo configurando las propiedades de color y subrayado:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Paso 3: Guarde el documento
Después de insertar el hipervínculo, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Ejemplo de código fuente para insertar hipervínculo usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar un hipervínculo usando Aspose.Words para .NET:

Los hipervínculos son una forma poderosa de mejorar la interactividad y la utilidad de sus documentos de Word. Se pueden usar para hacer referencia a recursos externos, proporcionar información adicional o crear elementos de navegación dentro del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos, incluido el texto del hipervínculo y la URL. Mejórelo con formato o funcionalidad adicional según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar hipervínculos en un documento de Word utilizando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede agregar hipervínculos en los que se puede hacer clic a sus documentos, dirigiendo a los lectores a sitios web externos o URL específicas.

