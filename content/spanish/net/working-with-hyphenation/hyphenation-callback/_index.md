---
title: Devolución de llamada de separación de palabras
linktitle: Devolución de llamada de separación de palabras
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar la devolución de llamada de separación de palabras en Aspose.Words para .NET para manejar la separación de palabras.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenation-callback/
---

En este tutorial paso a paso, le mostraremos cómo utilizar la función de devolución de llamada de separación de palabras en Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: guardar el recordatorio de separación de palabras

Primero, registraremos la devolución de llamada de separación de palabras usando un archivo personalizado.`CustomHyphenationCallback` clase. Esto nos permitirá manejar la separación de palabras según nuestras propias reglas:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Asegúrese de haber implementado el`CustomHyphenationCallback` clase de acuerdo a sus necesidades específicas.

## Paso 2: cargar el documento y aplicar la separación de palabras

A continuación, cargue su documento desde el directorio especificado y separe las palabras con guiones usando Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Paso 3: Manejo de errores de diccionario faltantes

En caso de que falte un diccionario de separación de palabras, detectaremos la excepción correspondiente y mostraremos un mensaje de error:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Paso 4: Limpiar y desactivar el recordatorio de separación de palabras

Finalmente, por motivos de limpieza y para desactivar el recordatorio de separación de palabras, realice los siguientes pasos:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Esto limpia y desactiva el recordatorio de separación de palabras después de finalizar el procesamiento.

Entonces ! Ha utilizado con éxito la devolución de llamada de separación de palabras en Aspose.Words para .NET.

### Código fuente de muestra para devolución de llamada de separación de palabras con Aspose.Words para .NET

```csharp
try
{
	 // Registre la devolución de llamada con separación de palabras.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Siéntase libre de utilizar este código en sus propios proyectos y modificarlo para adaptarlo a sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Qué es un recordatorio de silabización en Aspose.Words?

R: Un recordatorio de silabización en Aspose.Words es una función que le permite personalizar cómo se silabizan las palabras en sus documentos. Al utilizar un recordatorio de silabización, puede especificar reglas personalizadas para la silabización de palabras, lo que puede ser útil para idiomas específicos o escenarios particulares donde la silabización predeterminada no produce los resultados deseados.

#### P: ¿Cómo configurar un recordatorio de silabización en Aspose.Words?

 R: Para definir una devolución de llamada de separación de palabras en Aspose.Words, necesita crear una clase que implemente la`HyphenationCallback` interfaz e implementar el`HandleWord()` método. Este método se llamará para cada palabra encontrada durante la silabización. Puede aplicarle reglas de silabización personalizadas y devolver la palabra silabizada. Luego puede vincular su devolución de llamada de separación de palabras usando el`Document.HyphenationCallback` propiedad de su documento.

#### P: ¿Cuál es la ventaja de utilizar un recordatorio de silabización en Aspose.Words?

R: El beneficio de utilizar un recordatorio de silabización en Aspose.Words es la capacidad de personalizar cómo se silabizan las palabras en sus documentos. Esto le brinda más control sobre la silabización, especialmente para idiomas o escenarios específicos donde la silabización predeterminada no proporciona los resultados deseados. Podrás aplicar reglas específicas a cada palabra para obtener una silabización precisa según tus necesidades.

#### P: ¿Cuáles son algunos escenarios comunes en los que puede resultar útil utilizar un recordatorio de silabización?

R: Usar un refuerzo de silabización puede resultar útil en varios escenarios, como por ejemplo:
- Silabización de palabras en idiomas específicos que tienen reglas de silabización particulares.
- La aplicación de reglas de silabización personalizadas para siglas o palabras técnicas.
- Adaptación de la silabización según preferencias estilísticas o estándares tipográficos.

#### P: ¿Cómo puedo probar la silabización personalizada con un recordatorio de silabización en Aspose.Words?

R: Para probar la silabización personalizada con un recordatorio de silabización en Aspose.Words, puede crear un documento de prueba que contenga palabras a las que desee aplicar reglas de silabización personalizadas. Luego puede configurar su devolución de llamada de silabización personalizada, llame al`Document.Range.Replace()` método para reemplazar las palabras en el documento y utilizar el`Hyphenate()` método de la`Hyphenation` clase para obtener la silabización de las palabras. Luego puede formatear las palabras con sílabas según sea necesario, por ejemplo agregando guiones entre sílabas.