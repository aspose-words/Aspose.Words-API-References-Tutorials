---
title: Número de lista de reinicio
linktitle: Número de lista de reinicio
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a restablecer el número de una lista en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-list/restart-list-number/
---
En este tutorial paso a paso, le mostraremos cómo restablecer el número de una lista en un documento de Word usando Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde el sitio oficial.

## Paso 1: Crear el Documento y el Generador de Documentos

Primero, cree un nuevo documento y un generador de documentos asociado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: crear y personalizar la primera lista

Luego, cree una lista basada en una plantilla existente, luego personalice sus niveles:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Paso 3: agregar elementos a la primera lista

Use el generador de documentos para agregar elementos a la primera lista y eliminar números de lista:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 4: Creación y personalización de la segunda lista

Para reutilizar la primera lista restableciendo el número, cree una copia del diseño de la lista original:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

También puede realizar cambios adicionales en la segunda lista si es necesario.

## Paso 5: agregar elementos a la segunda lista

Use el generador de documentos nuevamente para agregar elementos a la segunda lista y eliminar los números de la lista:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 6: Guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Entonces ! Ha restablecido con éxito el número de una lista en un documento de Word utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para el restablecimiento del número de lista

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cree una lista basada en una plantilla.
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

// Podemos modificar la nueva lista de cualquier manera, incluida la configuración de un nuevo número de inicio.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```




