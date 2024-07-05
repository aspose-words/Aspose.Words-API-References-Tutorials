---
title: Obtenha tipos de revisão de palavras
linktitle: Obtenha tipos de revisão de palavras
second_title: API de processamento de documentos Aspose.Words
description: Obtenha tipos de revisão de palavras em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/get-revision-types/
---

Neste guia passo a passo, mostraremos como obter as revisões dos tipos de palavras em um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

primeiro passo é fazer o upload do documento contendo as revisões.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Etapa 2: percorra os parágrafos

A seguir, percorreremos os parágrafos do documento e verificaremos os tipos de palavras revisões associadas a cada parágrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Exemplo de código-fonte para obter tipos de revisão usando Aspose.Words for .NET

Aqui está o código-fonte completo para obter tipos de revisão em um documento usando Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Conclusão

Neste tutorial, aprendemos como obter as revisões dos tipos de palavras em um documento do Word usando Aspose.Words for .NET. Seguimos os passos para carregar o documento, percorrer os parágrafos e verificar os tipos de revisões de palavras associadas a cada parágrafo. Agora você pode aplicar esse conhecimento para analisar revisões de palavras em seus próprios documentos do Word usando Aspose.Words for .NET.

### Perguntas frequentes para obter tipos de revisão de palavras

#### P: Como fazer upload de um documento no Aspose.Words for .NET?

 R: Use o`Document` classe de Aspose.Words for .NET para carregar um documento de um arquivo. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como faço para percorrer os parágrafos de um documento no Aspose.Words for .NET?

 R: Use o`Paragraphs` propriedade da seção do documento para obter a coleção de parágrafos. Você pode então usar um loop para percorrer cada parágrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Processe cada parágrafo aqui
}
```

#### P: Como verificar se um parágrafo foi movido (excluído) no Aspose.Words for .NET?

 R: Use um parágrafo`IsMoveFromRevision`propriedade para verificar se ela foi movida (excluída).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // O parágrafo foi movido (excluído)
}
```

#### P: Como verificar se um parágrafo foi movido (inserido) no Aspose.Words for .NET?

 R: Use um parágrafo`IsMoveToRevision` propriedade para verificar se ela foi movida (inserida).

```csharp
if (paragraph.IsMoveToRevision)
{
     // O parágrafo foi movido (inserido)
}
```