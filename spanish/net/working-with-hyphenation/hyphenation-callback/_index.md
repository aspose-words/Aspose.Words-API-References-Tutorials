---
title: Devolución de llamada con guión
linktitle: Devolución de llamada con guión
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar la devolución de llamada de separación de palabras en Aspose.Words para .NET para manejar la separación de palabras.
type: docs
weight: 10
url: /es/net/working-with-hyphenation/hyphenation-callback/
---

En este tutorial paso a paso, le mostraremos cómo usar la función de devolución de llamada de partición en Aspose.Words para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde el sitio oficial.

## Paso 1: Guarde el recordatorio de división de palabras

 Primero, registraremos la devolución de llamada de separación de palabras usando un`CustomHyphenationCallback` clase. Esto nos permitirá manejar la división de palabras según nuestras propias reglas:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Asegúrese de haber implementado el`CustomHyphenationCallback`clase de acuerdo a sus necesidades específicas.

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