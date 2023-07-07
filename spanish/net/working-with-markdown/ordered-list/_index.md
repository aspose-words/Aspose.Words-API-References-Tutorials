---
title: Lista ordenada
linktitle: Lista ordenada
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear una lista ordenada con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/ordered-list/
---

En este ejemplo, explicaremos cómo usar la función de lista ordenada con Aspose.Words para .NET. La lista ordenada le permite organizar elementos secuencialmente con números.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para crear un nuevo documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Aplicar el formato de lista ordenada

 Aplicaremos el formato de lista ordenada usando el generador de documentos`ApplyBulletDefault`método. También podemos personalizar el formato de numeración yendo a los niveles de la lista y configurando el formato que queramos.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Paso 3: agregar elementos a la lista

 Podemos agregar elementos a la lista usando el generador de documentos`Writeln` método.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Paso 4: Aplicar sangría a la lista

 Podemos sangrar la lista usando el generador de documentos`ListIndent` método.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Paso 5: Guardar el documento

Finalmente, podemos guardar el documento en el formato deseado.

### Código fuente de ejemplo para lista ordenada con Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

¡Felicidades! Ahora ha aprendido a usar la función de lista ordenada con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo crear una lista ordenada en Markdown?

R: Para crear una lista ordenada en Markdown, comience cada elemento de la lista con un número seguido de un punto (`1.`, `2.`, `3.`), seguido de un espacio.

#### P: ¿Podemos anidar listas ordenadas en Markdown?

R: Sí, es posible anidar listas ordenadas en Markdown agregando cuatro espacios de compensación delante de cada elemento de la lista anidada.

#### P: ¿Cómo personalizar la numeración de listas ordenadas?

R: En Markdown estándar, la numeración de lista ordenada se genera automáticamente. Sin embargo, algunos editores de Markdown te permiten personalizarlo usando extensiones específicas.

#### P: ¿Las listas ordenadas en Markdown admiten sangría?

R: Sí, las listas ordenadas en Markdown admiten la sangría. Puede agregar un desplazamiento a la izquierda usando espacios o tabulaciones.

#### P: ¿Se pueden agregar enlaces o texto en línea a los elementos de la lista?

R: Sí, puede agregar enlaces o texto en línea para enumerar elementos utilizando la sintaxis de Markdown adecuada.