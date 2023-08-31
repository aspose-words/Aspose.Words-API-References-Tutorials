---
title: Verificar documento de Word cifrado
linktitle: Verificar documento de Word cifrado
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para verificar que un documento de Word esté cifrado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-fileformat/verify-encrypted-document/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función de verificación de documentos de Word cifrados con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo comprobar si un documento está cifrado.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: detectar el formato del archivo

 A continuación, utilizamos el`DetectFileFormat` método de la`FileFormatUtil` clase para detectar la información del formato del archivo. En este ejemplo, asumimos que el documento cifrado se llama "Encrypted.docx" y se encuentra en el directorio de documentos especificado.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Paso 3: comprueba si el documento está cifrado

 Usamos el`IsEncrypted` propiedad de la`FileFormatInfo`objeto para comprobar si el documento está cifrado. Esta propiedad regresa`true` si el documento está cifrado, en caso contrario devuelve`false`. Mostramos el resultado en la consola.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Eso es todo ! Ha comprobado con éxito si un documento está cifrado usando Aspose.Words para .NET.

### Código fuente de ejemplo para verificar documentos cifrados con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Preguntas frecuentes

### P: ¿Cuáles son los pasos para verificar un documento de Word cifrado?

Los pasos para verificar un documento de Word cifrado son los siguientes:

Defina el directorio de documentos.

Detecta el formato del archivo.

Compruebe si el documento está cifrado.

### P: ¿Cómo puedo configurar el directorio de documentos?
 Para configurar el directorio de documentos, debe reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos en el siguiente código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### P: ¿Cómo detectar el formato de archivo?
 Puedes usar el`DetectFileFormat` método de la`FileFormatUtil`clase para detectar información de formato de archivo. En el siguiente ejemplo, asumimos que el documento cifrado se llama "Encrypted.docx" y se encuentra en el directorio de documentos especificado:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### P: ¿Cómo comprobar si el documento está cifrado?
 Puedes usar el`IsEncrypted` propiedad de la`FileFormatInfo`objeto para comprobar si el documento está cifrado. Esta propiedad regresa`true` si el documento está cifrado, en caso contrario devuelve`false`. El resultado se muestra en la consola:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### P: ¿Cómo comprobar si un documento está cifrado utilizando Aspose.Words para .NET?
Si sigue los pasos mencionados en este tutorial y ejecuta el código fuente proporcionado, puede verificar si un documento está cifrado usando Aspose.Words para .NET.
