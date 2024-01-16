---
title: Mesclar documentos do Word
linktitle: Mesclar documentos
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mesclar vários documentos do Word usando Aspose.Words for .NET. Esta API poderosa simplifica o processo de mesclagem de documentos, tornando-o eficiente e direto.
type: docs
weight: 10
url: /pt/net/split-document/merge-documents/
---

Neste tutorial, orientaremos você sobre como mesclar vários documentos do Word usando o recurso Mesclar Documentos do Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e obter um documento mesclado contendo todos os documentos de origem.

## Etapa 1: procure documentos para mesclar

Antes de mesclar os documentos, precisamos localizar os documentos de origem a serem mesclados. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Procure documentos para mesclar.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Etapa 2: mesclar documentos

Agora iremos mesclar os documentos um por um para criar um documento final mesclado. Veja como:

```csharp
// Abra a primeira parte do documento resultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crie um novo documento resultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Mesclar os documentos um por um.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Exemplo de código-fonte para mesclar documentos usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso Mesclar Documentos do Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Encontre documentos usando para mesclar.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Abra a primeira parte do documento resultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crie um novo documento resultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Mesclar as partes do documento uma por uma.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Conclusão

Parabéns! Você aprendeu como mesclar vários documentos do Word usando o recurso Mesclar Documentos do Aspose.Words for .NET. Seguindo o código-fonte fornecido, você pode combinar documentos separados em um único documento mesclado, preservando a formatação de cada documento de origem.

mesclagem de documentos pode ser útil quando você deseja consolidar informações de diversas fontes ou criar um documento unificado a partir de partes individuais. Aspose.Words for .NET fornece uma API poderosa que simplifica o processo de mesclagem de documentos, tornando-o eficiente e direto.

Sinta-se à vontade para explorar outros recursos oferecidos pelo Aspose.Words for .NET para aprimorar seus recursos de processamento de documentos e agilizar seu fluxo de trabalho.

### Perguntas frequentes

#### Como posso mesclar documentos com formatações diferentes?

 Ao mesclar documentos, Aspose.Words for .NET oferece a opção de preservar a formatação de cada documento de origem. Ao usar o`ImportFormatMode.KeepSourceFormatting` opção, o documento mesclado manterá a formatação dos documentos originais. Se quiser aplicar uma formatação consistente em todo o documento mesclado, você pode modificar a formatação usando a API Aspose.Words após mesclar os documentos.

#### Posso mesclar documentos em formatos diferentes?

Sim, Aspose.Words for .NET oferece suporte à mesclagem de documentos em vários formatos, incluindo DOCX, DOC, RTF e muito mais. Você pode carregar documentos de diferentes formatos na API Aspose.Words e mesclá-los em um único documento, independentemente de seus formatos originais.

#### Posso mesclar documentos com estruturas complexas, como tabelas e imagens?

Absolutamente! Aspose.Words for .NET é capaz de mesclar documentos com estruturas complexas, incluindo tabelas, imagens, cabeçalhos, rodapés e muito mais. A API cuida do processo de fusão preservando a integridade e o layout do conteúdo de cada documento.

#### É possível mesclar documentos com diferentes orientações ou tamanhos de página?

Sim, o Aspose.Words for .NET lida com documentos com diferentes orientações ou tamanhos de página durante o processo de mesclagem. O documento mesclado resultante acomodará as diversas orientações e tamanhos de página dos documentos de origem.