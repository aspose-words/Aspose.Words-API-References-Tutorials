---
title: Detectar formato de arquivo de documento
linktitle: Detectar formato de arquivo de documento
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para detectar o formato de arquivo de documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-fileformat/detect-file-format/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso de detecção de formato de arquivo de documento com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como detectar o formato de diferentes arquivos de documentos.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Etapa 1: definir diretórios

 Para começar, você precisa definir os diretórios onde deseja armazenar os arquivos de acordo com seu formato. Substituir`"YOUR DOCUMENT DIRECTORY"`com o caminho real para o diretório de documentos. Criamos os diretórios "Supported", "Unknown", "Encrypted" e "Pre97" caso ainda não existam.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Crie os diretórios se eles ainda não existirem.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Etapa 2: navegar pelos arquivos

 Então usamos o`GetFiles` método do`Directory` class para obter a lista de arquivos no diretório especificado. Também usamos um`Where` cláusula para excluir um arquivo específico denominado "Documento corrompido.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Passo 3: Detecte o formato de cada arquivo

 Percorremos cada arquivo da lista e usamos o`DetectFileFormat` método do`FileFormatUtil` class para detectar o formato do arquivo. Também exibimos o tipo de documento detectado.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Exibir o tipo de documento
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
// ... Adicione casos para outros formatos de documento suportados
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

Isso é tudo ! Você detectou com sucesso o formato de diferentes arquivos de documentos usando Aspose.Words for .NET.

### Exemplo de código-fonte para detecção de formato de arquivo com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Crie os diretórios se eles ainda não existirem.
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

		// Exibir o tipo de documento
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

### Perguntas frequentes sobre detecção de formato de arquivo de documento

#### Como detectar o formato de um arquivo de documento usando Aspose.Words for .NET?

 Para detectar o formato de um arquivo de documento usando Aspose.Words for .NET, você pode seguir as etapas fornecidas no tutorial. Usando o`DetectFileFormat` método do`FileFormatUtil` class permitirá que você detecte o formato do arquivo do documento. Isso permitirá que você determine se é um documento do Microsoft Word 97-2003, um modelo, um documento Office Open XML WordprocessingML ou outros formatos suportados. O código fornecido no tutorial orientará você na implementação desse recurso.

#### Quais formatos de documento o Aspose.Words for .NET suporta?

Aspose.Words for .NET suporta uma variedade de formatos de documentos, incluindo documentos do Microsoft Word 97-2003 (DOC), modelos (DOT), documentos Office Open XML WordprocessingML (DOCX), documentos Office Open XML WordprocessingML com macros (DOCM), Office Open Modelos XML WordprocessingML sem macros (DOTX), modelos Office Open XML WordprocessingML com macros (DOTM), documentos Flat OPC, documentos RTF, documentos Microsoft Word 2003 WordprocessingML, documentos HTML, documentos MHTML (arquivo da Web), documentos OpenDocument Text (ODT), Modelos OpenDocument Text (OTT), documentos MS Word 6 ou Word 95 e formatos de documentos desconhecidos.

#### Como lidar com arquivos de documentos criptografados durante a detecção de formato?

 Ao detectar o formato de um arquivo de documento, você pode usar o`IsEncrypted` propriedade do`FileFormatInfo` objeto para verificar se o arquivo está criptografado. Se o arquivo estiver criptografado, você poderá executar etapas adicionais para lidar com esse caso específico, como copiar o arquivo para um diretório dedicado a documentos criptografados. Você pode usar o`File.Copy` método para fazer isso.

#### Que ações devem ser tomadas quando o formato de um documento é desconhecido?

Quando o formato de um documento é desconhecido, você pode decidir tratá-lo de uma forma específica para sua aplicação. No exemplo fornecido no tutorial, o documento é copiado para um diretório específico dedicado a documentos de formato desconhecido. Você pode personalizar esta ação para atender às suas necessidades específicas.

#### Existem outros recursos do Aspose.Words for .NET que podem ser usados em conjunto com a detecção de formato de documento?

Sim, Aspose.Words for .NET oferece muitos outros recursos para processamento e manipulação de documentos Word. Por exemplo, você pode usar a biblioteca para extrair texto, imagens ou metadados de documentos, aplicar alterações de formatação, mesclar documentos, converter documentos em diferentes formatos e muito mais.