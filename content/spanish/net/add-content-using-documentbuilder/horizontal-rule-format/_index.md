---
title: Formato de regla horizontal en documento de Word
linktitle: Formato de regla horizontal en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a formatear reglas horizontales en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/horizontal-rule-format/
---
En este ejemplo completo, aprenderá cómo formatear una regla horizontal en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá personalizar la alineación, el ancho, el alto, el color y otras propiedades de una regla horizontal.

## Requisitos previos
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
Ahora puede personalizar varias opciones de formato para la regla horizontal. Por ejemplo, puede ajustar la alineación, el ancho, el alto, el color y el sombreado:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Paso 4: guarde el documento
Después de formatear la regla horizontal, guarde el documento en un archivo usando el método Guardar del objeto Documento:

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
¡Felicidades! Ha aprendido con éxito cómo formatear una regla horizontal en un documento de Word usando Aspose.Words para .NET. Si sigue la guía paso a paso y utiliza el código fuente proporcionado, ahora puede personalizar la apariencia de las reglas horizontales para mejorar el diseño visual de su documento.

Experimente con diferentes opciones de formato para lograr el estilo y efecto deseados para sus reglas horizontales.

### Preguntas frecuentes sobre el formato de regla horizontal en un documento de Word

#### P: ¿Puedo aplicar diferentes colores a la regla horizontal?

R: ¡Absolutamente! Con Aspose.Words para .NET, puede personalizar fácilmente el color de la regla horizontal estableciendo la propiedad Color en el valor de color deseado. Esto le permite hacer coincidir la regla horizontal con el diseño general de su documento.

#### P: ¿Es posible ajustar el ancho y el alto de la regla horizontal?

R: Sí, tienes control total sobre el ancho y el alto de la regla horizontal. Al modificar las propiedades AnchoPercent y Alto, puede lograr las dimensiones deseadas para la regla horizontal.

#### P: ¿Puedo cambiar la alineación de la regla horizontal dentro del documento?

R: ¡Ciertamente! Aspose.Words para .NET le permite especificar la alineación de la regla horizontal utilizando la propiedad Alineación. Puede elegir entre varias opciones como Centro, Izquierda, Derecha y Justificado.

#### P: ¿Puedo aplicar sombreado o color de fondo a la regla horizontal?

R: Sí, puedes agregar sombreado o color de fondo a la regla horizontal. De forma predeterminada, la propiedad NoShade está establecida en verdadero, pero puede establecerla en falso y definir el sombreado utilizando los métodos apropiados.

#### P: ¿Puedo insertar varias reglas horizontales en un solo documento?

R: ¡Absolutamente! Puede insertar varias reglas horizontales en un documento de Word utilizando Aspose.Words para .NET. Simplemente repita los pasos del tutorial según sea necesario para agregar tantas reglas horizontales como necesite.