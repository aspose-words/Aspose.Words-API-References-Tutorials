---
title: Insira um gráfico de colunas simples em um documento do Word
linktitle: Insira um gráfico de colunas simples em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um gráfico de colunas simples em um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/insert-simple-column-chart/
---

Este tutorial explica como usar Aspose.Words for .NET para inserir um gráfico de colunas simples em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e salvar o documento.

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

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de colunas no documento. Você pode especificar diferentes tipos e tamanhos de gráficos de acordo com suas necessidades.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos várias séries com duas categorias cada.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Isso completa a implementação da inserção de um gráfico de colunas simples usando Aspose.Words for .NET.

### Exemplo de código-fonte para inserir gráfico de colunas simples usando Aspose.Words para .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Você pode especificar diferentes tipos e tamanhos de gráficos.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Exclua a série gerada padrão.
	seriesColl.Clear();
	// Crie um array de nomes de categorias, neste tutorial temos duas categorias.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Observe que as matrizes de dados não devem estar vazias e as matrizes devem ter o mesmo tamanho.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Conclusão

Neste tutorial, você aprendeu como inserir um gráfico de colunas simples em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de colunas, adicionar várias séries com categorias e valores correspondentes e salvar o documento com o gráfico.

Aspose.Words for .NET fornece uma API poderosa e flexível para processamento de palavras com gráficos em documentos do Word. O gráfico de colunas simples é uma forma eficaz de representar e comparar dados em diferentes categorias. Com Aspose.Words for .NET, você pode criar facilmente gráficos de colunas com dados personalizados, adicionar várias séries para comparação visual e personalizar a aparência do gráfico de acordo com suas necessidades.

Ao usar o Aspose.Words for .NET, você pode automatizar o processo de geração de documentos com gráficos de colunas, economizando tempo e esforço na criação manual de documentos. A biblioteca oferece uma ampla variedade de tipos de gráficos, incluindo gráficos de colunas simples, e oferece várias opções de personalização para adaptar a aparência do gráfico às suas necessidades.

### Perguntas frequentes

#### Q1. O que é um gráfico de colunas?
Um gráfico de colunas é um tipo de gráfico que exibe dados usando barras verticais de alturas variadas. Cada coluna representa uma categoria e a altura da coluna corresponde ao valor dessa categoria. Os gráficos de colunas são comumente usados para comparar dados em diferentes categorias ou para rastrear alterações ao longo do tempo.

#### Q2. Posso adicionar várias séries ao gráfico de colunas?
Sim, usando Aspose.Words for .NET, você pode adicionar várias séries ao gráfico de colunas. Cada série representa um conjunto de pontos de dados com suas respectivas categorias e valores. Ao adicionar várias séries, você pode comparar e analisar diferentes conjuntos de dados no mesmo gráfico de colunas, fornecendo uma visão abrangente dos seus dados.

#### Q3. Posso personalizar a aparência do gráfico de colunas?
Sim, Aspose.Words for .NET permite personalizar vários aspectos da aparência do gráfico de colunas. Você pode modificar propriedades como cor da série, rótulos de eixos, rótulos de dados e formatação de área do gráfico. A biblioteca fornece um rico conjunto de APIs para controlar os elementos visuais do gráfico e criar uma aparência personalizada que atenda às suas necessidades.

#### Q4. Posso salvar o documento com o gráfico de colunas inserido em diferentes formatos?
 Sim, Aspose.Words for .NET permite salvar o documento com o gráfico de colunas inserido em vários formatos, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O gráfico de colunas inserido será preservado no documento salvo.

#### Q5. Posso modificar os dados e a aparência do gráfico de colunas após inseri-lo?
Sim, após inserir o gráfico de colunas no documento, você pode modificar seus dados e aparência utilizando as APIs fornecidas pelo Aspose.Words for .NET. Você pode atualizar os dados da série com novas categorias e valores, alterar as cores e a formatação das colunas, personalizar as propriedades dos eixos e aplicar várias opções de formatação para criar gráficos dinâmicos e visualmente atraentes em seus documentos do Word.