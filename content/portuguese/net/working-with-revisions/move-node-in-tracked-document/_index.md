---
title: Mover nó no documento rastreado
linktitle: Mover nó no documento rastreado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mover nós em um documento do Word rastreado usando Aspose.Words for .NET com nosso guia passo a passo detalhado. Perfeito para desenvolvedores.
type: docs
weight: 10
url: /pt/net/working-with-revisions/move-node-in-tracked-document/
---
## Introdução

Olá, entusiastas do Aspose.Words! Se você já precisou mover um nó em um documento do Word enquanto rastreava revisões, você está no lugar certo. Hoje, estamos nos aprofundando em como conseguir isso usando Aspose.Words for .NET. Você não apenas aprenderá o processo passo a passo, mas também aprenderá algumas dicas e truques para tornar a manipulação de documentos fácil e eficiente.

## Pré-requisitos

Antes de sujarmos as mãos com algum código, vamos ter certeza de que você tem tudo o que precisa:

-  Aspose.Words para .NET: Faça o download[aqui](https://releases.aspose.com/words/net/).
- Ambiente .NET: certifique-se de ter um ambiente de desenvolvimento .NET compatível configurado.
- Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento básico de C#.

Tem tudo? Ótimo! Vamos passar para os namespaces que precisamos importar.

## Importar namespaces

Em primeiro lugar, precisamos importar os namespaces necessários. Eles são essenciais para trabalhar com Aspose.Words e lidar com nós de documentos.

```csharp
using Aspose.Words;
using System;
```

Tudo bem, vamos dividir o processo em etapas gerenciáveis. Cada etapa será explicada em detalhes para garantir que você entenda o que está acontecendo em cada ponto.

## Etapa 1: inicializar o documento

 Para começar, precisamos inicializar um novo documento e usar um`DocumentBuilder` para adicionar alguns parágrafos.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Adicionando alguns parágrafos
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Verifique a contagem inicial de parágrafos
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Etapa 2: comece a rastrear revisões

Em seguida, precisamos começar a rastrear as revisões. Isto é crucial porque nos permite ver as alterações feitas no documento.

```csharp
// Comece a rastrear revisões
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Etapa 3: mover nós

Agora vem a parte central da nossa tarefa: mover um nó de um local para outro. Moveremos o terceiro parágrafo e o colocaremos antes do primeiro parágrafo.

```csharp
// Defina o nó a ser movido e seu intervalo final
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Mova os nós dentro do intervalo definido
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Etapa 4: parar de rastrear revisões

Depois de movermos os nós, precisamos parar de rastrear as revisões.

```csharp
// Pare de rastrear revisões
doc.StopTrackRevisions();
```

## Etapa 5: salve o documento

Finalmente, vamos salvar nosso documento modificado no diretório especificado.

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Produza a contagem final de parágrafos
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Conclusão

E aí está! Você moveu com sucesso um nó em um documento rastreado usando Aspose.Words for .NET. Esta poderosa biblioteca facilita a manipulação programática de documentos do Word. Esteja você criando, editando ou rastreando alterações, o Aspose.Words tem o que você precisa. Então, vá em frente e experimente. Boa codificação!

## Perguntas frequentes

### O que é Aspose.Words para .NET?

Aspose.Words for .NET é uma biblioteca de classes para trabalhar programaticamente com documentos do Word. Ele permite que os desenvolvedores criem, editem, convertam e imprimam documentos do Word em aplicativos .NET.

### Como faço para rastrear revisões em um documento do Word usando Aspose.Words?

 Para rastrear revisões, use o`StartTrackRevisions` método no`Document` objeto. Isso permitirá o rastreamento de revisões, mostrando quaisquer alterações feitas no documento.

### Posso mover vários nós em Aspose.Words?

Sim, você pode mover vários nós iterando sobre eles e usando métodos como`InsertBefore` ou`InsertAfter` para colocá-los no local desejado.

### Como faço para parar de rastrear revisões no Aspose.Words?

 Use o`StopTrackRevisions` método no`Document` objeto para parar de rastrear revisões.

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?

 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/words/net/).