---
title: Mover nó no documento rastreado
linktitle: Mover nó no documento rastreado
second_title: API de processamento de documentos Aspose.Words
description: Mova nós em um documento rastreado com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/move-node-in-tracked-document/
---

Neste guia passo a passo, orientaremos você sobre como mover um nó em um documento do Word rastreado usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Criando o documento

O primeiro passo é criar um novo documento e adicionar parágrafos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Etapa 2: acompanhar as revisões

Vamos habilitar o rastreamento de revisão no documento.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Etapa 3: mover um nó

Moveremos um nó (parágrafo) de uma posição para outra enquanto geramos revisões.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Etapa 4: parar de rastrear avaliações

Pararemos de rastrear revisões no documento.

```csharp
doc.StopTrackRevisions();
```

## Passo 5: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save`método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Exemplo de código-fonte para mover nó em documento rastreado usando Aspose.Words for .NET

Aqui está o código-fonte completo para mover um nó em um documento rastreado usando Aspose.Words for .NET:


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Comece a rastrear revisões.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Gere revisões ao mover um nó de um local para outro.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Interrompa o processo de rastreamento de revisões.
doc.StopTrackRevisions();

// Existem 3 parágrafos adicionais na faixa de mudança.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Conclusão

Neste tutorial, aprendemos como mover um nó em um documento Word rastreado usando Aspose.Words for .NET. Seguindo as etapas de criação do documento, habilitando o rastreamento de revisão, movendo o nó e interrompendo o rastreamento de revisão, conseguimos realizar essa manipulação com sucesso. Aspose.Words for .NET é uma ferramenta poderosa para processamento de palavras com documentos Word e oferece recursos avançados para gerenciamento de revisões. Agora você pode usar esse conhecimento para mover nós em seus próprios documentos do Word enquanto rastreia revisões usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como posso ativar o rastreamento de revisão em um documento Aspose.Words for .NET?

 R: Para ativar o rastreamento de revisão em um documento Aspose.Words for .NET, você pode usar o`StartTrackRevisions` método do`Document` objeto. Este método toma como parâmetros o nome do autor das revisões e a data de início do acompanhamento das revisões.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### P: Como posso mover um nó em um documento controlado sem gerar revisões?

 R: Se quiser mover um nó em um documento rastreado sem gerar revisões, você pode usar o`Remove` e`InsertAfter` ou`InsertBefore` métodos do`Node` objeto. Por exemplo, para mover um parágrafo após outro parágrafo, você pode usar o seguinte código:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### P: Como posso interromper o rastreamento de revisão em um documento Aspose.Words for .NET?

 R: Para parar de rastrear revisões em um documento Aspose.Words for .NET, você pode usar o`StopTrackRevisions` método do`Document` objeto.

```csharp
doc.StopTrackRevisions();
```