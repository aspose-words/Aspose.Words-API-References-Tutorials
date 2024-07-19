---
title: Definir propriedades do eixo XY em um gráfico
linktitle: Definir propriedades do eixo XY em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir as propriedades do eixo XY em um gráfico usando Aspose.Words for .NET com este guia passo a passo. Perfeito para desenvolvedores .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/define-xyaxis-properties/
---
## Introdução

Os gráficos são uma ferramenta poderosa para visualizar dados. Quando você precisa criar documentos profissionais com gráficos dinâmicos, Aspose.Words for .NET é uma biblioteca inestimável. Este artigo orientará você no processo de definição das propriedades do eixo XY em um gráfico usando Aspose.Words for .NET, detalhando cada etapa para garantir clareza e facilidade de compreensão.

## Pré-requisitos

Antes de mergulhar na codificação, existem alguns pré-requisitos que você precisa ter em vigor:

1. Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET. Você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: você precisa de um ambiente de desenvolvimento integrado (IDE) como o Visual Studio.
3. .NET Framework: certifique-se de que seu ambiente de desenvolvimento esteja configurado para desenvolvimento .NET.
4. Conhecimento básico de C#: Este guia pressupõe que você tenha um conhecimento básico de programação em C#.

## Importar namespaces

Para começar, você precisa importar os namespaces necessários para o seu projeto. Isso garante que você tenha acesso a todas as classes e métodos necessários para criar e manipular documentos e gráficos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Dividiremos o processo em etapas simples, cada uma focando em uma parte específica da definição das propriedades do eixo XY em um gráfico.

## Etapa 1: inicializar o documento e o DocumentBuilder

 Primeiro, você precisa inicializar um novo documento e um`DocumentBuilder` objeto. O`DocumentBuilder` ajuda na inserção de conteúdo no documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir um gráfico

A seguir, você inserirá um gráfico no documento. Neste exemplo, usaremos um gráfico de área. Você pode personalizar as dimensões do gráfico conforme necessário.

```csharp
// Inserir gráfico
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: limpar a série padrão e adicionar dados personalizados

Por padrão, o gráfico terá algumas séries pré-definidas. Iremos limpá-los e adicionar nossa série de dados personalizados.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Etapa 4: definir as propriedades do eixo X

Agora é hora de definir as propriedades do eixo X. Isso inclui definir o tipo de categoria, personalizar o cruzamento do eixo e ajustar marcas e rótulos.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Medido em unidades de exibição do eixo Y (centenas).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Etapa 5: definir as propriedades do eixo Y

Da mesma forma, você definirá as propriedades do eixo Y. Isso inclui definir a posição do rótulo do tick, unidades maiores e menores, unidade de exibição e escala.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Etapa 6: salve o documento

Finalmente, salve o documento no diretório especificado. Isso irá gerar o documento Word com o gráfico personalizado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusão

Criar e personalizar gráficos em documentos do Word usando Aspose.Words for .NET é simples quando você entende as etapas envolvidas. Este guia orientou você no processo de definição das propriedades do eixo XY em um gráfico, desde a inicialização do documento até o salvamento do produto final. Com essas habilidades, você pode criar gráficos detalhados e com aparência profissional que aprimoram seus documentos.

## Perguntas frequentes

### Que tipos de gráficos posso criar com Aspose.Words for .NET?
Você pode criar vários tipos de gráficos, incluindo Área, Barra, Linha, Pizza e muito mais.

### Como instalo o Aspose.Words para .NET?
 Você pode baixar Aspose.Words para .NET em[aqui](https://releases.aspose.com/words/net/) e siga as instruções de instalação fornecidas.

### Posso personalizar a aparência dos meus gráficos?
Sim, Aspose.Words for .NET permite ampla personalização de gráficos, incluindo cores, fontes e propriedades de eixo.

### Existe um teste gratuito disponível para Aspose.Words for .NET?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Onde posso encontrar mais tutoriais e documentação?
 Você pode encontrar mais tutoriais e documentação detalhada no[Página de documentação do Aspose.Words para .NET](https://reference.aspose.com/words/net/).
