---
title: Características de tipo abierto
linktitle: Características de tipo abierto
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a habilitar y usar las funciones de tipo abierto en Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/enable-opentype-features/open-type-features/
---

En este completo tutorial, aprenderá cómo habilitar y utilizar las funciones de tipo abierto en Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá trabajar con funciones de tipo abierto en sus documentos de Word.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cargue el Documento
Para comenzar, cargue el documento usando la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Paso 2: habilite las funciones de tipo abierto
Para habilitar las funciones de tipo abierto, establezca la propiedad TextShaperFactory de la clase LayoutOptions en una instancia de la fábrica de modelado de texto deseada. En este ejemplo, usamos HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Paso 3: Guarde el documento
Después de habilitar las funciones de tipo abierto, guarde el documento en el formato de salida deseado, como PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Código fuente de ejemplo para características de tipo abierto usando Aspose.Words para .NET
Aquí está el código fuente completo para usar las funciones de tipo abierto en Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo habilitar y utilizar las funciones de tipo abierto en Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede trabajar con las funciones de tipo abierto en sus documentos de Word.

Las funciones Open Type ofrecen capacidades mejoradas de tipografía y forma de texto, lo que le permite crear documentos visualmente atractivos y de aspecto profesional. Experimente con diferentes fábricas de modeladores de texto y explore las posibilidades de las funciones de tipo abierto en sus proyectos.

### Preguntas frecuentes

#### P: ¿Cómo habilito las características de OpenType en Aspose.Words para .NET?

R: Para habilitar las funciones de OpenType en Aspose.Words para .NET, debe seguir los pasos mencionados en el tutorial.

#### P: ¿Qué características de OpenType son compatibles con Aspose.Words para .NET?

R: Aspose.Words para .NET admite varias características de OpenType, como ligaduras, variaciones de glifos, sustituciones contextuales y más.

#### P: ¿Cómo puedo verificar si una función OpenType es compatible con una fuente específica?

R: Puede verificar si una función OpenType es compatible con una fuente específica usando el`Font.OpenTypeFeatures` método en Aspose.Words para .NET.

#### P: ¿Qué otras funciones de formato de texto admite Aspose.Words para .NET?

R: Además de las funciones de OpenType, Aspose.Words para .NET también admite otras funciones de formato de texto, como formatear párrafos, crear tablas, agregar imágenes, etc.

#### P: ¿Puedo usar funciones de OpenType en todas las versiones de Aspose.Words para .NET?

R: Las funciones de OpenType son compatibles con las versiones más recientes de Aspose.Words para .NET. Asegúrese de estar utilizando una versión compatible para beneficiarse de estas funciones.