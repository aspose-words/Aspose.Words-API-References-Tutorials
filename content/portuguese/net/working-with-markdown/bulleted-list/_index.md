---
title: Lista com marcadores
linktitle: Lista com marcadores
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma lista com marcadores com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/bulleted-list/
---

Neste tutorial, mostraremos como criar uma lista com marcadores com Aspose.Words for .NET. Uma lista com marcadores é usada para listar itens sem usar numeração.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: aplicar uma lista com marcadores padrão

 Podemos aplicar uma lista com marcadores padrão usando o construtor de documentos`ApplyBulletDefault` método.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Etapa 3: Personalizando o formato do marcador

 Podemos personalizar o formato do marcador acessando as propriedades de`ListFormat.List.ListLevels[0]`. Neste exemplo, usamos o travessão "-" como marcador.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Passo 4: Adicionando itens à lista

 Agora podemos adicionar itens à lista com marcadores usando o construtor de documentos`Writeln` método.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Etapa 5: remover o recuo da lista

 Se quisermos criar uma sublista, podemos aumentar o recuo usando o`ListFormat.ListIndent()` método. Neste exemplo, estamos adicionando uma sublista aos itens 2a e 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Exemplo de código-fonte para lista com marcadores usando Aspose.Words for .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Parabéns! Agora você aprendeu como criar uma lista com marcadores com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como criar uma lista com marcadores no Markdown?

R: Para criar uma lista com marcadores no Markdown, inicie cada item da lista com um símbolo de marcador (`-`, `*` , ou`+`), seguido por um espaço.

#### P: Você pode aninhar listas com marcadores no Markdown?

R: Sim, é possível aninhar listas com marcadores no Markdown adicionando quatro espaços de deslocamento na frente de cada item da lista aninhada.

#### P: Como personalizar símbolos de marcadores?

R: No Markdown padrão, os símbolos de marcadores são predefinidos. No entanto, alguns editores Markdown permitem personalizá-los usando extensões específicas.

#### P: As listas com marcadores no Markdown suportam recuo?

R: Sim, listas com marcadores no Markdown suportam recuo. Você pode adicionar um deslocamento para a esquerda usando espaços ou tabulações.

#### P: Podem ser adicionados links ou texto embutido aos itens da lista?

R: Sim, você pode adicionar links ou texto embutido aos itens da lista usando a sintaxe Markdown apropriada.
