---
title: Formato de regla horizontal
linktitle: Formato de regla horizontal
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a formatear reglas horizontales en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/horizontal-rule-format/
---

En este ejemplo completo, aprenderá a formatear una regla horizontal en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá personalizar la alineación, el ancho, la altura, el color y otras propiedades de una regla horizontal.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: cree un DocumentBuilder e inserte una regla horizontal
Para comenzar, cree un objeto DocumentBuilder y use el método InsertHorizontalRule para insertar una regla horizontal:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Paso 2: acceda al formato de regla horizontal
A continuación, acceda a la propiedad HorizontalRuleFormat del objeto Shape para recuperar las opciones de formato:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Paso 3: personaliza las opciones de formato
Ahora, puede personalizar varias opciones de formato para la regla horizontal. Por ejemplo, puede ajustar la alineación, el ancho, la altura, el color y el sombreado:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Paso 4: Guarde el documento
Después de formatear la regla horizontal, guarde el documento en un archivo utilizando el método Guardar del objeto Documento:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Ejemplo de código fuente para formato de regla horizontal usando Aspose.Words para .NET
Aquí está el código fuente completo para formatear una regla horizontal usando Aspose.Words para .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo dar formato a una regla horizontal en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede personalizar la apariencia de las reglas horizontales para mejorar el diseño visual de su documento.

Experimente con diferentes opciones de formato para lograr el estilo y el efecto deseados para sus reglas horizontales.
