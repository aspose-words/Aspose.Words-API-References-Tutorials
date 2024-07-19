---
title: Mostrar ocultar conteúdo marcado em documento do Word
linktitle: Mostrar ocultar conteúdo marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mostrar e ocultar conteúdo marcado em documentos do Word usando Aspose.Words for .NET com este guia passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Introdução

Pronto para mergulhar no mundo da manipulação de documentos com Aspose.Words for .NET? Quer você seja um desenvolvedor que deseja automatizar tarefas de documentos ou apenas alguém curioso sobre como lidar com arquivos do Word de forma programática, você está no lugar certo. Hoje, exploraremos como mostrar e ocultar conteúdo marcado em um documento do Word usando Aspose.Words for .NET. Este guia passo a passo tornará você um profissional no controle da visibilidade do conteúdo com base em marcadores. Vamos começar!

## Pré-requisitos

Antes de entrarmos no âmago da questão, há algumas coisas que você precisará:

1. Visual Studio: qualquer versão compatível com .NET.
2.  Aspose.Words para .NET: Faça o download[aqui](https://releases.aspose.com/words/net/).
3. Compreensão básica de C#: Se você consegue escrever um programa simples “Hello World”, você está pronto para começar.
4. Um documento do Word com marcadores: usaremos um documento de exemplo com marcadores para este tutorial.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso garante que tenhamos todas as ferramentas necessárias para nossa tarefa.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Com esses namespaces implementados, estamos prontos para iniciar nossa jornada.

## Etapa 1: configurando seu projeto

Tudo bem, vamos começar configurando nosso projeto no Visual Studio.

### Crie um novo projeto

Abra o Visual Studio e crie um novo projeto de aplicativo de console (.NET Core). Dê um nome atraente, como "BookmarkVisibilityManager".

### Adicionar Aspose.Words para .NET

Você precisará adicionar Aspose.Words for .NET ao seu projeto. Você pode fazer isso por meio do Gerenciador de pacotes NuGet.

1. Vá para Ferramentas > Gerenciador de pacotes NuGet > Gerenciar pacotes NuGet para solução.
2. Procure por "Aspose.Words".
3. Instale o pacote.

Ótimo! Agora que nosso projeto está configurado, vamos carregar nosso documento.

## Passo 2: Carregando o Documento

Precisamos carregar o documento Word que contém os favoritos. Para este tutorial, usaremos um documento de amostra chamado "Bookmarks.docx".

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Este trecho de código define o caminho para o diretório do seu documento e carrega o documento no`doc` objeto.

## Etapa 3: mostrar/ocultar conteúdo marcado

Agora vem a parte divertida – mostrar ou ocultar o conteúdo com base nos favoritos. Criaremos um método chamado`ShowHideBookmarkedContent` para lidar com isso.

Este é o método que irá alternar a visibilidade do conteúdo marcado como favorito:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Análise do Método

-  Recuperação de favoritos:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` busca o marcador.
- Node Traversal: percorremos os nós dentro do marcador.
-  Alternar visibilidade: se o nó for um`Run` (uma sequência contígua de texto), definimos seu`Hidden` propriedade.

## Etapa 4: aplicando o método

Com nosso método implementado, vamos aplicá-lo para mostrar ou ocultar conteúdo com base em um marcador.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Esta linha de código ocultará o conteúdo do marcador denominado "MyBookmark1".

## Etapa 5: salvando o documento

Finalmente, vamos salvar nosso documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Isso salva o documento com as alterações que fizemos.

## Conclusão

aí está! Você acabou de aprender como mostrar e ocultar conteúdo marcado em um documento do Word usando Aspose.Words for .NET. Essa ferramenta poderosa facilita muito a manipulação de documentos, seja automatizando relatórios, criando modelos ou apenas mexendo em arquivos do Word. Boa codificação!

## Perguntas frequentes

### Posso alternar vários favoritos de uma vez?
 Sim, você pode ligar para`ShowHideBookmarkedContent` método para cada marcador que você deseja alternar.

### A ocultação do conteúdo afeta a estrutura do documento?
Não, ocultar conteúdo afeta apenas sua visibilidade. O conteúdo permanece no documento.

### Posso usar este método para outros tipos de conteúdo?
Este método alterna especificamente as execuções de texto. Para outros tipos de conteúdo, você precisará modificar a lógica de passagem do nó.

### O Aspose.Words para .NET é gratuito?
 Aspose.Words oferece um teste gratuito[aqui](https://releases.aspose.com/) , mas é necessária uma licença completa para uso em produção. Você pode comprá-lo[aqui](https://purchase.aspose.com/buy).

### Como posso obter suporte se encontrar problemas?
 Você pode obter suporte da comunidade Aspose[aqui](https://forum.aspose.com/c/words/8).