---
title: Insira gráfico de área em um documento do Word
linktitle: Insira gráfico de área em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de área em um documento usando Aspose.Words for .NET. Adicione dados de série e salve o documento com o gráfico.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-area-chart/
---
## Introdução

Bem-vindo a este guia passo a passo sobre como inserir um gráfico de área em um documento do Word usando Aspose.Words for .NET. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este tutorial irá guiá-lo por tudo o que você precisa saber para criar gráficos de área impressionantes e informativos em seus documentos do Word. Abordaremos os pré-requisitos, mostraremos como importar os namespaces necessários e orientaremos você em cada etapa do processo com instruções claras e fáceis de seguir.

## Pré-requisitos

Antes de começarmos, vamos garantir que você tenha tudo o que precisa para começar:

1.  Aspose.Words for .NET: Certifique-se de ter o Aspose.Words for .NET instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
2. .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
3. IDE: um ambiente de desenvolvimento integrado (IDE) como o Visual Studio para escrever e executar seu código.
4. Conhecimento básico de C#: Um conhecimento básico de programação C# será útil.

Depois de cumprir esses pré-requisitos, você estará pronto para começar a criar lindos gráficos de área em seus documentos do Word.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Esses namespaces fornecem as classes e métodos necessários para trabalhar com documentos e gráficos do Word no Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Agora que importamos os namespaces essenciais, vamos criar nosso documento e inserir um gráfico de área passo a passo.

## Etapa 1: crie um novo documento do Word

Vamos começar criando um novo documento do Word. Esta será a base onde inseriremos nosso gráfico de áreas.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Nesta etapa, inicializamos um novo`Document` objeto que representa nosso documento do Word.

## Etapa 2: use o DocumentBuilder para inserir um gráfico

 A seguir, usaremos o`DocumentBuilder` class para inserir um gráfico de área em nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Aqui, criamos um`DocumentBuilder` objeto e use-o para inserir um gráfico de área de dimensões específicas (432x252) em nosso documento.

## Etapa 3: acesse o objeto gráfico

 Após inserir o gráfico, precisamos acessar o`Chart` objeto para personalizar nosso gráfico de área.

```csharp
Chart chart = shape.Chart;
```

 Esta linha de código recupera o`Chart` objeto da forma que acabamos de inserir.

## Etapa 4: adicionar dados de série ao gráfico

Agora é hora de adicionar alguns dados ao nosso gráfico. Adicionaremos uma série com datas e valores correspondentes.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

Nesta etapa, adicionamos uma série chamada "Aspose Series 1" com um conjunto de datas e valores correspondentes.

## Etapa 5: salve o documento

Por fim, salvaremos nosso documento com o gráfico de áreas inserido.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Esta linha de código salva o documento no diretório especificado com o nome de arquivo fornecido.

## Conclusão

Parabéns! Você inseriu com sucesso um gráfico de área em um documento do Word usando Aspose.Words for .NET. Este guia guiou você em cada etapa, desde a configuração do seu ambiente até salvar o documento final. Com Aspose.Words for .NET, você pode criar uma grande variedade de gráficos e outros elementos complexos em seus documentos Word, tornando seus relatórios e apresentações mais dinâmicos e informativos.

## Perguntas frequentes

### Posso usar o Aspose.Words for .NET com outras linguagens .NET?
Sim, Aspose.Words for .NET oferece suporte a outras linguagens .NET, como VB.NET.

### É possível personalizar a aparência do gráfico?
Absolutamente! Aspose.Words for .NET oferece amplas opções para personalizar a aparência de seus gráficos.

### Posso adicionar vários gráficos a um único documento do Word?
Sim, você pode inserir quantos gráficos precisar em um único documento do Word.

### O Aspose.Words for .NET oferece suporte a outros tipos de gráfico?
Sim, Aspose.Words for .NET oferece suporte a vários tipos de gráfico, incluindo barra, linha, pizza e muito mais.

### Onde posso obter uma licença temporária do Aspose.Words for .NET?
 Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).