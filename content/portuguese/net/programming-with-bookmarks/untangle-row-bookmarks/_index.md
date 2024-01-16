---
title: Desembaraçar marcadores de linha em documento do Word
linktitle: Desembaraçar marcadores de linha em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desembaraçar marcadores de linhas aninhadas em documentos do Word para remover linhas específicas sem afetar outros marcadores.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Untangle Row Bookmarks na biblioteca Aspose.Words for .NET. Esta função permite colocar os finais das linhas dos marcadores na mesma linha do início dos marcadores.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Passo 1: Carregando o documento

 Nós usamos o`Document` classe para carregar o documento existente de um arquivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Etapa 2: desvendar marcadores de linha

 Nós usamos o`Untangle` função para desembaraçar marcadores de linhas. Esta função executa a tarefa personalizada de colocar o final das linhas do marcador na mesma linha em que o marcador começa:

```csharp
Untangle(doc);
```

## Etapa 3: excluir linha por marcador

 Nós usamos o`DeleteRowByBookmark` função para excluir uma linha específica por seu marcador:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Etapa 4: verifique a integridade de outros favoritos

Verificamos se os outros marcadores não foram danificados verificando se o final do marcador ainda está presente:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Exemplo de código-fonte para Untangle Row Bookmarks usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para desembaraçar marcadores de linhas usando Aspose.Words for .NET:


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Isso executa a tarefa personalizada de colocar as extremidades do marcador de linha na mesma linha com o início do marcador.
	Untangle(doc);

	// Agora podemos excluir facilmente linhas de um marcador sem danificar os marcadores de nenhuma outra linha.
	DeleteRowByBookmark(doc, "ROW2");

	// Isto é apenas para verificar se o outro marcador não foi danificado.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Desembaraçar código-fonte
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Obtenha a linha pai do marcador e do nó final do marcador.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Se ambas as linhas forem encontradas corretamente e o início e o fim do marcador estiverem contidos em linhas adjacentes,
                // mova o nó final do marcador para o final do último parágrafo na última célula da linha superior.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### Código-fonte DeleteRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso Untangle Row Bookmarks do Aspose.Words for .NET. Seguimos um guia passo a passo para desembaraçar os marcadores de linha e excluir uma linha específica sem danificar outros marcadores.

### Perguntas frequentes para desembaraçar marcadores de linha em documentos do Word

#### P: O Unscramble Row Bookmarks funciona apenas com marcadores de linha em tabelas?

R: Sim, o recurso Untangle Row Bookmarks foi projetado especificamente para desembaraçar marcadores de linha que estão em tabelas. Esta função pode ser usada para processar marcadores de linha em matrizes e garantir que o final do marcador esteja na mesma linha que o início do marcador.

#### P: A função Unscramble Line Bookmarks modifica o conteúdo do documento original?

R: Sim, a função Desembaralhar marcadores de linha modifica o documento original movendo os marcadores de fim de linha para colocá-los na mesma linha do início dos marcadores. Certifique-se de salvar uma cópia de backup do documento antes de aplicar este recurso.

#### P: Como posso identificar marcadores de linha em meu documento do Word?

R: Os marcadores de linha são normalmente usados em tabelas para marcar seções específicas. Você pode identificar marcadores de linha navegando pelos marcadores no documento e verificando se os marcadores estão nas linhas da tabela.

#### P: É possível desembaraçar marcadores de linha em tabelas não adjacentes?

R: A função Untangle Row Bookmarks, conforme apresentada neste artigo, foi projetada para desembaraçar marcadores de linha em tabelas adjacentes. Para desemaranhar marcadores de linha em tabelas não adjacentes, podem ser necessários ajustes adicionais no código, dependendo da estrutura do documento.

#### P: Que outras manipulações posso realizar nos marcadores de linha depois de desvendados?

R: Depois que os marcadores de linha forem desvendados, você poderá realizar diferentes manipulações conforme necessário. Isso pode incluir editar, excluir ou adicionar conteúdo às linhas marcadas. Certifique-se de manusear os marcadores de linha com cuidado para evitar qualquer impacto indesejado no restante do documento.