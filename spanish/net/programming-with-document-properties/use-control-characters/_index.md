---
title: Usar caracteres de control
linktitle: Usar caracteres de control
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para usar caracteres de control con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/use-control-characters/
---

En este tutorial, lo guiaremos a través del código fuente de C# para usar caracteres de control con Aspose.Words para .NET. Esta característica le permite manipular caracteres de control en el texto.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Usar caracteres de control

En este paso, vamos a utilizar caracteres de control en un texto. Usa el siguiente código:

```csharp
const string text = "test\r";
// Reemplace el carácter de control "\r" con "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Este código define un`text` cadena que contiene el carácter de control "\r" (nueva línea) y utiliza el`Replace` para reemplazarlo con el carácter de control "\r\n" (nueva línea). línea seguida de un salto de línea).

### Ejemplo de código fuente para usar caracteres de control usando Aspose.Words para .NET

```csharp

	const string text = "test\r";
	// Reemplace el carácter de control "\r" con "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Puede usar el código anterior en su propio proyecto reemplazando el`text` cadena con su propio texto que contiene caracteres de control.

Ahora ha aprendido a usar caracteres de control con Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede manipular fácilmente los caracteres de control en sus propias aplicaciones.