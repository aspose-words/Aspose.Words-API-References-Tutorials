---
title: Acesse a versão revisada
linktitle: Acesse a versão revisada
second_title: API de processamento de documentos Aspose.Words
description: Acesse uma versão revisada de um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/access-revised-version/
---

Neste guia passo a passo, mostraremos como acessar a versão revisada de um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

O primeiro passo é fazer o upload do documento contendo as revisões.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Passo 2: Acesse a versão revisada

Passaremos agora para a versão revisada do documento.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Etapa 3: navegar pelas revisões

A seguir, percorreremos as revisões presentes no documento e exibiremos informações específicas para parágrafos que são itens de lista.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Exemplo de código-fonte para Access Revised Version usando Aspose.Words for .NET

Aqui está o código-fonte completo para acessar a versão revisada de um documento usando Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Mude para a versão revisada do documento.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Conclusão

Neste tutorial, aprendemos como acessar a versão revisada de um documento do Word usando Aspose.Words for .NET. Ao carregar o documento, navegar até a versão revisada e navegar pelas revisões, conseguimos obter informações específicas para parágrafos que são itens de lista. Aspose.Words for .NET oferece recursos poderosos para manipulação de documentos do Word, incluindo acesso a revisões. Agora você pode usar esse conhecimento para acessar a versão revisada de seus próprios documentos do Word usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como carrego um documento com revisões no Aspose.Words for .NET?

 R: Use o`Document`classe de Aspose.Words for .NET para carregar um documento de um arquivo contendo revisões. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como faço para acessar a versão revisada de um documento no Aspose.Words for .NET?

 R: Use o`RevisionsView` propriedade do`Document` objeto para acessar a versão revisada do documento. Você pode definir o valor do`RevisionsView`propriedade para`RevisionsView.Final` para mostrar a versão final sem as revisões.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### P: Como procuro revisões de documentos no Aspose.Words for .NET?

 R: Use um`foreach` loop para iterar pelas revisões presentes no documento. Você pode usar o`Revisions` propriedade do`Document` objeto para obter uma coleção de todas as revisões do documento.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Processe cada revisão aqui
}
```

#### P: Como verificar se um parágrafo é um item de lista no Aspose.Words for .NET?

 R: Use o`IsListItem` propriedade do`Paragraph` objeto para verificar se um parágrafo é um item da lista. O`IsListItem` devoluções de propriedade`true` se o parágrafo for um item de lista, caso contrário ele retornará`false`.

```csharp
if (paragraph.IsListItem)
{
     // O parágrafo é um item da lista
}
else
{
     // O parágrafo não é um item da lista
}
```