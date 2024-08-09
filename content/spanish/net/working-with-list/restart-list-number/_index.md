---
title: Número de lista de reinicio
linktitle: Número de lista de reinicio
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo reiniciar números de lista en documentos de Word usando Aspose.Words para .NET. Esta guía detallada de 2000 palabras cubre todo lo que necesita saber, desde la configuración hasta la personalización avanzada.
type: docs
weight: 10
url: /es/net/working-with-list/restart-list-number/
---
## Introducción

¿Está buscando dominar el arte de la manipulación de listas en sus documentos de Word usando Aspose.Words para .NET? Bueno, ¡estás en el lugar correcto! En este tutorial, profundizaremos en el reinicio de números de lista, una característica ingeniosa que llevará sus habilidades de automatización de documentos al siguiente nivel. ¡Abróchate el cinturón y comencemos!

## Requisitos previos

Antes de pasar al código, asegurémonos de que tiene todo lo que necesita:

1.  Aspose.Words para .NET: Debe tener instalado Aspose.Words para .NET. Si aún no lo has instalado, puedes[descárgalo aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo adecuado como Visual Studio.
3. Conocimientos básicos de C#: un conocimiento básico de C# le ayudará a seguir el tutorial.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Estos son cruciales para acceder a las funciones de Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Ahora, dividamos el proceso en pasos fáciles de seguir. Cubriremos todo, desde crear una lista hasta reiniciar su numeración.

## Paso 1: configure su documento y su generador

Antes de poder empezar a manipular listas, necesita un documento y un DocumentBuilder. DocumentBuilder es su herramienta de referencia para agregar contenido a su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: crea y personaliza tu primera lista

A continuación, crearemos una lista basada en una plantilla y personalizaremos su apariencia. En este ejemplo, utilizamos el formato de número arábigo con paréntesis.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Aquí, configuramos el color de fuente en rojo y alineamos el texto a la derecha.

## Paso 3: agregue elementos a su primera lista

 Con su lista lista, es hora de agregar algunos elementos. El creador de documentos`ListFormat.List` La propiedad ayuda a aplicar el formato de lista al texto.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 4: reiniciar la numeración de listas

Para reutilizar la lista y reiniciar su numeración, es necesario crear una copia de la lista original. Esto le permite modificar la nueva lista de forma independiente.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

En este ejemplo, la nueva lista comienza en el número 10.

## Paso 5: agregar elementos a la nueva lista

Como antes, agregue elementos a su nueva lista. Esto demuestra que la lista se reinicia en el número especificado.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Paso 6: guarde su documento

Finalmente, guarde su documento en su directorio especificado.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Conclusión

Reiniciar números de lista en documentos de Word usando Aspose.Words para .NET es sencillo e increíblemente útil. Ya sea que esté generando informes, creando documentos estructurados o simplemente necesite un mejor control sobre sus listas, esta técnica lo tiene cubierto.

## Preguntas frecuentes

### ¿Puedo utilizar otras plantillas de listas además de NumberArabicParenthesis?

¡Absolutamente! Aspose.Words ofrece varias plantillas de listas, como viñetas, letras, números romanos y más. Podrás elegir el que mejor se adapte a tus necesidades.

### ¿Cómo cambio el nivel de la lista?

 Puede cambiar el nivel de la lista modificando el`ListLevels` propiedad. Por ejemplo,`list1.ListLevels[1]` se referiría al segundo nivel de la lista.

### ¿Puedo reiniciar la numeración en cualquier número?

 Sí, puede establecer el número inicial en cualquier valor entero usando el`StartAt` propiedad del nivel de lista.

### ¿Es posible tener diferentes formatos para diferentes niveles de lista?

¡En efecto! Cada nivel de lista puede tener su propia configuración de formato, como fuente, alineación y estilo de numeración.

### ¿Qué pasa si quiero seguir numerando desde una lista anterior en lugar de reiniciar?

Si desea continuar con la numeración, no necesita crear una copia de la lista. Simplemente continúe agregando elementos a la lista original.


