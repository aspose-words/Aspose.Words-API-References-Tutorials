---
title: Detectar formato de archivo de documento
linktitle: Detectar formato de archivo de documento
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para detectar el formato de archivo de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-fileformat/detect-file-format/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de detección de formato de archivo de documento con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo detectar el formato de diferentes archivos de documentos.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir directorios

 Para comenzar, debe definir los directorios donde desea almacenar los archivos según su formato. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real a su directorio de documentos. Creamos los directorios "Soportado", "Desconocido", "Cifrado" y "Pre97" si aún no existen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Cree los directorios si aún no existen.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Paso 2: Explorar archivos

 Entonces usamos el`GetFiles` metodo de la`Directory` class para obtener la lista de archivos en el directorio especificado. También usamos un`Where` cláusula para excluir un archivo específico llamado "Documento corrupto.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Paso 3: Detecta el formato de cada archivo

 Recorremos cada archivo en la lista y usamos el`DetectFileFormat` metodo de la`FileFormatUtil` class para detectar el formato del archivo. También mostramos el tipo de documento detectado.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Mostrar el tipo de documento
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Agregar casos para otros formatos de documentos compatibles
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

Eso es todo ! Ha detectado con éxito el formato de diferentes archivos de documentos utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para la detección de formato de archivo con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Cree los directorios si aún no existen.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Mostrar el tipo de documento
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### Preguntas frecuentes sobre la detección de formato de archivo de documento

#### ¿Cómo detectar el formato de un archivo de documento usando Aspose.Words para .NET?

 Para detectar el formato de un archivo de documento usando Aspose.Words para .NET, puede seguir los pasos proporcionados en el tutorial. Utilizando el`DetectFileFormat` metodo de la`FileFormatUtil` class le permitirá detectar el formato del archivo del documento. Esto le permitirá determinar si se trata de un documento de Microsoft Word 97-2003, una plantilla, un documento Office Open XML WordprocessingML u otros formatos admitidos. El código provisto en el tutorial lo guiará a través de la implementación de esta característica.

#### ¿Qué formatos de documentos admite Aspose.Words para .NET?

Aspose.Words para .NET admite una variedad de formatos de documentos, incluidos documentos de Microsoft Word 97-2003 (DOC), plantillas (DOT), documentos Office Open XML WordprocessingML (DOCX), documentos Office Open XML WordprocessingML con macros (DOCM), Office Open Plantillas XML WordprocessingML sin macros (DOTX), plantillas Office Open XML WordprocessingML con macros (DOTM), documentos Flat OPC, documentos RTF, documentos Microsoft Word 2003 WordprocessingML, documentos HTML, documentos MHTML (archivo web), documentos OpenDocument Text (ODT), Plantillas de OpenDocument Text (OTT), documentos de MS Word 6 o Word 95 y formatos de documentos desconocidos.

#### ¿Cómo manejar archivos de documentos encriptados durante la detección de formato?

 Al detectar el formato de un archivo de documento, puede utilizar el`IsEncrypted` propiedad de la`FileFormatInfo` object para verificar si el archivo está encriptado. Si el archivo está encriptado, puede tomar medidas adicionales para manejar este caso específico, como copiar el archivo en un directorio dedicado a documentos encriptados. Puedes usar el`File.Copy` método para hacer esto.

#### ¿Qué acciones se deben tomar cuando se desconoce el formato de un documento?

Cuando se desconoce el formato de un documento, puede decidir manejarlo de una manera específica para su aplicación. En el ejemplo proporcionado en el tutorial, el documento se copia en un directorio específico dedicado a documentos de formato desconocido. Puede personalizar esta acción para satisfacer sus necesidades específicas.

#### ¿Existen otras características de Aspose.Words para .NET que se puedan usar junto con la detección de formato de documento?

Sí, Aspose.Words para .NET ofrece muchas otras funciones para procesar y manipular documentos de Word. Por ejemplo, puede usar la biblioteca para extraer texto, imágenes o metadatos de documentos, aplicar cambios de formato, fusionar documentos, convertir documentos a diferentes formatos y más.