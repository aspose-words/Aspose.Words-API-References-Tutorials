---
title: Devolución de llamada de separación de palabras
linktitle: Devolución de llamada de separación de palabras
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a implementar la devolución de llamada de separación de palabras en Aspose.Words para .NET para mejorar el formato de documentos con esta guía completa paso a paso.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenation-callback/
---

## Introducción

¡Hola! ¿Alguna vez te has visto enredado en las complejidades del formato de texto, especialmente cuando se trata de idiomas que requieren separación de palabras? No estás solo. La separación de sílabas, si bien es crucial para el diseño adecuado del texto, puede ser un dolor de cabeza. ¿Pero adivina que? Aspose.Words para .NET te respalda. Esta poderosa biblioteca le permite administrar el formato de texto sin problemas, incluido el manejo de la separación de palabras a través de un mecanismo de devolución de llamada. ¿Intrigado? Profundicemos en el meollo de la cuestión de cómo implementar una devolución de llamada con separación de palabras utilizando Aspose.Words para .NET.

## Requisitos previos

Antes de ensuciarnos las manos con el código, asegurémonos de que tienes todo lo que necesitas:

1.  Aspose.Words para .NET: asegúrese de tener la biblioteca. Puede[descarguelo aqui](https://releases.aspose.com/words/net/).
2. IDE: un entorno de desarrollo como Visual Studio.
3. Conocimientos básicos de C#: comprensión de C# y .NET framework.
4. Diccionarios de separación de sílabas: diccionarios de separación de sílabas para los idiomas que planea utilizar.
5.  Licencia Aspose: Una licencia Aspose válida. Puedes conseguir un[licencia temporal](https://purchase.aspose.com/temporary-license/) si no tienes uno.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Esto garantiza que nuestro código tenga acceso a todas las clases y métodos que necesitamos de Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Paso 1: registre la devolución de llamada con sílabas

Para comenzar, necesitamos registrar nuestra devolución de llamada de separación de palabras. Aquí es donde le decimos a Aspose.Words que use nuestra lógica de separación de palabras personalizada.

```csharp
try
{
    // Registre la devolución de llamada con separación de palabras.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Aquí, estamos creando una instancia de nuestra devolución de llamada personalizada y asignándola a`Hyphenation.Callback`.

## Paso 2: definir la ruta del documento

A continuación, debemos definir el directorio donde se almacenan nuestros documentos. Esto es crucial ya que cargaremos y guardaremos documentos desde esta ruta.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a sus documentos.

## Paso 3: cargue el documento

Ahora, carguemos el documento que requiere separación de palabras.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 Aquí, estamos cargando un documento de texto en alemán. puedes reemplazar`"German text.docx"` con el nombre de archivo de su documento.

## Paso 4: guarde el documento

Después de cargar el documento, lo guardamos en un archivo nuevo, aplicando la devolución de llamada de separación de palabras en el proceso.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Esta línea guarda el documento como PDF con separación de palabras aplicada.

## Paso 5: Manejar la excepción del diccionario de separación de palabras que falta

A veces, es posible que te encuentres con un problema en el que falta el diccionario de separación de palabras. Manejemos eso.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

En este bloque, detectamos la excepción específica relacionada con los diccionarios que faltan e imprimimos el mensaje.

## Paso 6: Implementar la clase de devolución de llamada de separación de palabras personalizada

 Ahora, implementemos el`CustomHyphenationCallback` clase que maneja la solicitud de diccionarios de separación de palabras.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Registrar diccionario para el idioma solicitado.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 En esta clase, el`RequestDictionary` Se llama al método siempre que se necesita un diccionario de separación de palabras. Comprueba el idioma y registra el diccionario apropiado.

## Conclusión

¡Y ahí lo tienes! Acaba de aprender cómo implementar una devolución de llamada con separación de palabras en Aspose.Words para .NET. Si sigue estos pasos, podrá asegurarse de que sus documentos tengan un formato atractivo, independientemente del idioma. Ya sea que trabaje con inglés, alemán o cualquier otro idioma, este método le permite manejar la separación de palabras sin esfuerzo.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una potente biblioteca de manipulación de documentos que permite a los desarrolladores crear, modificar y convertir documentos mediante programación.

### ¿Por qué es importante la separación de palabras en el formato de documentos?
La separación de palabras mejora el diseño del texto al dividir las palabras en los lugares apropiados, lo que garantiza un documento más legible y visualmente atractivo.

### ¿Puedo utilizar Aspose.Words gratis?
 Aspose.Words ofrece una prueba gratuita. Puedes conseguirlo[aquí](https://releases.aspose.com/).

### ¿Cómo obtengo un diccionario de separación de palabras?
Puede descargar diccionarios de separación de palabras de varios recursos en línea o crear los suyos propios si es necesario.

### ¿Qué sucede si falta un diccionario de separación de palabras?
 Si falta un diccionario, el`RequestDictionary` El método genera una excepción, que puede manejar para informar al usuario o proporcionar una alternativa.