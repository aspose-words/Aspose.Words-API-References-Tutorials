---
title: Número da lista de reinicialização
linktitle: Número da lista de reinicialização
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como redefinir o número de uma lista em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-list/restart-list-number/
---
Neste tutorial passo a passo, mostraremos como redefinir o número de uma lista em um documento do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: Criando o Documento e o Gerador de Documentos

Primeiro, crie um novo documento e um gerador de documentos associado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: Criando e Personalizando a Primeira Lista

Em seguida, crie uma lista com base em um modelo existente e personalize seus níveis:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Etapa 3: adicionar itens à primeira lista

Use o construtor de documentos para adicionar itens à primeira lista e remover os números da lista:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Etapa 4: Criando e Personalizando a Segunda Lista

Para reutilizar a primeira lista redefinindo o número, crie uma cópia do layout da lista original:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Você também pode fazer alterações adicionais na segunda lista, se necessário.

## Passo 5: Adicionando itens à segunda lista

Use o construtor de documentos novamente para adicionar itens à segunda lista e remover os números da lista:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Etapa 6: salve o documento modificado

Por fim, salve o documento modificado:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Então ! Você redefiniu com êxito o número de uma lista em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para redefinição de número de lista

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crie uma lista com base em um modelo.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Para reutilizar a primeira lista, precisamos reiniciar a numeração criando uma cópia da formatação original da lista.
List list2 = doc.Lists.AddCopy(list1);

// Podemos modificar a nova lista de qualquer forma, inclusive definindo um novo número inicial.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Perguntas frequentes

#### P: Como posso reiniciar a numeração de uma lista no Aspose.Words?

 R: Para reiniciar a numeração de uma lista no Aspose.Words, você pode usar o`ListRestartAtNumber` método do`List` aula. Este método permite definir um novo valor de discagem a partir do qual a lista deve ser reiniciada. Por exemplo, você pode usar`list.ListRestartAtNumber(1)` para reiniciar a numeração a partir de 1.

#### P: É possível personalizar o prefixo e o sufixo da numeração da lista reiniciada no Aspose.Words?

 R: Sim, você pode personalizar o prefixo e o sufixo da numeração da lista reiniciada em Aspose.Words. O`ListLevel` classe oferece propriedades como`ListLevel.NumberPrefix` e`ListLevel.NumberSuffix` que permitem especificar o prefixo e o sufixo para cada nível da lista. É possível usar essas propriedades para customizar o prefixo e o sufixo conforme necessário.

#### P: Como posso especificar um valor de numeração específico a partir do qual a lista deve ser reiniciada?

R: Para especificar um valor numérico específico a partir do qual a lista deve ser reiniciada, você pode usar o`ListRestartAtNumber` método passando o valor desejado como argumento. Por exemplo, para reiniciar a numeração a partir de 5, você pode usar`list.ListRestartAtNumber(5)`.

#### P: É possível reiniciar a numeração de lista multinível em Aspose.Words?

 R: Sim, Aspose.Words suporta numeração de reinicialização de vários níveis de lista. Você pode aplicar o`ListRestartAtNumber` método em cada nível de lista para reiniciar a numeração individualmente. Por exemplo, você pode usar`list.Levels[0].ListRestartAtNumber(1)` para reiniciar o primeiro nível da lista a partir de 1, e`list.Levels[1].ListRestartAtNumber(1)` para reiniciar a lista de segundo nível começando em 1 e assim por diante.



