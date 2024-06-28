---
title: Definir propriedades do eixo XY em um gráfico
linktitle: Definir propriedades do eixo XY em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir as propriedades do eixo XY em um gráfico usando Aspose.Words for .NET. São demonstradas opções de personalização para os eixos X e Y.
type: docs
weight: 10
url: /pt/net/programming-with-charts/define-xyaxis-properties/
---

Este tutorial explica como usar Aspose.Words for .NET para definir propriedades para os eixos X e Y em um gráfico. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e personalizar as propriedades do eixo.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

- Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo usando o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório do documento onde o documento de saída será salvo.

## Passo 2: Crie um novo documento e insira um gráfico.

 Crie um novo`Document` objeto e um`DocumentBuilder` para construir o documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Em seguida, insira um gráfico no documento usando o`InsertChart` método do`DocumentBuilder`. Neste exemplo, inseriremos um gráfico de área.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos cinco pontos de dados com datas e valores correspondentes.

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

## Etapa 4: personalizar as propriedades dos eixos X e Y

 Para personalizar as propriedades dos eixos X e Y, acesse o`ChartAxis` objetos associados ao gráfico.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Modifique as propriedades do`xAxis` e`yAxis`objetos para definir as opções desejadas para os eixos X e Y. Neste exemplo, demonstraremos algumas propriedades comuns que podem ser personalizadas.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Etapa 5: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Isso conclui a implementação da definição das propriedades do eixo XY em um gráfico usando Aspose.Words for .NET.

### Exemplo de código-fonte para definir propriedades XYAxis usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserir gráfico
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Altere o eixo X para categoria em vez de data, para que todos os pontos sejam colocados com intervalos iguais no eixo X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Medido em unidades de exibição do eixo Y (centenas).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusão

Neste tutorial, você aprendeu como definir propriedades para os eixos X e Y em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo, você pode criar um gráfico, adicionar dados de série e personalizar as propriedades do eixo para atender aos seus requisitos específicos. Aspose.Words for .NET fornece uma API abrangente para processamento de palavras com gráficos em documentos do Word, permitindo manipular vários aspectos do gráfico, incluindo os eixos.

Ao acessar o`ChartAxis` objetos associados ao gráfico, você pode modificar propriedades como tipo de categoria, cruzamentos de eixos, marcas de escala, posições de rótulos, escala e muito mais. Essa flexibilidade permite personalizar a aparência e o comportamento dos eixos do gráfico para apresentar seus dados de maneira eficaz.

Ao usar o Aspose.Words for .NET, você pode integrar perfeitamente recursos de criação e personalização de gráficos em seus aplicativos .NET e automatizar a geração de documentos de aparência profissional com visualizações ricas.

### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, manipular e salvar documentos do Word programaticamente em aplicativos .NET. Ele fornece uma ampla gama de recursos para processamento de texto com elementos de documentos, incluindo gráficos.

#### Q2. Como posso instalar o Aspose.Words para .NET?
Você pode instalar o Aspose.Words for .NET baixando-o usando o gerenciador de pacotes NuGet no Visual Studio. Basta pesquisar “Apose.Words” no gerenciador de pacotes NuGet e instalá-lo em seu projeto.

#### Q3. Posso personalizar outros aspectos do gráfico usando Aspose.Words for .NET?
Sim, o Aspose.Words for .NET oferece amplos recursos para personalizar vários aspectos de um gráfico. Além de definir as propriedades do eixo, você pode modificar o tipo de gráfico, série de dados, legenda, título, área de plotagem, rótulos de dados e muitos outros elementos do gráfico. A API oferece controle refinado sobre a aparência e o comportamento do gráfico.

#### Q4. Posso criar diferentes tipos de gráficos usando Aspose.Words for .NET?
 Sim, Aspose.Words for .NET oferece suporte a uma ampla variedade de tipos de gráficos, incluindo área, barra, linha, pizza, dispersão e muito mais. Você pode usar o`ChartType` enumeração para especificar o tipo de gráfico desejado ao inserir uma forma de gráfico em um documento do Word.

#### Q5. Posso salvar o gráfico em diferentes formatos?
Sim, Aspose.Words for .NET permite salvar o documento que contém o gráfico em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato apropriado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento.

#### Q6. Posso aplicar essas técnicas a vários gráficos em um documento?
 Sim, você pode aplicar essas técnicas a vários gráficos em um documento, repetindo as etapas necessárias para cada gráfico. Você pode criar separado`Chart` e`ChartAxis` objetos para cada gráfico e personalize suas propriedades de acordo. Aspose.Words for .NET fornece suporte completo para processamento de palavras com vários gráficos em um único documento.