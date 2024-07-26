---
title: Aplicar bordes y sombreado al párrafo en un documento de Word
linktitle: Aplicar bordes y sombreado al párrafo en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aplique bordes y sombreado a párrafos en documentos de Word usando Aspose.Words para .NET. Siga nuestra guía paso a paso para mejorar el formato de su documento.
type: docs
weight: 10
url: /es/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Introducción

Hola, ¿alguna vez te has preguntado cómo hacer que tus documentos de Word destaquen con bordes y sombreados elegantes? Bueno, ¡estás en el lugar correcto! Hoy nos sumergimos en el mundo de Aspose.Words para .NET para darle vida a nuestros párrafos. Imagine que su documento luzca tan elegante como el trabajo de un diseñador profesional con sólo unas pocas líneas de código. ¿Listo para comenzar? ¡Vamos!

## Requisitos previos

Antes de arremangarnos y sumergirnos en la codificación, asegurémonos de tener todo lo que necesitamos. Aquí está su lista de verificación rápida:

-  Aspose.Words para .NET: Es necesario tener instalada esta biblioteca. Puedes descargarlo desde el[Aspose sitio web](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: Visual Studio o cualquier otro IDE que admita .NET.
- Conocimientos básicos de C#: lo suficiente para comprender y modificar los fragmentos de código.
- Una licencia válida: ya sea una[licencia temporal](https://purchase.aspose.com/temporary-license/) o uno comprado en[asponer](https://purchase.aspose.com/buy).

## Importar espacios de nombres

Antes de saltar al código, debemos asegurarnos de tener los espacios de nombres necesarios importados a nuestro proyecto. Esto hace que todas las funciones interesantes de Aspose.Words sean accesibles para nosotros.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Ahora, dividamos el proceso en pasos breves. Cada paso tendrá un encabezado y una explicación detallada. ¿Listo? ¡Vamos!

## Paso 1: configure su directorio de documentos

Lo primero es lo primero, necesitamos un lugar para guardar nuestro documento bellamente formateado. Establezcamos la ruta a su directorio de documentos.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Este directorio es donde se guardará su documento final. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real en su máquina.

## Paso 2: cree un nuevo documento y DocumentBuilder

 A continuación, necesitamos crear un nuevo documento y un`DocumentBuilder` objeto. El`DocumentBuilder` es nuestra varita mágica que nos permite manipular el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 El`Document` objeto representa todo nuestro documento de Word, y el`DocumentBuilder` nos ayuda a agregar y formatear contenido.

## Paso 3: definir los bordes de los párrafos

Ahora, agreguemos algunos bordes elegantes a nuestro párrafo. Definiremos la distancia desde el texto y estableceremos diferentes estilos de borde.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Aquí establecemos una distancia de 20 puntos entre el texto y los bordes. Los bordes de todos los lados (izquierdo, derecho, superior, inferior) están configurados como líneas dobles. Fantasía, ¿verdad?

## Paso 4: aplicar sombreado al párrafo

Los bordes son geniales, pero vayamos un paso más allá con un poco de sombreado. Usaremos un patrón de cruz diagonal con una combinación de colores para que nuestro párrafo se destaque.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

En este paso, aplicamos una textura cruzada diagonal con coral claro como color de fondo y salmón claro como color de primer plano. ¡Es como vestir tu párrafo con ropa de diseñador!

## Paso 5: agregue texto al párrafo

¿Qué es un párrafo sin texto? Agreguemos una oración de muestra para ver nuestro formato en acción.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Esta línea inserta nuestro texto en el documento. Simple, pero ahora está envuelto en un marco elegante y un fondo sombreado.

## Paso 6: guarde el documento

Finalmente, es hora de salvar nuestro trabajo. Guardemos el documento en el directorio especificado con un nombre descriptivo.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Esto guarda nuestro documento con el nombre.`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` en el directorio que especificamos anteriormente.

## Conclusión

¡Y ahí lo tienes! Con solo unas pocas líneas de código, hemos transformado un párrafo simple en un contenido visualmente atractivo. Aspose.Words para .NET hace que sea increíblemente fácil agregar formato de aspecto profesional a sus documentos. Ya sea que estés preparando un informe, una carta o cualquier documento, estos trucos te ayudarán a causar una gran impresión. ¡Así que adelante, pruébalo y observa cómo tus documentos cobran vida!

## Preguntas frecuentes

### ¿Puedo usar diferentes estilos de línea para cada borde?  
 ¡Absolutamente! Aspose.Words para .NET le permite personalizar cada borde individualmente. Simplemente configura el`LineStyle` para cada tipo de borde como se muestra en la guía.

### ¿Qué otras texturas de sombreado están disponibles?  
 Hay varias texturas que puede utilizar, como sólida, raya horizontal, raya vertical y más. Comprobar el[Asponer documentación](https://reference.aspose.com/words/net/) para obtener una lista completa.

### ¿Cómo puedo cambiar el color del borde?  
 Puede establecer el color del borde usando el`Color` propiedad para cada frontera. Por ejemplo,`borders[BorderType.Left].Color = Color.Red;`.

### ¿Es posible aplicar bordes y sombreado a una parte específica del texto?  
 Sí, puedes aplicar bordes y sombreado a tiradas de texto específicas usando el`Run` objeto dentro del`DocumentBuilder`.

### ¿Puedo automatizar este proceso para varios párrafos?  
¡Definitivamente! Puede recorrer sus párrafos y aplicar los mismos bordes y configuraciones de sombreado mediante programación.
