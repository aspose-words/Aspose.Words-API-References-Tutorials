---
title: Formatar o número do rótulo de dados em um gráfico
linktitle: Formatar o número do rótulo de dados em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como formatar o número de rótulos de dados em um gráfico usando Aspose.Words for .NET. Personalize formatos numéricos para rótulos de dados facilmente.
type: docs
weight: 10
url: /pt/net/programming-with-charts/format-number-of-data-label/
---

Este tutorial explica como usar Aspose.Words for .NET para formatar o número de rótulos de dados em um gráfico. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e personalizar o formato numérico dos rótulos de dados.

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

 Em seguida, insira um gráfico no documento usando o`InsertChart` método do`DocumentBuilder`. Neste exemplo, inseriremos um gráfico de linhas.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos três categorias e seus valores correspondentes.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Etapa 4: personalize o formato numérico dos rótulos de dados

 Para formatar o número de rótulos de dados, acesse o`DataLabels` coleção associada à série.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Neste exemplo, definimos diferentes formatos numéricos para cada rótulo de dados. O primeiro rótulo de dados é formatado como moeda, o segundo como data e o terceiro como porcentagem.

## Etapa 5: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Isso completa a implementação da formatação do número de rótulos de dados em um gráfico usando Aspose.Words for .NET.

### Exemplo de código-fonte para Format Number Of Data Label usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Exclua a série gerada padrão.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Ou você pode definir o código de formato para ser vinculado a uma célula de origem,
	//Neste caso, NumberFormat será redefinido para geral e herdado de uma célula de origem.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Conclusão

Neste tutorial, você aprendeu como formatar o número de rótulos de dados em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um gráfico, adicionar dados de série e personalizar o formato numérico dos rótulos de dados de acordo com suas necessidades.

 Aspose.Words for .NET fornece uma API abrangente para processamento de palavras com gráficos em documentos do Word, permitindo manipular vários aspectos do gráfico, incluindo rótulos de dados. Ao acessar o`DataLabels` coleção associada a uma série, você pode personalizar o formato numérico de rótulos de dados individuais.

A API permite controlar a exibição de valores, definir diferentes formatos de número para cada rótulo de dados e vincular o formato de número a uma célula de origem. Essa flexibilidade permite apresentar dados numéricos em gráficos com a formatação desejada, como símbolos de moeda, formatos de data e valores percentuais.

Ao usar o Aspose.Words for .NET, você pode incorporar poderosos recursos de gráficos em seus aplicativos .NET e gerar documentos de aparência profissional com gráficos e rótulos de dados totalmente formatados.

### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca de processamento de documentos rica em recursos que permite aos desenvolvedores criar, manipular e salvar documentos do Word programaticamente em aplicativos .NET. Ele fornece uma ampla gama de recursos para processamento de texto com elementos de documentos, incluindo gráficos e rótulos de dados.

#### Q2. Como posso instalar o Aspose.Words para .NET?
Você pode instalar o Aspose.Words for .NET baixando-o usando o gerenciador de pacotes NuGet no Visual Studio. Basta pesquisar “Apose.Words” no gerenciador de pacotes NuGet e instalá-lo em seu projeto.

#### Q3. Posso formatar outros aspectos do gráfico usando Aspose.Words for .NET?
Sim, o Aspose.Words for .NET oferece amplos recursos para formatar vários aspectos de um gráfico. Além dos rótulos de dados, você pode personalizar o tipo de gráfico, dados de série, propriedades de eixo, legenda, título, área de plotagem e muitos outros elementos do gráfico. A API oferece controle refinado sobre a aparência e formatação do gráfico.

#### Q4. Posso aplicar formatos numéricos diferentes a rótulos de dados diferentes na mesma série?
Sim, Aspose.Words for .NET permite aplicar diferentes formatos de números a rótulos de dados individuais dentro da mesma série. Ao acessar o`DataLabels` coleção associada a uma série, você pode definir o`FormatCode` propriedade de cada rótulo de dados para especificar o formato numérico desejado. Isso permite apresentar valores numéricos em diferentes formatos dentro do mesmo gráfico.

#### Q5. Posso usar formatos numéricos personalizados para rótulos de dados?
 Sim, Aspose.Words for .NET oferece suporte a formatos numéricos personalizados para rótulos de dados. Você pode especificar o formato de número desejado definindo o`FormatCode` propriedade de um rótulo de dados para um código de formato personalizado. Isso lhe dá flexibilidade para aplicar uma ampla variedade de formatos numéricos, como símbolos de moeda, formatos de data, valores percentuais e muito mais.

#### Q6. Posso salvar o gráfico com rótulos de dados formatados em formatos diferentes?
Sim, Aspose.Words for .NET permite salvar o documento que contém o gráfico com rótulos de dados formatados em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato apropriado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. Os rótulos de dados formatados serão preservados no documento salvo.