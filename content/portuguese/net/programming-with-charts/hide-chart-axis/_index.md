---
title: Ocultar o eixo do gráfico em um documento do Word
linktitle: Ocultar o eixo do gráfico em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ocultar o eixo do gráfico em um documento usando Aspose.Words for .NET. Oculte o eixo para obter uma exibição do gráfico mais limpa e focada.
type: docs
weight: 10
url: /pt/net/programming-with-charts/hide-chart-axis/
---

Este tutorial explica como usar Aspose.Words for .NET para ocultar o eixo do gráfico em um documento. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e ocultar o eixo do gráfico.

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

 Em seguida, insira um gráfico no documento usando o`InsertChart` método do`DocumentBuilder`. Neste exemplo, inseriremos um gráfico de colunas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos cinco itens e seus valores correspondentes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Etapa 4: ocultar o eixo do gráfico

 Para ocultar o eixo do gráfico, acesse o`AxisY` propriedade do gráfico e defina o`Hidden`propriedade para`true`.

```csharp
chart.AxisY.Hidden = true;
```

Neste exemplo, ocultamos o eixo Y do gráfico.

## Etapa 5: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Isso completa a implementação de ocultar o eixo do gráfico usando Aspose.Words for .NET.

### Exemplo de código-fonte para ocultar o eixo do gráfico usando Aspose.Words para .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Conclusão

Neste tutorial, você aprendeu como ocultar o eixo do gráfico em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e usando o código-fonte fornecido, você pode criar um gráfico, adicionar dados de série e ocultar o eixo do gráfico para obter o efeito visual desejado.

 Aspose.Words for .NET fornece uma API abrangente para processamento de palavras com gráficos em documentos do Word, permitindo manipular vários aspectos do gráfico, incluindo propriedades do eixo. Ao acessar o`AxisY` propriedade do gráfico, você pode ocultar o eixo Y para removê-lo da visualização do gráfico.

Ocultar o eixo do gráfico pode ser útil quando você deseja focar nos dados do gráfico sem a distração das linhas e rótulos dos eixos. Ele fornece uma aparência mais limpa e minimalista ao gráfico.

Ao usar o Aspose.Words for .NET, você pode incorporar facilmente recursos de gráficos em seus aplicativos .NET e gerar documentos de aparência profissional com gráficos personalizados e eixos de gráfico ocultos.

### Perguntas frequentes

#### Q1. O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, manipular e salvar documentos do Word programaticamente em aplicativos .NET. Ele fornece uma ampla gama de recursos para processamento de texto com elementos de documentos, incluindo gráficos e eixos de gráficos.

#### Q2. Como posso instalar o Aspose.Words para .NET?
Você pode instalar o Aspose.Words for .NET baixando-o usando o gerenciador de pacotes NuGet no Visual Studio. Basta pesquisar “Apose.Words” no gerenciador de pacotes NuGet e instalá-lo em seu projeto.

#### Q3. Posso ocultar o eixo X e o eixo Y de um gráfico?
 Sim, você pode ocultar o eixo X e o eixo Y de um gráfico usando Aspose.Words for .NET. Para ocultar o eixo X, você pode acessar o`AxisX` propriedade do gráfico e defina o`Hidden`propriedade para`true` . Da mesma forma, para ocultar o eixo Y, você pode acessar o`AxisY` propriedade e definir o`Hidden`propriedade para`true`. Isso permite remover ambos os eixos da visualização do gráfico.

#### Q4. Posso mostrar o eixo novamente depois de ocultá-lo?
Sim, você pode mostrar o eixo do gráfico novamente depois de ocultá-lo usando Aspose.Words for .NET. Para mostrar um eixo oculto, basta definir o`Hidden` propriedade do correspondente`AxisX` ou`AxisY` opor-se a`false`. Isso tornará o eixo visível novamente no gráfico.

#### Q5. Posso personalizar outras propriedades do eixo do gráfico?
 Sim, Aspose.Words for .NET permite personalizar várias propriedades do eixo do gráfico, como título do eixo, rótulos, cor da linha e muito mais. Ao acessar o`AxisX` e`AxisY` propriedades do gráfico, você pode modificar propriedades como`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, e muitos outros. Isso oferece controle refinado sobre a aparência e o comportamento do eixo do gráfico.

#### Q6. Posso salvar o gráfico com o eixo oculto em diferentes formatos de arquivo?
 Sim, Aspose.Words for .NET permite salvar o documento que contém o gráfico com um eixo oculto em vários formatos de arquivo, como DOCX, PDF, HTML e muito mais. Você pode escolher o formato de saída desejado com base em seus requisitos e usar o`Save` método do`Document` objeto para salvar o documento. O eixo oculto será preservado no documento salvo.