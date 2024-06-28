---
title: Formato numérico para eixo em um gráfico
linktitle: Formato numérico para eixo em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o formato numérico de um eixo em um gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/number-format-for-axis/
---

Este tutorial explica como usar Aspose.Words for .NET para definir o formato numérico de um eixo em um gráfico. O código-fonte fornecido demonstra como criar um gráfico, adicionar dados de série e formatar os rótulos dos eixos.

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

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de colunas no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Etapa 3: adicionar dados de série ao gráfico

Adicione dados de série ao gráfico. Neste exemplo, adicionaremos cinco itens com seus valores correspondentes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Etapa 4: formate os rótulos dos eixos

 Para definir o formato numérico para os rótulos do eixo Y, acesse o`AxisY` propriedade do gráfico e defina o`NumberFormat.FormatCode` propriedade para o formato desejado. Neste exemplo, definimos o formato como "#,##0" para exibir números com separadores de milhares.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Etapa 5: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Isso conclui a implementação da configuração do formato numérico do eixo usando Aspose.Words for .NET.

### Exemplo de código-fonte para Number Format For Axis usando Aspose.Words for .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Conclusão

Neste tutorial, você aprendeu como definir o formato numérico de um eixo em um gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de colunas, adicionar dados de série e formatar os rótulos dos eixos para exibir números em um formato específico.

Aspose.Words for .NET fornece recursos poderosos para personalizar a aparência de gráficos em documentos do Word. Ao definir o formato numérico dos rótulos dos eixos, você pode controlar como os números são exibidos, incluindo opções como casas decimais, separadores de milhares, símbolos de moeda e muito mais. Isso permite apresentar dados numéricos de forma clara e significativa.

Com Aspose.Words for .NET, você tem flexibilidade para formatar vários aspectos do gráfico, incluindo os rótulos dos eixos. Ao definir o formato numérico do eixo, você pode garantir consistência e melhorar a legibilidade do gráfico, facilitando a interpretação dos valores representados pelos usuários.

### Perguntas frequentes

#### Q1. Qual é o formato numérico de um eixo em um gráfico?
O formato numérico de um eixo em um gráfico refere-se à formatação aplicada aos valores numéricos exibidos no eixo. Ele permite controlar como os números são apresentados, incluindo opções como casas decimais, separadores de milhares, símbolos de moeda, sinais de porcentagem e muito mais. Ao definir o formato numérico, você pode personalizar a aparência dos dados numéricos no gráfico para atender às suas necessidades específicas.

#### Q2. Como posso definir o formato numérico dos rótulos dos eixos?
 Para definir o formato numérico para os rótulos dos eixos em um gráfico usando Aspose.Words for .NET, você pode acessar o`AxisY` propriedade do gráfico e defina o`NumberFormat.FormatCode`propriedade para o código de formato desejado. O código de formato segue a sintaxe dos padrões de formatação numérica padrão e determina como os números são exibidos. Por exemplo, você pode usar "#,##0,00" para exibir números com duas casas decimais e separadores de milhar.

#### Q3. Posso definir formatos numéricos diferentes para os rótulos dos eixos X e Y?
Sim, você pode definir diferentes formatos numéricos para os rótulos do eixo X e do eixo Y usando Aspose.Words for .NET. Acesse o respectivo eixo (`AxisX` para eixo X ou`AxisY` para o eixo Y) do gráfico e modifique o`NumberFormat.FormatCode` propriedade individualmente para cada eixo. Isso permite que você aplique diferentes formatos de números aos rótulos de cada eixo com base em seus requisitos específicos.

#### Q4. Quais são alguns códigos de formato numérico comuns que posso usar?
Aspose.Words for .NET oferece suporte a uma ampla variedade de códigos de formato numérico que você pode usar para formatar os rótulos dos eixos em um gráfico. Alguns códigos de formato comuns incluem:

- `0` ou`#` - Exibe o número sem casas decimais.
- `0.00` ou`#.00` - Exibe o número com duas casas decimais.
- `#,##0` Exibe o número com milhares de separadores.
- `"€"0.00` - Exibe o número com o símbolo da moeda Euro e duas casas decimais.
- `"%"0` - Exibe o número como uma porcentagem.

 Você pode encontrar mais informações sobre o número[códigos de formato](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) na Referência da API do Aspose.Words para .NET.

#### Q5. Posso personalizar outras propriedades dos rótulos dos eixos?
Sim, Aspose.Words for .NET fornece uma ampla gama de propriedades para personalizar a aparência e o comportamento dos rótulos dos eixos. Além do formato numérico, você pode modificar propriedades como fonte, tamanho, cor, orientação, alinhamento e muito mais. Isso permite que você personalize totalmente os rótulos dos eixos para corresponder ao estilo e aos requisitos de apresentação desejados.