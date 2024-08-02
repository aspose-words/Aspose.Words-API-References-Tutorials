---
title: Número de lista de reinicio
linktitle: Número de lista de reinicio
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo restablecer el número de una lista en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-list/restart-list-number/
---
En este tutorial paso a paso, le mostraremos cómo restablecer el número de una lista en un documento de Word usando Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: Crear el documento y el generador de documentos

Primero, cree un nuevo documento y un generador de documentos asociado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: crear y personalizar la primera lista

A continuación, cree una lista basada en una plantilla existente y luego personalice sus niveles:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Paso 3: agregar elementos a la primera lista

Utilice el generador de documentos para agregar elementos a la primera lista y eliminar números de lista:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 4: Crear y personalizar la segunda lista

Para reutilizar la primera lista restableciendo el número, cree una copia del diseño de lista original:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

También puede realizar cambios adicionales en la segunda lista si es necesario.

## Paso 5: agregar elementos a la segunda lista

Utilice el generador de documentos nuevamente para agregar elementos a la segunda lista y eliminar los números de la lista:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 6: guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Entonces ! Ha restablecido con éxito el número de una lista en un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de muestra para restablecer el número de lista

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea una lista basada en una plantilla.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Para reutilizar la primera lista, debemos reiniciar la numeración creando una copia del formato de la lista original.
List list2 = doc.Lists.AddCopy(list1);

// Podemos modificar la nueva lista de cualquier forma, incluso estableciendo un nuevo número de inicio.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Preguntas frecuentes

#### P: ¿Cómo puedo reiniciar la numeración de una lista en Aspose.Words?

 R: Para reiniciar la numeración de una lista en Aspose.Words, puede utilizar el`ListRestartAtNumber` método de la`List` clase. Este método le permite establecer un nuevo valor de marcado a partir del cual se debe reiniciar la lista. Por ejemplo, puedes usar`list.ListRestartAtNumber(1)` para reiniciar la numeración desde 1.

#### P: ¿Es posible personalizar el prefijo y el sufijo de la numeración de la lista reiniciada en Aspose.Words?

 R: Sí, puede personalizar el prefijo y el sufijo de la numeración de la lista reiniciada en Aspose.Words. El`ListLevel`clase ofrece propiedades tales como`ListLevel.NumberPrefix`y`ListLevel.NumberSuffix` que le permiten especificar el prefijo y el sufijo para cada nivel de la lista. Puede utilizar estas propiedades para personalizar el prefijo y el sufijo según sea necesario.

#### P: ¿Cómo puedo especificar un valor de numeración específico a partir del cual se debe reiniciar la lista?

 R: Para especificar un valor numérico específico a partir del cual se debe reiniciar la lista, puede usar el`ListRestartAtNumber` método que pasa el valor deseado como argumento. Por ejemplo, para reiniciar la numeración desde 5, puede utilizar`list.ListRestartAtNumber(5)`.

#### P: ¿Es posible reiniciar la numeración de listas de varios niveles en Aspose.Words?

 R: Sí, Aspose.Words admite reiniciar la numeración de múltiples niveles de lista. Puedes aplicar el`ListRestartAtNumber` método en cada nivel de lista para reiniciar la numeración individualmente. Por ejemplo, puedes usar`list.Levels[0].ListRestartAtNumber(1)` para reiniciar el primer nivel de lista desde 1, y`list.Levels[1].ListRestartAtNumber(1)` para reiniciar la lista del segundo nivel comenzando desde 1, y así sucesivamente.



