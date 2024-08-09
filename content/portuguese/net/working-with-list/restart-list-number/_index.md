---
title: Número da lista de reinicialização
linktitle: Número da lista de reinicialização
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reiniciar números de lista em documentos do Word usando Aspose.Words for .NET. Este guia detalhado de 2.000 palavras cobre tudo o que você precisa saber, desde a configuração até a personalização avançada.
type: docs
weight: 10
url: /pt/net/working-with-list/restart-list-number/
---
## Introdução

Você deseja dominar a arte da manipulação de listas em seus documentos do Word usando Aspose.Words for .NET? Bem, você está no lugar certo! Neste tutorial, vamos nos aprofundar na reinicialização dos números da lista, um recurso bacana que levará suas habilidades de automação de documentos para o próximo nível. Aperte o cinto e vamos começar!

## Pré-requisitos

Antes de entrarmos no código, vamos ter certeza de que você tem tudo o que precisa:

1.  Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Se você ainda não o instalou, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento adequado, como o Visual Studio.
3. Conhecimento básico de C#: Um conhecimento básico de C# o ajudará a acompanhar o tutorial.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Eles são cruciais para acessar os recursos do Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Agora, vamos dividir o processo em etapas fáceis de seguir. Abordaremos tudo, desde a criação de uma lista até o reinício de sua numeração.

## Etapa 1: configure seu documento e construtor

Antes de começar a manipular listas, você precisa de um documento e de um DocumentBuilder. O DocumentBuilder é a ferramenta ideal para adicionar conteúdo ao seu documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: crie e personalize sua primeira lista

A seguir, criaremos uma lista baseada em um modelo e personalizaremos sua aparência. Neste exemplo, estamos usando o formato de número arábico entre parênteses.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Aqui, definimos a cor da fonte para vermelho e alinhamos o texto à direita.

## Etapa 3: adicione itens à sua primeira lista

 Com sua lista pronta, é hora de adicionar alguns itens. O DocumentBuilder`ListFormat.List` propriedade ajuda a aplicar o formato de lista ao texto.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Etapa 4: reiniciar a numeração da lista

Para reutilizar a lista e reiniciar sua numeração, é necessário criar uma cópia da lista original. Isto permite modificar a nova lista de forma independente.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Neste exemplo, a nova lista começa no número 10.

## Etapa 5: adicionar itens à nova lista

Assim como antes, adicione itens à sua nova lista. Isso demonstra a lista reiniciando no número especificado.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Etapa 6: salve seu documento

Finalmente, salve seu documento no diretório especificado.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Conclusão

Reiniciar números de listas em documentos do Word usando Aspose.Words for .NET é simples e incrivelmente útil. Esteja você gerando relatórios, criando documentos estruturados ou apenas precisando de um melhor controle sobre suas listas, esta técnica o ajudará.

## Perguntas frequentes

### Posso usar outros modelos de lista além de NumberArabicParenthesis?

Absolutamente! Aspose.Words oferece vários modelos de lista, como marcadores, letras, algarismos romanos e muito mais. Você pode escolher aquele que melhor se adapta às suas necessidades.

### Como altero o nível da lista?

 Você pode alterar o nível da lista modificando o`ListLevels` propriedade. Por exemplo,`list1.ListLevels[1]` se referiria ao segundo nível da lista.

### Posso reiniciar a numeração em qualquer número?

 Sim, você pode definir o número inicial para qualquer valor inteiro usando o`StartAt` propriedade do nível da lista.

### É possível ter formatação diferente para diferentes níveis de lista?

De fato! Cada nível de lista pode ter suas próprias configurações de formatação, como fonte, alinhamento e estilo de numeração.

### E se eu quiser continuar a numeração de uma lista anterior em vez de reiniciar?

Se quiser continuar a numeração, não é necessário criar uma cópia da lista. Simplesmente continue adicionando itens à lista original.


