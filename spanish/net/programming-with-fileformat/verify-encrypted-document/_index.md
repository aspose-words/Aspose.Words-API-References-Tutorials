---
title: Verificar documento cifrado
linktitle: Verificar documento cifrado
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para verificar que un documento esté encriptado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-fileformat/verify-encrypted-document/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función de verificación de documentos cifrados con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo verificar si un documento está encriptado.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Detectar formato de archivo

 A continuación, usamos el`DetectFileFormat` metodo de la`FileFormatUtil` clase para detectar la información de formato de archivo. En este ejemplo, asumimos que el documento cifrado se llama "Encrypted.docx" y se encuentra en el directorio de documentos especificado.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Paso 3: Comprueba si el documento está encriptado

 usamos el`IsEncrypted` propiedad de la`FileFormatInfo` object para verificar si el documento está encriptado. Esta propiedad vuelve`true` si el documento está encriptado, de lo contrario devuelve`false`. Mostramos el resultado en la consola.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Eso es todo ! Ha verificado con éxito si un documento está encriptado usando Aspose.Words para .NET.

### Ejemplo de código fuente para verificar documentos cifrados con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```
