---
title: Mostrar ocultar conteúdo marcado em documento do Word
linktitle: Mostrar ocultar conteúdo marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mostrar ou ocultar dinamicamente o conteúdo marcado em documentos do Word usando Aspose.Words for .NET com este guia passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Introdução

Ei! Você já quis controlar a visibilidade de um conteúdo específico em um documento do Word com base em determinadas condições? Com Aspose.Words for .NET, você pode mostrar ou ocultar dinamicamente o conteúdo marcado com apenas algumas linhas de código. Neste tutorial, orientarei você pelo processo passo a passo, garantindo que você entenda cada parte do código. No final, você será um profissional na manipulação de marcadores em documentos do Word. Vamos começar!

## Pré-requisitos

Antes de mergulharmos no tutorial, vamos ter certeza de que você tem tudo o que precisa:

1. Conhecimento básico de C#: você deve estar confortável com a sintaxe e os conceitos do C#.
2.  Aspose.Words para .NET: Faça o download[aqui](https://releases.aspose.com/words/net/) . Se você não estiver pronto para comprar, você pode começar com um[teste grátis](https://releases.aspose.com/).
3. Visual Studio: qualquer versão recente funcionará, mas é recomendável usar a versão mais recente.
4. .NET Framework: certifique-se de que esteja instalado em sua máquina.

Pronto para começar? Ótimo! Vamos começar importando os namespaces necessários.

## Importar namespaces

Para usar Aspose.Words for .NET, precisamos importar os namespaces necessários. Esta etapa garante que tenhamos acesso a todas as classes e métodos que usaremos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Esses namespaces são cruciais para trabalhar com documentos do Word e manipular seu conteúdo.

## Passo 1: Configurando o Documento

Primeiro, vamos criar um novo documento do Word e um construtor de documentos. O construtor de documentos nos ajuda a adicionar e manipular facilmente o conteúdo do documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nesta etapa, inicializamos um novo documento e um construtor de documentos. Isso configura nosso ambiente para operações futuras.

## Etapa 2: adicionar conteúdo marcado

A seguir, adicionaremos algum conteúdo ao documento e criaremos um marcador em torno dele. Este marcador nos ajudará a identificar e manipular o conteúdo.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Aqui, adicionamos algum texto antes e depois do conteúdo marcado. O`StartBookmark` e`EndBookmark` métodos definem os limites do marcador.

## Etapa 3: Inserindo um Campo Condicional

Para controlar a visibilidade do conteúdo marcado, usaremos um campo condicional. Este campo verificará uma condição e exibirá ou ocultará o conteúdo de acordo.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Nesta etapa inserimos um campo IF que verifica o valor do marcador. Se o valor for “true”, será exibido “Visível”; caso contrário, exibirá "Oculto".

## Etapa 4: reorganizando nós

Em seguida, precisamos reorganizar os nós para garantir que a lógica condicional se aplique corretamente ao conteúdo marcado.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

Aqui, movemos os nós para garantir que a condição abrange adequadamente o conteúdo marcado.

## Etapa 5: executando a mala direta

Por fim, executaremos uma mala direta para definir o valor do marcador e determinar se o conteúdo deve ser mostrado ou ocultado.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Esta etapa define o valor do marcador como "true", o que tornará o conteúdo visível com base em nossa condição.

## Etapa 6: salvando o documento

Após todas as manipulações, o último passo é salvar o documento modificado.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Aqui salvamos o documento com um nome de arquivo descritivo para indicar as alterações.

## Conclusão

 E é isso! Você aprendeu com sucesso como mostrar ou ocultar conteúdo marcado em um documento do Word usando Aspose.Words for .NET. Este tutorial abordou a criação de um documento, a adição de marcadores, a inserção de campos condicionais, a reorganização de nós e a execução de uma mala direta. Aspose.Words oferece uma infinidade de recursos, então não hesite em explorar o[Documentação da API](https://reference.aspose.com/words/net/) para recursos mais avançados.

## Perguntas frequentes

### 1. O que é Aspose.Words para .NET?

Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e converter documentos do Word programaticamente. É amplamente utilizado para tarefas de automação de documentos.

### 2. Posso usar o Aspose.Words for .NET gratuitamente?

 Você pode tentar Aspose.Words for .NET usando um[teste grátis](https://releases.aspose.com/). Para uso de longo prazo, você precisará adquirir uma licença.

### 3. Como modifico outras propriedades de um marcador?

 Aspose.Words permite manipular várias propriedades de um marcador, como texto e localização. Consulte o[Documentação da API](https://reference.aspose.com/words/net/) para obter instruções detalhadas.

### 4. Como obtenho suporte para Aspose.Words for .NET?

Você pode obter suporte visitando o[Aspose fórum de suporte](https://forum.aspose.com/c/words/8).

### 5. Posso manipular outros tipos de conteúdo com Aspose.Words for .NET?

Sim, Aspose.Words for .NET oferece suporte a vários tipos de manipulação de conteúdo, incluindo texto, imagens, tabelas e muito mais.