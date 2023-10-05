---
title: Funciones de tipo abierto
linktitle: Funciones de tipo abierto
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a habilitar y utilizar las funciones de Open Type en Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/enable-opentype-features/open-type-features/
---

En este completo tutorial, aprenderá cómo habilitar y utilizar las funciones de Open Type en Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá trabajar con las funciones de Open Type en sus documentos de Word.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: cargue el documento
Para comenzar, cargue el documento usando la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Paso 2: habilite las funciones de tipo abierto
Para habilitar las funciones de Open Type, establezca la propiedad TextShaperFactory de la clase LayoutOptions en una instancia de la fábrica de modeladores de texto deseada. En este ejemplo, utilizamos HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Paso 3: guarde el documento
Después de habilitar las funciones de Open Type, guarde el documento en el formato de salida deseado, como PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Ejemplo de código fuente para funciones de tipo abierto utilizando Aspose.Words para .NET
Aquí está el código fuente completo para usar las funciones Open Type en Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo habilitar y utilizar las funciones de Open Type en Aspose.Words para .NET. Si sigue la guía paso a paso y utiliza el código fuente proporcionado, ahora puede trabajar con funciones de Open Type en sus documentos de Word.

Las funciones Open Type ofrecen capacidades mejoradas de tipografía y configuración de texto, lo que le permite crear documentos visualmente atractivos y de apariencia profesional. Experimente con diferentes fábricas de modeladores de texto y explore las posibilidades de las funciones de tipo abierto en sus proyectos.

### Preguntas frecuentes

#### P: ¿Cómo habilito las funciones OpenType en Aspose.Words para .NET?

R: Para habilitar las funciones OpenType en Aspose.Words para .NET, debe seguir los pasos mencionados en el tutorial.

#### P: ¿Qué funciones OpenType son compatibles con Aspose.Words para .NET?

R: Aspose.Words para .NET admite varias funciones OpenType, como ligaduras, variaciones de glifos, sustituciones contextuales y más.

#### P: ¿Cómo puedo comprobar si una función OpenType es compatible con una fuente específica?

R: Puede comprobar si una función OpenType es compatible con una fuente específica utilizando el`Font.OpenTypeFeatures` método en Aspose.Words para .NET.

#### P: ¿Qué otras funciones de formato de texto admite Aspose.Words para .NET?

R: Además de las funciones OpenType, Aspose.Words para .NET también admite otras funciones de formato de texto, como formatear párrafos, crear tablas, agregar imágenes, etc.

#### P: ¿Puedo utilizar las funciones OpenType en todas las versiones de Aspose.Words para .NET?

R: Las funciones OpenType son compatibles con las versiones más recientes de Aspose.Words para .NET. Asegúrese de estar utilizando una versión compatible para beneficiarse de estas funciones.