---
title: Comprobar secuencia
linktitle: Comprobar secuencia
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a verificar la secuencia de cuadros de texto en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/check-sequence/
---

## Paso 1: configurar el documento y crear una forma de cuadro de texto

 Para comenzar, debemos configurar el documento y crear una forma de cuadro de texto. El siguiente código inicializa una nueva instancia del`Document` clase y crea una forma de cuadro de texto:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Paso 2: Comprobación de la secuencia de TextBox

 Ahora comprobaremos la secuencia del TextBox usando`if` condiciones. El código fuente provisto contiene tres condiciones separadas para verificar la posición del cuadro de texto en relación con las formas anteriores y posteriores.

## Paso 3: Comprobación del encabezado de secuencia:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Si el cuadro de texto tiene una forma siguiente (`Next`) pero sin forma previa (`Previous`), eso significa que es la cabeza de la secuencia. Se mostrará el mensaje "La cabecera de la secuencia".

## Paso 4: Comprobación de la mitad de la secuencia:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Si el cuadro de texto tiene una forma Siguiente (`Next`) y una forma anterior (`Previous`), esto indica que está en medio de la secuencia. Se mostrará el mensaje "La mitad de la secuencia".

## Paso 5: Verificación del final de la secuencia:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Si el cuadro de texto no tiene la siguiente forma (`Next`) pero tiene una forma anterior (`Previous`), eso significa que es el final de la secuencia. Se mostrará el mensaje "El final de la secuencia".

### Ejemplo de código fuente para verificar la secuencia con Aspose.Words para .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```