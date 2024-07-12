---
title: Copiar texto marcado em documento do Word
linktitle: Copiar texto marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Copie facilmente texto marcado entre documentos do Word usando Aspose.Words for .NET. Aprenda como com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Introdução

Você já precisou copiar seções específicas de um documento do Word para outro? Bem, você está com sorte! Neste tutorial, orientaremos você sobre como copiar texto marcado como favorito de um documento do Word para outro usando Aspose.Words for .NET. Esteja você criando um relatório dinâmico ou automatizando a geração de documentos, este guia simplificará o processo para você.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Biblioteca Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Ambiente de Desenvolvimento: Visual Studio ou qualquer outro ambiente de desenvolvimento .NET.
- Conhecimento básico de C#: Familiaridade com programação C# e framework .NET.

## Importar namespaces

Para começar, certifique-se de ter os namespaces necessários importados em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Etapa 1: carregar o documento de origem

Em primeiro lugar, você precisa carregar o documento de origem que contém o texto marcado que deseja copiar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Aqui,`dataDir` é o caminho para o diretório do seu documento e`Bookmarks.docx` é o documento de origem.

## Etapa 2: Identifique o marcador

A seguir, identifique o marcador que deseja copiar do documento de origem.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Substituir`"MyBookmark1"` com o nome real do seu favorito.

## Etapa 3: Crie o documento de destino

Agora, crie um novo documento onde o texto marcado será copiado.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Etapa 4: importar conteúdo marcado como favorito

 Para garantir que os estilos e a formatação sejam preservados, use`NodeImporter` para importar o conteúdo marcado do documento de origem para o documento de destino.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Etapa 5: definir o método AppendBookmarkedText

É aqui que a mágica acontece. Defina um método para lidar com a cópia do texto marcado:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Etapa 6: salve o documento de destino

Por fim, salve o documento de destino para verificar o conteúdo copiado.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Conclusão

E é isso! Você copiou com sucesso o texto marcado de um documento do Word para outro usando Aspose.Words for .NET. Este método é poderoso para automatizar tarefas de manipulação de documentos, tornando seu fluxo de trabalho mais eficiente e ágil.

## Perguntas frequentes

### Posso copiar vários favoritos de uma vez?
Sim, você pode percorrer vários marcadores e usar o mesmo método para copiar cada um deles.

### O que acontece se o marcador não for encontrado?
 O`Range.Bookmarks` propriedade retornará`null`, portanto, certifique-se de lidar com esse caso para evitar exceções.

### Posso preservar a formatação do marcador original?
 Absolutamente! Usando`ImportFormatMode.KeepSourceFormatting` garante que a formatação original seja preservada.

### Existe um limite para o tamanho do texto marcado?
Não há limite específico, mas o desempenho pode variar com documentos extremamente grandes.

### Posso copiar texto entre diferentes formatos de documentos do Word?
Sim, Aspose.Words oferece suporte a vários formatos do Word e o método funciona nesses formatos.