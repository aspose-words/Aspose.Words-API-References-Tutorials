---
title: Detectar numeración con espacios en blanco
linktitle: Detectar numeración con espacios en blanco
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a detectar números de lista con espacios en blanco en Aspose.Words para .NET. Mejora la estructura de tus documentos con facilidad.
type: docs
weight: 10
url: /es/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
En este tutorial, exploraremos el código fuente de C# proporcionado para la función "Detección de numeración con espacios en blanco" con Aspose.Words para .NET. Esta función le permite detectar y crear listas a partir de un documento de texto que contiene números de lista seguidos de espacios en blanco.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Crear el documento de texto

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

En este paso, creamos una cadena de texto que simula un documento de texto que contiene números de lista seguidos de espacios en blanco. Usamos diferentes delimitadores de lista, como punto, corchete derecho, símbolo de viñeta y espacios en blanco.

## Paso 3: configurar las opciones de carga

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 En este paso, configuramos las opciones de carga de documentos. Creamos un nuevo`TxtLoadOptions` objeto y establecer el`DetectNumberingWithWhitespaces` propiedad a`true`. Esto permitirá que Aspose.Words detecte los números de la lista incluso si van seguidos de espacios en blanco.

## Paso 4: Cargar el documento y guardar

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 En este paso, cargamos el documento usando la cadena de texto especificada y las opciones de carga. usamos un`MemoryStream` para convertir la cadena de texto en un flujo de memoria. Luego guardamos el documento resultante en formato .docx.

### Ejemplo de código fuente para la función de detección de numeración de espacios en blanco con Aspose.Words para .NET.

```csharp

            
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Cree un documento de texto sin formato en forma de cadena con partes que puedan interpretarse como listas.
// Al cargar, las tres primeras listas siempre serán detectadas por Aspose.Words,
// y los objetos de lista se crearán para ellos después de la carga.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// La cuarta lista, con espacios en blanco entre el número de la lista y el contenido del elemento de la lista,
// solo se detectará como una lista si "DetectNumberingWithWhitespaces" en un objeto LoadOptions se establece en verdadero,
// para evitar que los párrafos que comienzan con números se detecten erróneamente como listas.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Cargue el documento mientras aplica LoadOptions como parámetro y verifique el resultado.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Ahora puede ejecutar el código fuente para cargar el documento de texto que contiene números de lista con espacios en blanco y luego crear un documento .docx con las listas detectadas. El archivo de salida se guardará en el directorio especificado con el nombre "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusión
En este tutorial, exploramos la función de detección de numeración de espacios en blanco en Aspose.Words para .NET. Aprendimos a crear listas a partir de un documento de texto que contiene números de lista seguidos de espacios en blanco.

Esta característica es extremadamente útil para procesar documentos que contienen números de lista con diferentes formatos. Mediante el uso de las opciones de carga adecuadas, Aspose.Words puede detectar estos números de lista, incluso si van seguidos de espacios en blanco, y convertirlos en listas estructuradas en el documento final.

El uso de esta función puede ahorrarle tiempo y mejorar la eficiencia de su flujo de trabajo. Puede extraer fácilmente información de documentos de texto y convertirlos en documentos bien estructurados con listas adecuadas.

Recuerde considerar las opciones de carga, como configurar la detección de marcado de espacios en blanco, para lograr los resultados deseados.

Aspose.Words para .NET ofrece muchas características avanzadas para la manipulación y generación de documentos. Al explorar más a fondo la documentación y los ejemplos proporcionados por Aspose.Words, podrá aprovechar al máximo las capacidades de esta poderosa biblioteca.

Por lo tanto, no dude en integrar la detección de numeración de espacios en blanco en sus proyectos de Aspose.Words para .NET y aproveche sus beneficios para crear documentos legibles y bien estructurados.


