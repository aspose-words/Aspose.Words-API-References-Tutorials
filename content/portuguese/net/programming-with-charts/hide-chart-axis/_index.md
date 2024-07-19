---
title: Ocultar o eixo do gráfico em um documento do Word
linktitle: Ocultar o eixo do gráfico em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ocultar o eixo do gráfico em um documento do Word usando Aspose.Words for .NET com nosso tutorial passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-charts/hide-chart-axis/
---
## Introdução

A criação de documentos Word dinâmicos e visualmente atraentes geralmente envolve a incorporação de tabelas e gráficos. Um desses cenários pode exigir a ocultação do eixo do gráfico para uma apresentação mais limpa. Aspose.Words for .NET fornece uma API abrangente e fácil de usar para tais tarefas. Este tutorial irá guiá-lo através das etapas para ocultar um eixo de gráfico em um documento do Word usando Aspose.Words for .NET.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:

-  Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: qualquer IDE que ofereça suporte ao desenvolvimento .NET, como Visual Studio.
- .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
- Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces

Para começar a trabalhar com Aspose.Words for .NET, você precisa importar os namespaces necessários em seu projeto. Veja como você pode fazer isso:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Vamos dividir o processo em etapas simples e fáceis de seguir.

## Etapa 1: inicializar o documento e o DocumentBuilder

primeira etapa envolve a criação de um novo documento do Word e a inicialização do objeto DocumentBuilder.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Nesta etapa definimos o caminho onde o documento será salvo. Criamos então um novo`Document` objeto e um`DocumentBuilder` objeto para começar a construir nosso documento.

## Etapa 2: inserir um gráfico

 A seguir, inseriremos um gráfico no documento usando o`DocumentBuilder` objeto.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 Aqui, inserimos um gráfico de colunas com dimensões especificadas. O`InsertChart` método retorna um`Shape` objeto que contém o gráfico.

## Etapa 3: limpar séries existentes

Antes de adicionar novos dados ao gráfico, precisamos limpar todas as séries existentes.

```csharp
chart.Series.Clear();
```

Esta etapa garante que todos os dados padrão do gráfico sejam removidos, abrindo caminho para os novos dados que adicionaremos a seguir.

## Etapa 4: adicionar dados de série

Agora, vamos adicionar nossa própria série de dados ao gráfico.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

Nesta etapa, adicionamos uma série intitulada "Aspose Series 1" com categorias e valores correspondentes.

## Etapa 5: ocultar o eixo Y

 Para ocultar o eixo Y do gráfico, simplesmente definimos o`Hidden` propriedade do eixo Y para`true`.

```csharp
chart.AxisY.Hidden = true;
```

Esta linha de código oculta o eixo Y, tornando-o invisível no gráfico.

## Etapa 6: salve o documento

Finalmente, salve o documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Este comando salva o documento do Word com o gráfico no caminho especificado.

## Conclusão

Parabéns! Você aprendeu com sucesso como ocultar um eixo de gráfico em um documento do Word usando Aspose.Words for .NET. Esta poderosa biblioteca facilita a manipulação programática de documentos do Word. Seguindo essas etapas, você pode criar documentos personalizados e com aparência profissional com o mínimo de esforço.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma API poderosa para criar, editar, converter e manipular documentos Word em aplicativos .NET.

### Posso ocultar os eixos X e Y em um gráfico?
 Sim, você pode ocultar ambos os eixos definindo o`Hidden` propriedade de ambos`AxisX`e`AxisY` para`true`.

### Existe um teste gratuito disponível para Aspose.Words for .NET?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Onde posso encontrar mais documentação?
 Você pode encontrar documentação detalhada no Aspose.Words for .NET[aqui](https://reference.aspose.com/words/net/).

### Como posso obter suporte para Aspose.Words for .NET?
 Você pode obter suporte da comunidade Aspose[aqui](https://forum.aspose.com/c/words/8).
