---
title: Copiar texto marcado em documento do Word
linktitle: Copiar texto marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como copiar o texto do marcador em um documento do Word para outro documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/copy-bookmarked-text/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Copiar texto marcado como favorito na biblioteca Aspose.Words for .NET. Este recurso permite copiar o conteúdo de um marcador específico de um documento de origem para outro documento.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Carregando o documento de origem

 Antes de copiar o texto do marcador, precisamos carregar o documento de origem em um`Document` objeto usando o caminho do arquivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Etapa 2: obter o marcador de origem

 Nós usamos o`Bookmarks` propriedade do intervalo do documento de origem para obter o marcador específico que queremos copiar:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Etapa 3: Criando o documento de destino

Criamos um novo documento que servirá como documento de destino para copiar o conteúdo do marcador:

```csharp
Document dstDoc = new Document();
```

## Etapa 4: especificando o local da cópia

Especificamos o local onde queremos adicionar o texto copiado. No nosso exemplo, adicionamos o texto ao final do corpo da última seção do documento de destino:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Etapa 5: importar e copiar o texto do marcador

 Usamos um`NodeImporter`objeto para importar e copiar o texto do marcador de um documento de origem para o documento de destino:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Exemplo de código-fonte para copiar texto marcado como favorito usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a cópia de texto de um marcador usando Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Este é o marcador cujo conteúdo queremos copiar.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Estaremos adicionando a este documento.
	Document dstDoc = new Document();

	// Digamos que seremos anexados ao final do corpo da última seção.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Se você importar várias vezes sem um único contexto, isso resultará na criação de muitos estilos.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### Código-fonte AppendBookmarkedText

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Este é o parágrafo que contém o início do marcador.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Este é o parágrafo que contém o final do marcador.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Limitamo-nos a um cenário razoavelmente simples.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Queremos copiar todos os parágrafos desde o parágrafo inicial até (e incluindo) o parágrafo final,
            // portanto, o nó no qual paramos é aquele após o parágrafo final.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Isso cria uma cópia do nó atual e o importa (torna-o válido) no contexto
                // do documento de destino. Importar significa ajustar estilos e identificadores de lista corretamente.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Copiar texto marcado como favorito de Aspose.Words para .NET. Seguimos um guia passo a passo para copiar o conteúdo de um marcador de um documento de origem para outro documento.

### Perguntas frequentes para copiar texto marcado em documento do Word

#### P: Quais são os requisitos para usar o recurso "Copiar texto com marcadores" no Aspose.Words for .NET?

R: Para usar o recurso "Copiar texto com marcadores" no Aspose.Words for .NET, você precisa ter conhecimento básico da linguagem C#. Você também precisa de um ambiente de desenvolvimento .NET com a biblioteca Aspose.Words instalada.

#### P: Como carrego um documento de origem no Aspose.Words for .NET?

 R: Para carregar um documento de origem no Aspose.Words for .NET, você pode usar o`Document` class especificando o caminho do arquivo do documento. Aqui está um exemplo de código:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### P: Como obter o conteúdo de um marcador específico em um documento de origem usando Aspose.Words for .NET?

 R: Para obter o conteúdo de um marcador específico em um documento de origem usando Aspose.Words for .NET, você pode acessar o`Bookmarks` propriedade do intervalo do documento de origem e use o nome do marcador para recuperar o marcador específico. Aqui está um exemplo de código:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### P: Como especificar o local da cópia do texto do marcador em um documento de destino usando Aspose.Words for .NET?

 R: Para especificar onde deseja adicionar texto de marcador copiado em um documento de destino usando Aspose.Words for .NET, você pode navegar até o corpo da última seção do documento de destino. Você pode usar o`LastSection` propriedade para acessar a última seção e o`Body` propriedade para acessar o corpo dessa seção. Aqui está um exemplo de código:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### P: Como importar e copiar o texto do marcador do documento de origem para o documento de destino usando Aspose.Words for .NET?

 R: Para importar e copiar o texto do marcador de um documento de origem para um documento de destino usando Aspose.Words for .NET, você pode usar o`NodeImporter` classe especificando o documento de origem, o documento de destino e o modo de formatação a ser mantido. Então você pode usar o`AppendBookmarkedText` método para adicionar o texto do marcador no documento de destino. Aqui está um exemplo de código:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### P: Como salvar um documento de destino após copiar o texto do marcador usando Aspose.Words for .NET?

R: Para salvar um documento de destino após copiar o texto de um marcador usando Aspose.Words for .NET, você pode usar o`Save` método do`Document` objeto especificando o caminho do arquivo de destino. Aqui está um exemplo de código:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```