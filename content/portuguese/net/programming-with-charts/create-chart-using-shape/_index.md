---
title: Crie e personalize gráfico usando forma
linktitle: Crie e personalize gráfico usando forma
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar e personalizar um gráfico usando uma forma em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/create-chart-using-shape/
---

Este tutorial explica como criar um gráfico usando uma forma em um documento do Word usando Aspose.Words for .NET.

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
 Crie uma nova instância do`Document` aula e um`DocumentBuilder`objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir e configurar um formato de gráfico
 Insira uma forma de gráfico no documento usando o`InsertChart` método do`DocumentBuilder` objeto. Defina o tipo e as dimensões do gráfico desejado.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 4: personalize o gráfico
Personalize o gráfico modificando várias propriedades, como título e legenda do gráfico.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Etapa 5: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Exemplo de código-fonte para criar gráfico usando forma usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Observe que se um valor nulo ou vazio for especificado como texto do título, o título gerado automaticamente será mostrado.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

É isso! Você criou com sucesso um gráfico usando uma forma em um documento do Word usando Aspose.Words for .NET.

## Conclusão
Neste tutorial, você aprendeu como criar um gráfico usando uma forma em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo, você pode inserir e configurar um formato de gráfico, personalizar sua aparência e salvar o documento. Aspose.Words for .NET fornece um conjunto abrangente de recursos para processamento de palavras com documentos e gráficos do Word, permitindo que você crie gráficos com aparência profissional e visualmente atraentes diretamente em seus aplicativos .NET.

### Perguntas frequentes

#### Q1. Posso criar gráficos em um documento do Word usando Aspose.Words for .NET?
Sim, com Aspose.Words for .NET, você pode criar gráficos em um documento do Word programaticamente. Aspose.Words fornece APIs e funcionalidades para inserir vários tipos de gráficos, personalizar sua aparência e manipular dados de gráficos.

#### Q2. Quais tipos de gráficos são suportados pelo Aspose.Words for .NET?
Aspose.Words for .NET oferece suporte a uma ampla variedade de tipos de gráficos, incluindo gráficos de linhas, gráficos de barras, gráficos de pizza, gráficos de área, gráficos de dispersão e muito mais. Você pode escolher o tipo de gráfico apropriado com base em seus dados e requisitos de visualização.

#### Q3. Posso personalizar a aparência do gráfico criado?
Sim, você pode personalizar a aparência do gráfico criado usando Aspose.Words for .NET. Você pode modificar propriedades como título do gráfico, posição da legenda, rótulos de dados, rótulos de eixos, cores e outros elementos visuais para atender às suas necessidades específicas de design e formatação.
