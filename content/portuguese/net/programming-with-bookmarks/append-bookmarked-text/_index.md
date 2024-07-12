---
title: Anexar texto marcado em documento do Word
linktitle: Anexar texto marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar texto marcado em um documento do Word usando Aspose.Words for .NET com este guia passo a passo. Perfeito para desenvolvedores.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/append-bookmarked-text/
---
## Introdução

Ei! Você já tentou anexar texto de uma seção marcada em um documento do Word e achou complicado? Você está com sorte! Este tutorial irá guiá-lo através do processo usando Aspose.Words for .NET. Vamos dividi-lo em etapas simples para que você possa acompanhar facilmente. Vamos mergulhar e adicionar aquele texto marcado como um profissional!

## Pré-requisitos

Antes de começarmos, vamos ter certeza de que você tem tudo o que precisa:

-  Aspose.Words for .NET: Certifique-se de tê-lo instalado. Se não, você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: qualquer ambiente de desenvolvimento .NET como Visual Studio.
- Conhecimento básico de C#: Compreender os conceitos básicos de programação em C# ajudará.
- Documento do Word com marcadores: um documento do Word com marcadores configurados, que usaremos para anexar texto.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso garantirá que tenhamos todas as ferramentas de que precisamos ao nosso alcance.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Vamos dividir o exemplo em etapas detalhadas.

## Etapa 1: carregar o documento e inicializar as variáveis

Tudo bem, vamos começar carregando nosso documento Word e inicializando as variáveis que precisaremos.

```csharp
// Carregue os documentos de origem e destino.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Inicialize o importador de documentos.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Encontre o marcador no documento de origem.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Etapa 2: identificar os parágrafos iniciais e finais

Agora, vamos localizar os parágrafos onde o marcador começa e termina. Isto é crucial porque precisamos lidar com o texto dentro desses limites.

```csharp
// Este é o parágrafo que contém o início do marcador.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Este é o parágrafo que contém o final do marcador.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Etapa 3: validar os pais do parágrafo

Precisamos garantir que os parágrafos inicial e final tenham o mesmo pai. Este é um cenário simples para manter as coisas simples.

```csharp
// Limitamo-nos a um cenário razoavelmente simples.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Etapa 4: Identifique o nó a ser interrompido

A seguir, precisamos determinar o nó onde pararemos de copiar o texto. Este será o nó imediatamente após o parágrafo final.

```csharp
// Queremos copiar todos os parágrafos desde o parágrafo inicial até (e incluindo) o parágrafo final,
// portanto, o nó no qual paramos é aquele após o parágrafo final.
Node endNode = endPara.NextSibling;
```

## Etapa 5: anexar texto marcado ao documento de destino

Finalmente, vamos percorrer os nós do parágrafo inicial até o nó após o parágrafo final e anexá-los ao documento de destino.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Isso cria uma cópia do nó atual e o importa (torna-o válido) no contexto
    // do documento de destino. Importar significa ajustar estilos e identificadores de lista corretamente.
    Node newNode = importer.ImportNode(curNode, true);

    // Anexe o nó importado ao documento de destino.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Salve o documento de destino com o texto anexado.
dstDoc.Save("appended_document.docx");
```

## Conclusão

E aí está! Você anexou com êxito o texto de uma seção marcada em um documento do Word usando Aspose.Words for .NET. Essa ferramenta poderosa facilita muito a manipulação de documentos e agora você tem mais um truque na manga. Boa codificação!

## Perguntas frequentes

### Posso anexar texto de vários marcadores de uma só vez?
Sim, você pode repetir o processo para cada marcador e anexar o texto de acordo.

### E se os parágrafos inicial e final tiverem pais diferentes?
exemplo atual pressupõe que eles tenham o mesmo pai. Para pais diferentes, é necessário um tratamento mais complexo.

### Posso manter a formatação original do texto anexado?
 Absolutamente! O`ImportFormatMode.KeepSourceFormatting` garante que a formatação original seja preservada.

### É possível acrescentar texto a uma posição específica no documento de destino?
Sim, você pode anexar o texto a qualquer posição navegando até o nó desejado no documento de destino.

### E se eu precisar anexar texto de um marcador a uma nova seção?
Você pode criar uma nova seção no documento de destino e anexar o texto lá.