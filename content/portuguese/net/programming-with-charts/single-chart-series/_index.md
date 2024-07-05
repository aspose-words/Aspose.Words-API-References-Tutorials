---
title: Personalize séries de gráficos únicos em um gráfico
linktitle: Personalize séries de gráficos únicos em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como personalizar séries de gráficos únicos em um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/single-chart-series/
---

Este tutorial explica como usar Aspose.Words for .NET para personalizar séries de gráficos únicos em um gráfico. O código-fonte fornecido demonstra como criar um gráfico, acessar séries específicas e modificar suas propriedades.

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

## Etapa 3: acesse e personalize a série de gráficos

 Para modificar séries de gráficos únicos, você precisa acessar o`ChartSeries` objetos do gráfico.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Isso conclui a implementação da personalização de uma única série de gráficos usando Aspose.Words for .NET.

### Exemplo de código-fonte para série de gráfico único usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Você também pode especificar se a linha que conecta os pontos no gráfico deve ser suavizada usando splines Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Especifica se por padrão o elemento pai deve inverter suas cores se o valor for negativo.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Conclusão

Neste tutorial, você aprendeu como personalizar uma única série de gráficos em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de linhas, acessar séries específicas de gráficos e modificar suas propriedades para obter a personalização desejada.

Aspose.Words for .NET fornece recursos poderosos para manipular gráficos em documentos do Word. Ao acessar séries de gráficos individuais, você pode aplicar modificações específicas para personalizar sua aparência e comportamento. Isso permite alterar o nome da série, ativar a suavização da linha do gráfico, personalizar marcadores para pontos de dados, inverter cores para valores negativos e muito mais, para aprimorar a representação visual do seu gráfico.

A personalização de uma única série de gráficos oferece flexibilidade para destacar dados específicos ou enfatizar tendências específicas em seu gráfico. Com Aspose.Words for .NET, você pode acessar e modificar facilmente as propriedades da série de gráficos, permitindo criar gráficos visualmente atraentes e informativos em seus documentos do Word.

### Perguntas frequentes

#### Q1. Posso personalizar várias séries de gráficos em um gráfico?
 Sim, você pode personalizar várias séries de gráficos em um gráfico usando Aspose.Words for .NET. Ao acessar o`ChartSeries`objetos no gráfico, você pode selecionar e modificar diversas séries com base em seus índices ou critérios específicos. Use um loop ou atribuições individuais para modificar as propriedades desejadas para cada série de gráficos. Dessa forma, você pode aplicar diferentes personalizações a várias séries no mesmo gráfico.

#### Q2. Como posso alterar o nome de uma série de gráficos?
 Para alterar o nome de uma série de gráficos em um gráfico usando Aspose.Words for .NET, você precisa acessar o`Name` propriedade do`ChartSeries` objeto e defina-o com o nome desejado. O nome da série normalmente é exibido na legenda do gráfico ou nos rótulos de dados, fornecendo um rótulo descritivo para a série. Ao modificar o nome da série, você pode fornecer nomes significativos que reflitam os dados representados por cada série.

#### Q3. O que é suavização de série de gráficos?
 suavização de série de gráficos é uma técnica de aprimoramento visual que permite criar uma linha suave conectando os pontos no gráfico. Ele aplica um algoritmo de suavização, como splines Catmull-Rom, para interpolar entre pontos de dados e criar uma curva visualmente agradável. Para habilitar a suavização de série em um gráfico usando Aspose.Words for .NET, acesse o`Smooth` propriedade do`ChartSeries` objeto e configurá-lo para`true`. A suavização pode ser útil para exibir tendências ou padrões em dados com flutuações irregulares.

#### Q4. Como posso personalizar marcadores para pontos de dados em uma série de gráficos?
 Para personalizar marcadores para pontos de dados em uma série de gráficos usando Aspose.Words for .NET, você precisa acessar o`Marker` propriedade do`ChartSeries` objeto e modificar suas propriedades, como`Symbol` e`Size`. Marcadores são indicadores visuais colocados no gráfico para representar pontos de dados individuais. Você pode escolher entre uma variedade de símbolos de marcadores integrados e ajustar seu tamanho para destacar ou diferenciar pontos de dados específicos na série.

#### Q5. Posso inverter cores para valores negativos em uma série de gráficos?
 Sim, você pode inverter cores para valores negativos em uma série de gráficos usando Aspose.Words for .NET. Ao definir o`InvertIfNegative` propriedade do`ChartSeries` opor-se a`true`, as cores dos pontos de dados com valores negativos serão invertidas, tornando-os visualmente distintos dos valores positivos. Este recurso pode ser útil ao comparar valores positivos e negativos em uma série de gráficos, fornecendo uma diferenciação clara entre os dois.