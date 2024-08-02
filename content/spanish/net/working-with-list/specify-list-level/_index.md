---
title: Especificar nivel de lista
linktitle: Especificar nivel de lista
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a especificar el nivel de lista en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-list/specify-list-level/
---

En este tutorial paso a paso, le mostraremos cómo especificar el nivel de lista en un documento de Word usando Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: Crear el documento y el generador de documentos

Primero, cree un nuevo documento y un generador de documentos asociado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: crear y aplicar una lista numerada

A continuación, cree una lista numerada basada en una de las plantillas de listas de Microsoft Word y aplíquela al párrafo actual en el generador de documentos:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Paso 3: Especificación del nivel de lista

 Utilice el generador de documentos`ListLevelNumber` propiedad para especificar el nivel de la lista y agregar texto al párrafo:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Repita estos pasos para especificar niveles de lista y agregar texto en cada nivel.

## Paso 4: crear y aplicar una lista con viñetas

También puede crear y aplicar una lista con viñetas utilizando una de las plantillas de lista de Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Paso 5: Agregar texto a los niveles de la lista con viñetas

 Utilizar el`ListLevelNumber` propiedad nuevamente para especificar el nivel de la lista con viñetas y agregar texto:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Paso 6: dejar de formatear la lista

 Para detener el formato de la lista, configure`null` hacia`List`propiedad del generador de documentos:

```csharp
builder. ListFormat. List = null;
```

## Paso 7: guardar el documento modificado

Guarde el documento modificado:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Entonces ! Ha especificado correctamente el nivel de lista en un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de muestra para especificar el nivel de lista

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cree una lista numerada basada en una de las plantillas de listas de Microsoft Word
// aplicarlo al párrafo actual del creador de documentos.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Hay nueve niveles en esta lista, probémoslos todos.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Cree una lista con viñetas basada en una de las plantillas de listas de Microsoft Word
// aplicarlo al párrafo actual del creador de documentos.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Esta es una forma de detener el formato de la lista.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Preguntas frecuentes

#### P: ¿Cómo puedo especificar el nivel de lista en Aspose.Words?

 R: Para especificar el nivel de lista en Aspose.Words, necesita crear una instancia del`List` clase y dale una lista numerada. Entonces puedes usar el`Paragraph.ListFormat.ListLevelNumber` propiedad para especificar el nivel de cada elemento de la lista. Puede asociar esta lista con una sección de su documento para que los elementos de la lista tengan el nivel deseado.

#### P: ¿Es posible cambiar el formato de numeración de los elementos de la lista en Aspose.Words?

 R: Sí, puede cambiar el formato de numeración de los elementos de la lista en Aspose.Words. El`ListLevel` La clase ofrece varias propiedades para esto, como`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, etc. Puede utilizar estas propiedades para establecer el formato de numeración de los elementos de la lista, como números arábigos, números romanos, letras, etc.

#### P: ¿Puedo agregar niveles adicionales a una lista numerada en Aspose.Words?

 R: Sí, es posible agregar niveles adicionales a una lista numerada en Aspose.Words. El`ListLevel`La clase le permite establecer propiedades de formato para cada nivel de la lista. Puede configurar opciones como prefijo, sufijo, alineación, sangría, etc. Esto le permite crear listas con múltiples niveles de jerarquía.


