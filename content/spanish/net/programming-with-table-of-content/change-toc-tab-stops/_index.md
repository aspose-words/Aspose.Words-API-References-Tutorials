---
title: Cambiar las tabulaciones de Toc en un documento de Word
linktitle: Cambiar las tabulaciones de Toc en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo cambiar las tabulaciones de TOC en documentos de Word usando Aspose.Words para .NET. Esta guía paso a paso le ayudará a crear un índice de aspecto profesional.
type: docs
weight: 10
url: /es/net/programming-with-table-of-content/change-toc-tab-stops/
---
## Introducción

¿Alguna vez te has preguntado cómo mejorar la tabla de contenidos (TOC) de tus documentos de Word? Tal vez quieras que esas tabulaciones se alineen perfectamente para darle ese toque profesional. ¡Estás en el lugar correcto! Hoy, profundizaremos en cómo puede cambiar las tabulaciones de TOC usando Aspose.Words para .NET. Quédese y le prometo que se irá con todos los conocimientos necesarios para que su TOC luzca elegante y ordenado.

## Requisitos previos

Antes de comenzar, asegurémonos de que tiene todo lo que necesita:

1.  Aspose.Words para .NET: puedes[descarguelo aqui](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: Visual Studio o cualquier IDE compatible con C#.
3. Un documento de Word: específicamente, uno que contiene una TOC.

¿Tienes todo eso? ¡Impresionante! Vamos a rodar.

## Importar espacios de nombres

Lo primero es lo primero, necesitarás importar los espacios de nombres necesarios. Esto es como empacar sus herramientas antes de comenzar un proyecto.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Dividamos este proceso en pasos simples y digeribles. Pasaremos a cargar el documento, modificar las tabulaciones de TOC y guardar el documento actualizado.

## Paso 1: cargue el documento

¿Por qué? Necesitamos acceder al documento de Word que contiene el TOC que queremos modificar.

¿Cómo? Aquí hay un fragmento de código simple para comenzar:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento que contiene la tabla de contenidos.
Document doc = new Document(dataDir + "Table of contents.docx");
```

Imagine que su documento es como un pastel y estamos a punto de agregarle un poco de guinda. El primer paso es sacar ese pastel de la caja.

## Paso 2: identificar los párrafos de la TOC

¿Por qué? Necesitamos identificar los párrafos que componen el TOC. 

¿Cómo? Recorre los párrafos y comprueba sus estilos:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Párrafo TOC encontrado
    }
}
```

Piense en ello como escanear una multitud para encontrar a sus amigos. Aquí, buscamos párrafos con el estilo de entradas TOC.

## Paso 3: modificar las tabulaciones

¿Por qué? Aquí es donde ocurre la magia. Cambiar las tabulaciones le da a su TOC una apariencia más limpia.

¿Cómo? Elimine la tabulación existente y agregue una nueva en una posición modificada:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Es como ajustar los muebles de su sala de estar hasta que se sientan bien. Estamos ajustando esas tabulaciones para que sean perfectas.

## Paso 4: guarde el documento modificado

¿Por qué? Para garantizar que todo su arduo trabajo se guarde y pueda verse o compartirse.

¿Cómo? Guarde el documento con un nuevo nombre para mantener intacto el original:

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

¡Y voilá! Su TOC ahora tiene las tabulaciones exactamente donde las desea.

## Conclusión

Cambiar las tabulaciones de TOC en un documento de Word usando Aspose.Words para .NET es sencillo una vez que lo desglosas. Al cargar su documento, identificar los párrafos de la TOC, modificar las tabulaciones y guardar el documento, puede lograr una apariencia pulida y profesional. Recuerde, la práctica hace la perfección, así que siga experimentando con diferentes posiciones de tabulación para obtener el diseño exacto que desea.

## Preguntas frecuentes

### ¿Puedo modificar las tabulaciones para diferentes niveles de TOC por separado?
¡Sí tu puedes! Simplemente verifique cada nivel de TOC específico (Toc1, Toc2, etc.) y ajústelo en consecuencia.

### ¿Qué pasa si mi documento tiene múltiples TOC?
El código busca todos los párrafos con estilo TOC, por lo que modificará todos los TOC presentes en el documento.

### ¿Es posible agregar varias tabulaciones en una entrada TOC?
 ¡Absolutamente! Puede agregar tantas tabulaciones como necesite ajustando el`para.ParagraphFormat.TabStops` recopilación.

### ¿Puedo cambiar la alineación de la tabulación y el estilo de la directriz?
Sí, puede especificar diferentes alineaciones y estilos de guía al agregar una nueva tabulación.

### ¿Necesito una licencia para usar Aspose.Words para .NET?
 Sí, necesita una licencia válida para utilizar Aspose.Words para .NET más allá del período de prueba. Puedes conseguir un[licencia temporal](https://purchase.aspose.com/temporary-license/) o[compra uno](https://purchase.aspose.com/buy).