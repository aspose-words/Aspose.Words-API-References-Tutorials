---
title: Converter entre unidades de medida
linktitle: Converter entre unidades de medida
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para converter unidades de medida em um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/convert-between-measurement-units/
---

Neste tutorial, orientaremos você no código-fonte C# para converter entre unidades de medida com Aspose.Words for .NET. Este recurso permite especificar margens, distâncias de cabeçalho e rodapé, etc. em diferentes unidades de medida.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Etapa 2: Criando o Documento e o Construtor

Nesta etapa criaremos um novo documento e inicializaremos o construtor. Use o seguinte código:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 3: Configurar unidades de medida

Agora iremos converter os valores das margens, distâncias do cabeçalho e rodapé, etc. em diferentes unidades de medida. Use o código a seguir para especificar valores em unidades de medida específicas:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Este código usa o`ConvertUtil` classe de Aspose.Words para converter os valores especificados em polegadas (`InchToPoint`). Você também pode usar outros métodos de conversão disponíveis no`ConvertUtil` classe para converter valores para outras unidades de medida.

### Exemplo de código-fonte para conversão entre unidades de medida usando Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Agora você aprendeu como converter entre unidades de medida ao especificar margens, distâncias de cabeçalho e rodapé, etc. em um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode especificar facilmente os valores nas unidades de medida desejadas em seus próprios documentos.