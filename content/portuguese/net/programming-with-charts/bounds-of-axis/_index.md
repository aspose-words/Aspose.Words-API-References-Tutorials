---
title: Limites do eixo em um gráfico
linktitle: Limites do eixo em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir os limites de um eixo em um gráfico usando Aspose.Words for .NET controlando o intervalo de valores exibidos no eixo.
type: docs
weight: 10
url: /pt/net/programming-with-charts/bounds-of-axis/
---

Este tutorial explica como definir os limites de um eixo em um gráfico usando Aspose.Words for .NET. Ao inserir um gráfico, adicionar dados de série e configurar a escala do eixo, você pode definir os valores mínimo e máximo do eixo.

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

## Etapa 3: inserir e configurar um gráfico
 Insira um gráfico no documento usando o`InsertChart` método do`DocumentBuilder` objeto. Defina o tipo e as dimensões do gráfico desejado.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 4: adicionar dados de série
Limpe qualquer série existente no gráfico e adicione novos dados de série. Neste exemplo, adicionamos uma série com rótulos “Item 1” a “Item 5” e valores correspondentes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Etapa 5: definir os limites do eixo
 Configure a escala do eixo Y definindo os valores mínimo e máximo usando o`Scaling.Minimum` e`Scaling.Maximum` propriedades do eixo.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Etapa 6: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Exemplo de código-fonte para Bounds Of Axis usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

É isso! Você definiu com êxito os limites de um eixo em um gráfico usando Aspose.Words for .NET.

## Conclusão
Neste tutorial, você aprendeu como definir os limites de um eixo em um gráfico usando Aspose.Words for .NET. Seguindo o passo a passo, você pode inserir e configurar um gráfico, adicionar dados de série e definir os valores mínimo e máximo para a escala do eixo. Aspose.Words for .NET fornece uma API poderosa e flexível para processamento de palavras com documentos do Word, permitindo criar gráficos dinâmicos e visualmente atraentes com facilidade.


### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca que permite aos desenvolvedores trabalhar com documentos do Word programaticamente. Ele oferece uma ampla gama de recursos e funcionalidades para criar, manipular e salvar documentos do Word.

#### Q2. Como posso instalar o Aspose.Words para .NET?
Para instalar o Aspose.Words for .NET, você pode usar o gerenciador de pacotes NuGet no Visual Studio. Basta pesquisar “Aspose.Words” no gerenciador de pacotes NuGet e instalá-lo em seu projeto.

#### Q3. Posso usar Aspose.Words for .NET com outras linguagens de programação?
Não, o Aspose.Words for .NET foi projetado especificamente para aplicativos .NET. Funciona com linguagens de programação como C# e VB.NET.

#### Q4. Existem outros pré-requisitos para usar o Aspose.Words for .NET?
Além de instalar a biblioteca Aspose.Words for .NET, você deve ter um conhecimento básico de programação C# e processamento de palavras com documentos Word. A familiaridade com o framework .NET também será útil.
