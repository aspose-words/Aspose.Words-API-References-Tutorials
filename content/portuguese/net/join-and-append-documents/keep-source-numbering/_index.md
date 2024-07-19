---
title: Mantenha a numeração da fonte
linktitle: Mantenha a numeração da fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como importar documentos preservando a formatação usando Aspose.Words for .NET. Guia passo a passo com exemplos de código.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/keep-source-numbering/
---
## Introdução

 Ao trabalhar com Aspose.Words for .NET, a importação de documentos de uma fonte para outra enquanto preserva a formatação pode ser tratada de forma eficiente usando o`NodeImporter` aula. Este tutorial irá guiá-lo através do processo passo a passo.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:
- Visual Studio instalado em sua máquina.
-  Aspose.Words para .NET instalado. Se não, baixe-o em[aqui](https://releases.aspose.com/words/net/).
- Conhecimento básico de programação C# e .NET.

## Importar namespaces

Primeiro, inclua os namespaces necessários em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Etapa 1: configure seu projeto

Comece criando um novo projeto C# no Visual Studio e instale o Aspose.Words por meio do NuGet Package Manager.

## Etapa 2: inicializar documentos
Crie instâncias da origem (`srcDoc`) e destino (`dstDoc`) documentos.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: configurar opções de importação
Configure opções de importação para manter a formatação original, incluindo parágrafos numerados.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Etapa 4: importar parágrafos
Itere pelos parágrafos do documento de origem e importe-os para o documento de destino.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Etapa 5: salve o documento
Salve o documento mesclado no local desejado.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Conclusão

 Concluindo, usar Aspose.Words for .NET para importar documentos enquanto preserva a formatação é simples com o`NodeImporter` aula. Este método garante que seus documentos mantenham perfeitamente sua aparência e estrutura originais.

## Perguntas frequentes

### Posso importar documentos com diferentes estilos de formatação?
 Sim o`NodeImporter` classe suporta a importação de documentos com estilos de formatação variados.

### E se meus documentos contiverem tabelas e imagens complexas?
Aspose.Words for .NET lida com estruturas complexas como tabelas e imagens durante operações de importação.

### O Aspose.Words é compatível com todas as versões do .NET?
Aspose.Words oferece suporte às versões .NET Framework e .NET Core para integração perfeita.

### Como posso lidar com erros durante a importação de documentos?
Use blocos try-catch para lidar com exceções que podem ocorrer durante o processo de importação.

### Onde posso encontrar documentação mais detalhada sobre Aspose.Words for .NET?
 Visite a[documentação](https://reference.aspose.com/words/net/) para guias abrangentes e referências de API.
