---
title: Adicionar valores de data e hora ao eixo de um gráfico
linktitle: Adicionar valores de data e hora ao eixo de um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET neste guia passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/programming-with-charts/date-time-values-to-axis/
---
## Introdução

Criar gráficos em documentos pode ser uma forma poderosa de visualizar dados. Ao lidar com dados de série temporal, adicionar valores de data e hora ao eixo de um gráfico é crucial para maior clareza. Neste tutorial, orientaremos você no processo de adição de valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET. Este guia passo a passo ajudará você a configurar seu ambiente, escrever o código e compreender cada parte do processo. Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio ou qualquer IDE .NET: você precisa de um ambiente de desenvolvimento para escrever e executar seu código .NET.
2.  Aspose.Words for .NET: Você deve ter a biblioteca Aspose.Words for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
3. Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento básico de programação C#.
4.  Uma licença Aspose válida: Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).

## Importar namespaces

Para começar, certifique-se de ter os namespaces necessários importados em seu projeto. Esta etapa é crucial para acessar as classes e métodos Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa definir o diretório onde seu documento será salvo. Isso é importante para organizar seus arquivos e garantir que seu código seja executado corretamente.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder

 Em seguida, crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto. Esses objetos irão ajudá-lo a construir e manipular seu documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: insira um gráfico no documento

 Agora, insira um gráfico em seu documento usando o`DocumentBuilder` objeto. Neste exemplo, estamos usando um gráfico de colunas, mas você também pode escolher outros tipos.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 4: limpar as séries existentes

Limpe todas as séries existentes no gráfico para garantir que você está começando do zero. Esta etapa é essencial para dados personalizados.

```csharp
chart.Series.Clear();
```

## Etapa 5: adicionar valores de data e hora à série

Adicione seus valores de data e hora à série de gráficos. Esta etapa envolve a criação de matrizes para datas e valores correspondentes.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Etapa 6: configurar o eixo X

Defina a escala e as marcas de escala para o eixo X. Isso garante que suas datas sejam exibidas corretamente e em intervalos apropriados.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Etapa 7: salve o documento

Finalmente, salve seu documento no diretório especificado. Esta etapa conclui o processo e seu documento agora deve conter um gráfico com valores de data e hora no eixo X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Conclusão

Adicionar valores de data e hora ao eixo de um gráfico em um documento é um processo simples com Aspose.Words for .NET. Seguindo as etapas descritas neste tutorial, você pode criar gráficos claros e informativos que visualizam dados de série temporal de maneira eficaz. Esteja você preparando relatórios, apresentações ou qualquer documento que exija representação detalhada de dados, Aspose.Words fornece as ferramentas de que você precisa para ter sucesso.

## Perguntas frequentes

### Posso usar outros tipos de gráfico com Aspose.Words for .NET?

Sim, Aspose.Words oferece suporte a vários tipos de gráfico, incluindo linha, barra, pizza e muito mais.

### Como posso personalizar a aparência do meu gráfico?

Você pode personalizar a aparência acessando as propriedades do gráfico e definindo estilos, cores e muito mais.

### É possível adicionar várias séries a um gráfico?

 Absolutamente! Você pode adicionar várias séries ao seu gráfico chamando o método`Series.Add` método várias vezes com dados diferentes.

### E se eu precisar atualizar os dados do gráfico de forma dinâmica?

Você pode atualizar os dados do gráfico dinamicamente manipulando as propriedades da série e do eixo de forma programática com base em seus requisitos.

### Onde posso encontrar documentação mais detalhada para Aspose.Words for .NET?

 Você pode encontrar documentação mais detalhada[aqui](https://reference.aspose.com/words/net/).