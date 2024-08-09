---
title: Lista com marcadores
linktitle: Lista com marcadores
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar e personalizar listas com marcadores em documentos do Word usando Aspose.Words for .NET com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/working-with-markdown/bulleted-list/
---
## Introdução

Pronto para mergulhar no mundo do Aspose.Words for .NET? Hoje, veremos como criar uma lista com marcadores em seus documentos do Word. Esteja você organizando ideias, listando itens ou apenas adicionando um pouco de estrutura ao seu documento, as listas com marcadores são muito úteis. Então, vamos começar!

## Pré-requisitos

Antes de entrarmos na diversão da codificação, vamos ter certeza de que você tem tudo o que precisa:

1.  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Se você ainda não tem, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: ambiente de desenvolvimento AC# como Visual Studio.
3. Conhecimento básico de C#: Um conhecimento básico de programação C# o ajudará a acompanhar.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso é como preparar o terreno para que nosso código funcione sem problemas.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Agora, vamos dividir o processo em etapas fáceis e gerenciáveis.

## Etapa 1: crie um novo documento

Tudo bem, vamos começar criando um novo documento. É aqui que toda a magia acontecerá.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: aplicar formato de lista com marcadores

A seguir, aplicaremos um formato de lista com marcadores. Isso informa ao documento que estamos prestes a iniciar uma lista com marcadores.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Etapa 3: personalizar a lista com marcadores

Aqui, personalizaremos a lista com marcadores ao nosso gosto. Neste exemplo, usaremos um travessão (-) como marcador.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Etapa 4: adicionar itens à lista

Agora, vamos adicionar alguns itens à nossa lista com marcadores. É aqui que você pode ser criativo e adicionar qualquer conteúdo que precisar.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## Etapa 5: adicionar subitens

Para tornar as coisas mais interessantes, vamos adicionar alguns subitens no “Item 2”. Isso ajuda na organização dos subpontos.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // Retornar ao nível da lista principal
```

## Conclusão

E aí está! Você acabou de criar uma lista com marcadores em um documento do Word usando Aspose.Words for .NET. É um processo simples, mas incrivelmente poderoso para organizar seus documentos. Esteja você criando listas simples ou listas aninhadas complexas, o Aspose.Words tem o que você precisa.

Sinta-se à vontade para experimentar diferentes estilos e formatos de lista para atender às suas necessidades. Boa codificação!

## Perguntas frequentes

### Posso usar símbolos de marcadores diferentes na lista?
    Sim, você pode personalizar os símbolos dos marcadores alterando o`NumberFormat` propriedade.

### Como adiciono mais níveis de recuo?
    Use o`ListIndent` método para adicionar mais níveis e`ListOutdent` para voltar a um nível superior.

### É possível misturar listas com marcadores e números?
   Absolutamente! Você pode alternar entre formatos de marcadores e números usando o`ApplyNumberDefault`e`ApplyBulletDefault` métodos.

### Posso estilizar o texto nos itens da lista?
    Sim, você pode aplicar diferentes estilos, fontes e formatação ao texto nos itens da lista usando o botão`Font` propriedade do`DocumentBuilder`.

### Como posso criar uma lista com marcadores de várias colunas?
   Você pode usar a formatação de tabela para criar listas com várias colunas, onde cada célula contém uma lista com marcadores separada.