---
title: Marque o alinhamento do rótulo multilinha em um gráfico
linktitle: Marque o alinhamento do rótulo multilinha em um gráfico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como alinhar rótulos de múltiplas linhas em um eixo de gráfico usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-charts/tick-multi-line-label-alignment/
---

Este tutorial explica como usar Aspose.Words for .NET para definir o alinhamento de rótulos de múltiplas linhas em um eixo do gráfico. O código-fonte fornecido demonstra como criar um gráfico, acessar o eixo e modificar o alinhamento do rótulo do tick.

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

 A seguir, use o`InsertChart` método do`DocumentBuilder` para inserir um gráfico de dispersão no documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Etapa 3: definir o alinhamento do rótulo de escala

 Para definir o alinhamento dos rótulos multilinhas dos ticks, acesse o`AxisX` propriedade do gráfico e defina o`TickLabelAlignment` propriedade para o alinhamento desejado. Neste exemplo, definimos o alinhamento para`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Etapa 4: salve o documento

 Finalmente, salve o documento no diretório especificado usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Isso conclui a implementação da configuração do alinhamento do rótulo multilinha usando Aspose.Words for .NET.

### Exemplo de código-fonte para Tick Multi Line Label Alignment usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Esta propriedade tem efeito apenas para rótulos multilinhas.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Conclusão

Neste tutorial, você aprendeu como definir o alinhamento de rótulos de múltiplas linhas em um eixo de gráfico usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, você pode criar um novo documento, inserir um gráfico de dispersão, acessar o eixo do gráfico e modificar o alinhamento do rótulo do tick.

Aspose.Words for .NET fornece recursos poderosos para manipular gráficos em documentos do Word. Os rótulos de múltiplas linhas são úteis quando os rótulos dos eixos contêm texto longo que requer quebra automática ou divisão em várias linhas. Ao definir o alinhamento do rótulo de escala, você pode controlar o alinhamento horizontal de rótulos multilinhas dentro do eixo do gráfico, garantindo apresentação e legibilidade ideais.

Personalizar o alinhamento dos rótulos multilinhas permite ajustar a aparência do seu gráfico, especialmente ao lidar com rótulos longos ou complexos. Ao alinhar os rótulos à direita, à esquerda, ao centro ou justificados, você pode obter um arranjo equilibrado e visualmente atraente dos rótulos de escala ao longo do eixo.

Com Aspose.Words for .NET, você pode acessar e modificar facilmente a propriedade de alinhamento do rótulo de escala de um eixo do gráfico, fornecendo controle total sobre a aparência e o layout dos rótulos de escala em seus gráficos de documentos do Word.

### Perguntas frequentes

#### Q1. O que são rótulos multilinhas em um eixo do gráfico?
Os rótulos de múltiplas linhas em um eixo do gráfico referem-se aos rótulos dos eixos que se estendem por várias linhas quando o texto do rótulo é longo ou requer quebra automática para caber no espaço disponível. Em vez de truncar o texto do rótulo ou causar confusão visual, o eixo do gráfico divide automaticamente os rótulos em várias linhas para garantir a legibilidade. Os rótulos de múltiplas linhas são particularmente úteis ao lidar com rótulos longos de categorias ou valores em gráficos.

#### Q2. Posso personalizar o alinhamento dos rótulos de escala em um eixo do gráfico?
 Sim, você pode personalizar o alinhamento dos rótulos de escala em um eixo do gráfico usando Aspose.Words for .NET. Ao acessar o`TickLabelAlignment` propriedade do`ChartAxis` objeto, você pode definir o alinhamento desejado para os rótulos de escala. As opções de alinhamento incluem alinhamento à esquerda, à direita, centralizado ou justificado. Ajustar o alinhamento permite controlar o posicionamento horizontal dos rótulos de escala ao longo do eixo do gráfico, garantindo legibilidade e apresentação visual adequadas.

#### Q3. Quando devo considerar alterar o alinhamento do rótulo de escala em um eixo do gráfico?
Alterar o alinhamento do rótulo de escala em um eixo do gráfico é benéfico quando você tem rótulos longos ou com várias linhas que exigem apresentação e legibilidade ideais. Ao ajustar o alinhamento, você pode garantir que as etiquetas estejam devidamente alinhadas e espaçadas, evitando sobreposições ou truncamentos. Considere alterar o alinhamento do rótulo de escala ao lidar com gráficos que possuem nomes de categorias longos, rótulos de valores detalhados ou quaisquer outros cenários em que o alinhamento padrão não fornece a aparência visual desejada.

#### Q4. O alinhamento do rótulo do tick afeta rótulos de linha única em um eixo do gráfico?
Não, a propriedade de alinhamento do rótulo de escala não afeta rótulos de linha única em um eixo do gráfico. Ele foi projetado especificamente para etiquetas multilinhas que exigem embalagem ou divisão. Os rótulos de linha única são alinhados com base nas configurações de alinhamento padrão do eixo do gráfico. A propriedade de alinhamento do rótulo de escala só se aplica a rótulos que se estendem por diversas linhas, permitindo controlar o alinhamento de cada linha dentro do rótulo de múltiplas linhas.

#### Q5. Posso alinhar rótulos de escala de maneira diferente para o eixo X e o eixo Y em um gráfico?
 Sim, você pode alinhar rótulos de escala de maneira diferente para o eixo X e o eixo Y em um gráfico usando Aspose.Words for .NET. A propriedade de alinhamento do rótulo de escala é específica para cada eixo do gráfico. Ao acessar o correspondente`ChartAxis` objeto para o eixo X ou eixo Y, você pode definir independentemente o alinhamento do rótulo de escala para valores diferentes. Isso fornece flexibilidade para alinhar rótulos de escala de maneira diferente com base em seus requisitos específicos para cada eixo do gráfico.