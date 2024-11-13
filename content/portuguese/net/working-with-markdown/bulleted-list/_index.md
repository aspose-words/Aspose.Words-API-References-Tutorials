---
title: Lista com marcadores
linktitle: Lista com marcadores
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a criar e personalizar listas com marcadores em documentos do Word usando o Aspose.Words para .NET com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/working-with-markdown/bulleted-list/
---
## Introdução

Pronto para mergulhar no mundo do Aspose.Words para .NET? Hoje, vamos explicar como criar uma lista com marcadores em seus documentos do Word. Não importa se você está organizando ideias, listando itens ou apenas adicionando um pouco de estrutura ao seu documento, as listas com marcadores são super úteis. Então, vamos começar!

## Pré-requisitos

Antes de começarmos a diversão da codificação, vamos garantir que você tenha tudo o que precisa:

1.  Aspose.Words para .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Se você ainda não a tem, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: ambiente de desenvolvimento AC# como o Visual Studio.
3. Conhecimento básico de C#: um conhecimento básico de programação em C# ajudará você a acompanhar.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários. Isso é como preparar o cenário para que nosso código rode suavemente.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Agora, vamos dividir o processo em etapas fáceis e gerenciáveis.

## Etapa 1: Crie um novo documento

Certo, vamos começar criando um novo documento. É aqui que toda a mágica vai acontecer.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: aplicar formato de lista com marcadores

Em seguida, aplicaremos um formato de lista com marcadores. Isso informa ao documento que estamos prestes a iniciar uma lista com marcadores.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Etapa 3: personalizar a lista com marcadores

Aqui, personalizaremos a lista de marcadores conforme nossa preferência. Para este exemplo, usaremos um traço (-) como marcador.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Etapa 4: Adicionar itens de lista

Agora, vamos adicionar alguns itens à nossa lista com marcadores. É aqui que você pode ser criativo e adicionar qualquer conteúdo que precisar.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## Etapa 5: Adicionar subitens

Para tornar as coisas mais interessantes, vamos adicionar alguns subitens em "Item 2". Isso ajuda a organizar os subpontos.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // Retornar ao nível da lista principal
```

## Conclusão

E aí está! Você acabou de criar uma lista com marcadores em um documento do Word usando o Aspose.Words para .NET. É um processo direto, mas incrivelmente poderoso para organizar seus documentos. Não importa se você está criando listas simples ou listas aninhadas complexas, o Aspose.Words tem tudo o que você precisa.

Sinta-se à vontade para experimentar diferentes estilos e formatos de lista para atender às suas necessidades. Boa codificação!

## Perguntas frequentes

### Posso usar diferentes símbolos de marcadores na lista?
    Sim, você pode personalizar os símbolos de marcadores alterando o`NumberFormat` propriedade.

### Como adiciono mais níveis de recuo?
    Use o`ListIndent` método para adicionar mais níveis e`ListOutdent` para voltar a um nível mais alto.

### É possível misturar listas com marcadores e listas numéricas?
   Absolutamente! Você pode alternar entre os formatos de marcadores e números usando o`ApplyNumberDefault` e`ApplyBulletDefault` métodos.

### Posso estilizar o texto nos itens da lista?
    Sim, você pode aplicar diferentes estilos, fontes e formatações ao texto dentro dos itens da lista usando o`Font` propriedade do`DocumentBuilder`.

### Como posso criar uma lista com marcadores de várias colunas?
   Você pode usar a formatação de tabela para criar listas com várias colunas, onde cada célula contém uma lista com marcadores separada.