---
title: Usar caracteres de control
linktitle: Usar caracteres de control
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para usar caracteres de control con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/use-control-characters/
---

En este tutorial, lo guiaremos a través del código fuente de C# para usar caracteres de control con Aspose.Words para .NET. Esta característica le permite manipular caracteres de control en el texto.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: usar personajes de control

En este paso, usaremos caracteres de control en un texto. Utilice el siguiente código:

```csharp
const string text = "test\r";
// Reemplace el carácter de control "\r" por "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Este código define un`text` cadena que contiene el carácter de control "\r" (nueva línea) y utiliza el`Replace` método para reemplazarlo con el carácter de control "\r\n" (nueva línea). línea seguida de un salto de línea).

### Código fuente de ejemplo para usar caracteres de control usando Aspose.Words para .NET

```csharp

	const string text = "test\r";
	// Reemplace el carácter de control "\r" por "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Puede utilizar el código anterior en su propio proyecto reemplazando el`text` cadena con su propio texto que contiene caracteres de control.

Ahora ha aprendido a utilizar caracteres de control con Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, podrá manipular fácilmente los caracteres de control en sus propias aplicaciones.