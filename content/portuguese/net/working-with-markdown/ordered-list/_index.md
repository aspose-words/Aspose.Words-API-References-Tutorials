---
title: Lista ordenada
linktitle: Lista ordenada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma lista ordenada com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/ordered-list/
---

Neste exemplo, explicaremos como usar a funcionalidade de lista ordenada com Aspose.Words for .NET. A Lista ordenada permite organizar itens sequencialmente com números.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para criar um novo documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: aplicar o formato de lista ordenada

 Aplicaremos o formato de lista ordenada usando o construtor de documentos`ApplyBulletDefault`método. Também podemos personalizar o formato da numeração acessando os níveis da lista e definindo o formato que desejamos.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Passo 3: Adicionando itens à lista

 Podemos adicionar itens à lista usando o gerador de documentos`Writeln` método.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Etapa 4: recuar a lista

 Podemos recuar a lista usando o gerador de documentos`ListIndent` método.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Passo 5: Salvando o documento

Finalmente, podemos salvar o documento no formato desejado.

### Exemplo de código-fonte para lista ordenada com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Parabéns! Agora você aprendeu como usar o recurso de lista ordenada com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como criar uma lista ordenada no Markdown?

R: Para criar uma lista ordenada no Markdown, comece cada item da lista com um número seguido por um ponto (`1.`, `2.`, `3.`), seguido por um espaço.

#### P: Podemos aninhar listas ordenadas no Markdown?

R: Sim, é possível aninhar listas ordenadas no Markdown adicionando quatro espaços de deslocamento na frente de cada item da lista aninhada.

#### P: Como personalizar a numeração de listas ordenadas?

R: No Markdown padrão, a numeração da lista ordenada é gerada automaticamente. No entanto, alguns editores Markdown permitem personalizá-lo usando extensões específicas.

#### P: As listas ordenadas no Markdown suportam recuo?

R: Sim, listas ordenadas no Markdown suportam recuo. Você pode adicionar um deslocamento para a esquerda usando espaços ou tabulações.

#### P: Podem ser adicionados links ou texto embutido aos itens da lista?

R: Sim, você pode adicionar links ou texto embutido aos itens da lista usando a sintaxe Markdown apropriada.