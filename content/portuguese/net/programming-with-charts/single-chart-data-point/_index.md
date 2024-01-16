---
title: Personalize um único ponto de dados do gráfico em um gráfico
linktitle: Personalize um único ponto de dados do gráfico em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como personalizar um único ponto de dados em um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/single-chart-data-point/
---

Este tutorial explica como usar Aspose.Words for .NET para personalizar um único ponto de dados em um gráfico. O código-fonte fornecido demonstra como criar um gráfico, acessar pontos de dados específicos e modificar suas propriedades.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

- Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo usando o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório do documento onde o documento de saída será salvo.

## Passo 2: Crie um novo documento e insira um gráfico

 Crie um novo`Document` objeto e um`DocumentBuilder` para construir o documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de linhas no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: acessar e personalizar pontos de dados

 Para modificar pontos de dados individuais, você precisa acessar o`ChartDataPointCollection` da série e selecione o ponto de dados desejado usando o índice.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Isso conclui a implementação da personalização de um único ponto de dados em um gráfico usando Aspose.Words for .NET.

### Exemplo de código-fonte para ponto de dados de gráfico único usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusão

Neste tutorial, você aprendeu como personalizar um único ponto de dados em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de linhas, acessar pontos de dados específicos dentro da série de gráficos e modificar suas propriedades para obter a personalização desejada.

Aspose.Words for .NET fornece recursos poderosos para manipular gráficos em documentos do Word. Ao acessar pontos de dados individuais em uma série de gráficos, você pode aplicar modificações específicas para personalizar sua aparência e comportamento. Isso permite destacar pontos de dados específicos, alterar símbolos de marcadores, ajustar tamanhos de marcadores e muito mais, para aprimorar a representação visual do seu gráfico.

A personalização de pontos de dados individuais oferece flexibilidade para enfatizar dados importantes ou destacar tendências específicas em seu gráfico. Com Aspose.Words for .NET, você pode acessar e modificar facilmente pontos de dados em vários tipos de gráficos, permitindo criar gráficos visualmente atraentes e informativos em seus documentos do Word.

### Perguntas frequentes

#### Q1. Posso personalizar vários pontos de dados em um gráfico?
 Sim, você pode personalizar vários pontos de dados em um gráfico usando Aspose.Words for .NET. Ao acessar o`ChartDataPointCollection`de uma série, você pode selecionar e modificar vários pontos de dados com base em seus índices. Use um loop ou atribuições individuais para modificar as propriedades desejadas para cada ponto de dados. Dessa forma, você pode aplicar diferentes personalizações a vários pontos de dados no mesmo gráfico.

#### Q2. Como posso alterar o símbolo do marcador de um ponto de dados?
 Para alterar o símbolo do marcador para um ponto de dados em um gráfico usando Aspose.Words for .NET, você precisa acessar o`Marker` propriedade do`ChartDataPoint` objeto e definir o`Symbol` propriedade para o símbolo do marcador desejado. Os símbolos marcadores representam a forma ou ícone usado para representar cada ponto de dados no gráfico. Você pode escolher entre uma variedade de símbolos de marcadores integrados, como círculo, quadrado, diamante, triângulo, estrela e muito mais.

#### Q3. Posso ajustar o tamanho de um marcador de ponto de dados?
 Sim, você pode ajustar o tamanho de um marcador de ponto de dados em um gráfico usando Aspose.Words for .NET. Acesse o`Marker` propriedade do`ChartDataPoint` objeto e definir o`Size`propriedade para o tamanho de marcador desejado. O tamanho do marcador normalmente é especificado em pontos, onde um valor maior representa um tamanho maior do marcador. Ajustar o tamanho do marcador permite enfatizar pontos de dados específicos ou diferenciá-los com base em sua importância.

#### Q4. Que outras propriedades posso modificar para um ponto de dados?
Aspose.Words for .NET fornece uma variedade de propriedades que você pode modificar para um ponto de dados em um gráfico. Algumas das propriedades comumente modificadas incluem o símbolo do marcador, tamanho do marcador, cor do marcador, visibilidade do rótulo de dados, explosão, inversão se negativo e muito mais. Essas propriedades permitem personalizar a aparência, o comportamento e a interatividade de pontos de dados individuais, permitindo criar gráficos personalizados de acordo com seus requisitos específicos.

#### Q5. Posso personalizar pontos de dados em outros tipos de gráficos?
Sim, você pode personalizar pontos de dados em vários tipos de gráficos usando Aspose.Words for .NET. Embora este tutorial demonstre a personalização de pontos de dados em um gráfico de linhas, você pode aplicar técnicas semelhantes a outros tipos de gráfico, como gráficos de colunas, gráficos de barras, gráficos de pizza e muito mais. O processo envolve acessar as séries e pontos de dados no gráfico e modificar suas propriedades de acordo.