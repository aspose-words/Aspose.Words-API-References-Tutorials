---
title: Agregar forma de grupo
linktitle: Agregar forma de grupo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar formas de grupo a documentos de Word usando Aspose.Words para .NET con este completo tutorial paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-shapes/add-group-shape/
---
## Introducción

Crear documentos complejos con elementos visuales ricos a veces puede ser una tarea desalentadora, especialmente cuando se trata de formas grupales. ¡Pero no temas! Aspose.Words para .NET simplifica este proceso, haciéndolo muy fácil. En este tutorial, lo guiaremos a través de los pasos para agregar formas de grupo a sus documentos de Word. ¿Listo para sumergirte? ¡Empecemos!

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1.  Aspose.Words para .NET: puede descargarlo desde[Página de lanzamientos de Aspose](https://releases.aspose.com/words/net/).
2. Entorno de Desarrollo: Visual Studio o cualquier otro IDE compatible con .NET.
3. Comprensión básica de C#: la familiaridad con la programación de C# es una ventaja.

## Importar espacios de nombres

Para comenzar, necesitamos importar los espacios de nombres necesarios en nuestro proyecto. Estos espacios de nombres brindan acceso a las clases y métodos necesarios para manipular documentos de Word con Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Paso 1: Inicializar el documento

Primero lo primero, inicialicemos un nuevo documento de Word. Piense en esto como crear un lienzo en blanco donde agregaremos las formas de nuestro grupo.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Aquí,`EnsureMinimum()` agrega un conjunto mínimo de nodos necesarios para el documento.

## Paso 2: crear el objeto GroupShape

 A continuación, necesitamos crear un`GroupShape`objeto. Este objeto servirá como contenedor para otras formas, permitiéndonos agruparlas.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Paso 3: agregar formas a GroupShape

 Ahora, agreguemos formas individuales a nuestro`GroupShape` recipiente. Comenzaremos con una forma de borde acentuada y luego agregaremos una forma de botón de acción.

### Agregar una forma de borde de acento

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Este fragmento de código crea una forma de borde de acento con un ancho y alto de 100 unidades y la agrega al`GroupShape`.

### Agregar una forma de botón de acción

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Aquí, creamos una forma de botón de acción, la posicionamos y la agregamos a nuestro`GroupShape`.

## Paso 4: definir las dimensiones de GroupShape

 Para garantizar que nuestras formas encajen bien dentro del grupo, debemos establecer las dimensiones del`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Esto define el ancho y alto del`GroupShape` como 200 unidades y establece el tamaño de las coordenadas en consecuencia.

## Paso 5: inserte GroupShape en el documento

 Ahora, insertemos nuestro`GroupShape` en el documento usando`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` proporciona una manera fácil de agregar nodos, incluidas formas, al documento.

## Paso 6: guarde el documento

Finalmente, guarde el documento en su directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

¡Y ahí lo tienes! Su documento con formas grupales está listo.

## Conclusión

Agregar formas grupales a sus documentos de Word no tiene por qué ser un proceso complicado. Con Aspose.Words para .NET, puede crear y manipular formas con facilidad, haciendo que sus documentos sean más atractivos y funcionales visualmente. ¡Sigue los pasos descritos en este tutorial y serás un profesional en poco tiempo!

## Preguntas frecuentes

### ¿Puedo agregar más de dos formas a un GroupShape?
 Sí, puedes agregar tantas formas como necesites a un`GroupShape` . Sólo usa el`AppendChild` método para cada forma.

### ¿Es posible diseñar las formas dentro de GroupShape?
 ¡Absolutamente! Cada forma se puede diseñar individualmente usando las propiedades disponibles en la`Shape` clase.

### ¿Cómo coloco GroupShape dentro del documento?
 Puedes posicionar el`GroupShape` estableciendo su`Left`y`Top` propiedades.

### ¿Puedo agregar texto a las formas dentro de GroupShape?
 Sí, puedes agregar texto a las formas usando el`AppendChild` método para agregar un`Paragraph` que contiene`Run` nodos con texto.

### ¿Es posible agrupar formas dinámicamente según la entrada del usuario?
Sí, puede crear y agrupar formas dinámicamente según la entrada del usuario ajustando las propiedades y los métodos en consecuencia.