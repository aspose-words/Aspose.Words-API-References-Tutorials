---
title: Definir opções padrão para rótulos de dados em um gráfico
linktitle: Definir opções padrão para rótulos de dados em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir opções padrão para rótulos de dados em um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/default-options-for-data-labels/
---

Este tutorial explica como usar Aspose.Words for .NET para definir opções padrão para rótulos de dados em um gráfico. O código fornecido demonstra como criar um gráfico, adicionar séries de dados e personalizar os rótulos de dados usando Aspose.Words.

## Etapa 1: configurar o projeto

Antes de começarmos, certifique-se de ter os seguintes requisitos em vigor:

- Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo usando o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório do documento onde o documento de saída será salvo.

## Passo 2: Crie um novo documento e insira um gráfico.

 Primeiro, vamos criar um novo`Document` objeto e um`DocumentBuilder` para construir o documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A seguir, inserimos um gráfico no documento usando o`InsertChart` método do`DocumentBuilder`. Neste exemplo, inseriremos um gráfico de pizza.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar séries de dados ao gráfico

Agora, vamos adicionar uma série de dados ao gráfico. Neste exemplo, adicionaremos três categorias e seus valores correspondentes.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Etapa 4: personalizar rótulos de dados

 Para personalizar os rótulos de dados no gráfico, precisamos acessar o`ChartDataLabelCollection` objeto associado à série.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Podemos então modificar várias propriedades do`labels`objeto para definir as opções desejadas para rótulos de dados. Neste exemplo, ativaremos a exibição da porcentagem e do valor, desativaremos as linhas líderes e definiremos um separador personalizado.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Etapa 5: salve o documento

 Finalmente, salvamos o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Isso conclui a implementação da configuração de opções padrão para rótulos de dados em um gráfico usando Aspose.Words for .NET.

### Exemplo de código-fonte para opções padrão para rótulos de dados usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Conclusão

Neste tutorial, você aprendeu como definir opções padrão para rótulos de dados em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo, você pode criar um gráfico, adicionar séries de dados e personalizar os rótulos de dados para atender aos seus requisitos específicos. Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com gráficos em documentos do Word, permitindo manipular vários elementos do gráfico e obter a aparência e funcionalidade desejadas.

 Ao definir as propriedades do`ChartDataLabelCollection`objeto associado à série de gráficos, você pode controlar a exibição de rótulos de dados, incluindo opções como mostrar porcentagens, valores, linhas de chamada e separadores personalizados. Essa flexibilidade permite apresentar dados de maneira eficaz e aprimorar a representação visual de seus gráficos.

### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca que permite aos desenvolvedores criar, manipular e salvar documentos do Word programaticamente usando aplicativos .NET. Ele fornece uma ampla gama de recursos para processamento de texto com elementos de documentos, incluindo gráficos.

#### Q2. Como posso instalar o Aspose.Words para .NET?
Você pode instalar o Aspose.Words for .NET baixando-o usando o gerenciador de pacotes NuGet no Visual Studio. Basta pesquisar “Apose.Words” no gerenciador de pacotes NuGet e instalá-lo em seu projeto.

#### Q3. Posso personalizar outros aspectos do gráfico usando Aspose.Words for .NET?
Sim, Aspose.Words for .NET permite personalizar vários aspectos de um gráfico, como tipo de gráfico, rótulos de eixo, legenda, área de plotagem e muito mais. Você pode acessar e modificar diferentes propriedades do objeto gráfico para obter a aparência e o comportamento desejados.

#### Q4. Posso salvar o gráfico em diferentes formatos?
 Sim, Aspose.Words for .NET suporta salvar o documento que contém o gráfico em vários formatos, incluindo DOCX, PDF, HTML e muito mais. Você pode escolher o formato apropriado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento.

#### Q5. Posso aplicar essas técnicas a outros tipos de gráficos?
Sim, as técnicas descritas neste tutorial podem ser aplicadas a outros tipos de gráficos suportados pelo Aspose.Words for .NET. A chave é acessar os objetos e propriedades relevantes específicos para o tipo de gráfico com o qual você está processando palavras.