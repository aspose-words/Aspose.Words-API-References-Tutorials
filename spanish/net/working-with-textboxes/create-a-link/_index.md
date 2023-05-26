---
title: Crear un enlace
linktitle: Crear un enlace
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear un vínculo entre cuadros de texto en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/create-a-link/
---

## Paso 1: Configurar el documento y crear formas de TextBox

 Para comenzar, necesitamos configurar el documento y crear dos formas de TextBox. El siguiente código inicializa una nueva instancia del`Document` clase y crea dos formas de cuadro de texto:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Paso 2: Creando un enlace entre TextBoxes

 Ahora crearemos un enlace entre los dos TextBoxes usando el`IsValidLinkTarget()` método y el`Next` propiedad del primer TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 El`IsValidLinkTarget()` El método comprueba si el segundo TextBox puede ser un objetivo válido para el enlace del primer TextBox. Si la validación tiene éxito, el`Next` La propiedad del primer TextBox se establece en el segundo TextBox, creando un vínculo entre los dos.

### Ejemplo de código fuente para vincular con Aspose.Words para .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```