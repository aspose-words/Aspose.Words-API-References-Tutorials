---
title: Adicionar valores de data e hora ao eixo de um gráfico
linktitle: Adicionar valores de data e hora ao eixo de um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/date-time-values-to-axis/
---

Este tutorial explica como adicionar valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir e configurar um formato de gráfico
 Insira uma forma de gráfico no documento usando o`InsertChart` método do`DocumentBuilder` objeto. Defina o tipo e as dimensões do gráfico desejado.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Etapa 4: adicionar dados ao gráfico
Adicione dados à série de gráficos, incluindo valores de data e hora.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Etapa 5: configurar o eixo
Configure o eixo X do gráfico para exibir os valores de data e hora.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Etapa 6: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Exemplo de código-fonte para valores de data e hora para eixo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Defina as unidades principais como uma semana e as unidades menores como um dia.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Este código de exemplo cria um novo documento do Word, insere um gráfico de colunas com valores de data e hora no eixo X e salva o documento no diretório especificado.

## Conclusão
Neste tutorial, você aprendeu como adicionar valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo, você pode criar um gráfico, adicionar valores de data e hora à série e configurar o eixo para exibir os valores de data e hora com precisão. Aspose.Words for .NET fornece um poderoso conjunto de recursos para processamento de palavras com gráficos em documentos do Word, permitindo representar e visualizar dados com valores de data e hora de forma eficaz.

### Perguntas frequentes

#### Q1. Posso adicionar valores de data e hora ao eixo de um gráfico usando Aspose.Words for .NET?
Sim, com Aspose.Words for .NET, você pode adicionar e exibir valores de data e hora no eixo de um gráfico em um documento do Word. Aspose.Words fornece APIs e funcionalidades para trabalhar com vários tipos de gráficos e personalizar sua aparência, incluindo o tratamento de valores de data e hora no eixo.

#### Q2. Como adiciono valores de data e hora à série do gráfico?
 Para adicionar valores de data e hora à série do gráfico, você pode usar o`Add`método da série do gráfico. Forneça uma matriz de valores de data e hora como dados de categoria (eixo X), junto com os valores de série correspondentes. Isso permite plotar pontos de dados com valores de data e hora no gráfico.

#### Q3. Como posso configurar o eixo para exibir valores de data e hora?
 Você pode configurar o eixo do gráfico para exibir valores de data e hora definindo as propriedades apropriadas. Por exemplo, você pode especificar os valores mínimo e máximo para o eixo usando o`Scaling.Minimum` e`Scaling.Maximum` propriedades, respectivamente. Além disso, você pode definir as unidades maiores e menores para definir o intervalo e as marcas de escala do eixo.
