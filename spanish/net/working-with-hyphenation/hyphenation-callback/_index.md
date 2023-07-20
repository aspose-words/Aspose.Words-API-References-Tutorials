---
title: Devolución de llamada con guión
linktitle: Devolución de llamada con guión
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a usar la devolución de llamada de separación de palabras en Aspose.Words para .NET para manejar la separación de palabras.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenation-callback/
---

En este tutorial paso a paso, le mostraremos cómo usar la función de devolución de llamada de partición en Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: Guarde el recordatorio de división de palabras

Primero, registraremos la devolución de llamada de separación de palabras usando un`CustomHyphenationCallback` clase. Esto nos permitirá manejar la división de palabras según nuestras propias reglas:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Asegúrese de haber implementado el`CustomHyphenationCallback` clase de acuerdo a sus necesidades específicas.

## Paso 2: Cargar el documento y aplicar guiones

A continuación, cargue su documento desde el directorio especificado y divida las palabras usando Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Paso 3: Manejo de errores de diccionario que faltan

En caso de que falte un diccionario de partición de palabras, detectaremos la excepción correspondiente y mostraremos un mensaje de error:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Paso 4: Limpiar y deshabilitar el recordatorio de separación de sílabas

Finalmente, para la limpieza y para desactivar el recordatorio de partición, realice los siguientes pasos:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Esto limpia y deshabilita el recordatorio de partición después de finalizar el procesamiento.

Entonces ! Ha utilizado con éxito la devolución de llamada de partición en Aspose.Words para .NET.

### Ejemplo de código fuente para devolución de llamada con guiones con Aspose.Words para .NET

```csharp
try
{
	 // Registre la devolución de llamada con guión.
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

Siéntase libre de usar este código en sus propios proyectos y modifíquelo para satisfacer sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Qué es un recordatorio de silabeo en Aspose.Words?

R: Un recordatorio de silabeo en Aspose.Words es una característica que le permite personalizar cómo se silabean las palabras en sus documentos. Mediante el uso de un recordatorio de silabeo, puede especificar reglas personalizadas para el silabeo de palabras, lo que puede ser útil para idiomas específicos o escenarios particulares donde el silabeo predeterminado no produce los resultados deseados.

#### P: ¿Cómo configurar un recordatorio de silabeo en Aspose.Words?

 R: Para definir una devolución de llamada de partición en Aspose.Words, debe crear una clase que implemente el`HyphenationCallback` interfaz e implementar el`HandleWord()` método. Este método se llamará para cada palabra encontrada durante el silabeo. Puede aplicarle reglas de silabeo personalizadas y devolver la palabra silabizada. Luego puede vincular su devolución de llamada de separación de palabras usando el`Document.HyphenationCallback` propiedad de su documento.

#### P: ¿Cuál es la ventaja de usar un recordatorio de silabeo en Aspose.Words?

R: El beneficio de usar un recordatorio de silabeo en Aspose.Words es la capacidad de personalizar cómo se silabean las palabras en sus documentos. Esto le da más control sobre el silabeo, especialmente para idiomas o escenarios específicos donde el silabeo predeterminado no da los resultados deseados. Puedes aplicar reglas específicas a cada palabra para obtener un silabeo preciso de acuerdo a tus necesidades.

#### P: ¿Cuáles son algunos escenarios comunes en los que puede ser útil usar un recordatorio de silabeo?

R: El uso de un refuerzo de sílabas puede ser útil en varios escenarios, como:
- Silabeo de palabras en idiomas específicos que tienen reglas particulares de silabeo.
- La aplicación de reglas de silabeo personalizadas para siglas o palabras técnicas.
- Adaptación del silabeo según preferencias estilísticas o normas tipográficas.

#### P: ¿Cómo puedo probar el silabeo personalizado con un recordatorio de silabeo en Aspose.Words?

R: Para probar el silabeo personalizado con un recordatorio de silabeo en Aspose.Words, puede crear un documento de prueba que contenga palabras para las que desea aplicar reglas de silabeo personalizado. Luego puede configurar su devolución de llamada de silabización personalizada, llame al`Document.Range.Replace()` método para reemplazar las palabras en el documento, y use el`Hyphenate()` metodo de la`Hyphenation` clase para obtener el silabeo de las palabras. A continuación, puede dar formato a las palabras divididas en sílabas según sea necesario, por ejemplo, añadiendo guiones entre sílabas.