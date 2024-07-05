---
title: Mostrar ocultar marcadores em documento do Word
linktitle: Mostrar ocultar marcadores em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mostrar ou ocultar um marcador específico em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/show-hide-bookmarks/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Show Hide Bookmarks na biblioteca Aspose.Words for .NET. Este recurso permite mostrar ou ocultar um marcador específico em um documento do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Passo 1: Carregando o documento

 Nós usamos o`Document` classe para carregar o documento existente de um arquivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Etapa 2: mostrar ou ocultar um favorito específico

 Nós usamos o`ShowHideBookmarkedContent` função para mostrar ou ocultar um marcador específico no documento. Esta função toma como parâmetros o documento, o nome do bookmark e um booleano para indicar se deve mostrar ou ocultar o bookmark:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Passo 3: Salvando o documento modificado

 Nós usamos o`Save` método para salvar o documento modificado em um arquivo:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Exemplo de código-fonte para Show Hide Bookmarks usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a exibição ou ocultação de um marcador específico usando Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Código-fonte ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{marcador MERGEFIELD}" = "true" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso Show Hide Bookmarks do Aspose.Words for .NET. Seguimos um guia passo a passo para mostrar ou ocultar um marcador específico em um documento.

### Perguntas frequentes sobre mostrar e ocultar marcadores em documentos do Word

#### P: Posso mostrar ou ocultar vários marcadores no mesmo documento?

R: Sim, você pode mostrar ou ocultar vários marcadores no mesmo documento repetindo as etapas 2 e 3 para cada marcador que deseja processar.

#### P: O código fornecido funciona com outros formatos de documentos do Word, como .doc ou .docm?

R: Sim, o código fornecido funciona com vários formatos de documentos do Word suportados pelo Aspose.Words, como .doc e .docm. Apenas certifique-se de usar o nome de arquivo e caminho corretos ao carregar e salvar o documento.

#### P: Como posso mostrar um marcador oculto novamente?

 R: Para mostrar um marcador oculto novamente, você precisa usar o mesmo`ShowHideBookmarkedContent` função passando o valor`true` para o parâmetro booleano que indica se o marcador deve ser mostrado ou ocultado.

#### P: Posso usar condições para mostrar ou ocultar marcadores com base nos valores dos campos de mesclagem no documento?

 R: Sim, você pode usar condições e mesclar valores de campos para determinar se um marcador deve ser mostrado ou ocultado. Você pode personalizar o código do`ShowHideBookmarkedContent` função para levar em conta as condições e valores apropriados.

#### P: Como posso excluir um marcador em um documento do Word usando Aspose.Words for .NET?

 R: Para remover um marcador em um documento do Word usando Aspose.Words for .NET, você pode usar o`RemoveBookmarks` método do`Document` aula. Aqui está um exemplo de código:

```csharp
doc.RemoveBookmarks("BookmarkName");
```