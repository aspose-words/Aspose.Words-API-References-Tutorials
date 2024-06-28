---
title: Gerando etiquetas de código de barras personalizadas em Aspose.Words para Java
linktitle: Gerando etiquetas de código de barras personalizadas
second_title: API de processamento de documentos Java Aspose.Words
description: Gere etiquetas de código de barras personalizadas em Aspose.Words para Java. Aprenda como criar soluções de código de barras personalizadas usando Aspose.Words for Java neste guia passo a passo.
type: docs
weight: 10
url: /pt/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Introdução à geração de etiquetas de código de barras personalizadas em Aspose.Words para Java

Neste guia abrangente, nos aprofundaremos no processo de geração de etiquetas de código de barras personalizadas usando Aspose.Words for Java. Aspose.Words for Java é uma API poderosa que permite aos desenvolvedores manipular documentos do Word programaticamente. Uma de suas características notáveis é a capacidade de trabalhar com etiquetas de código de barras, tornando-se uma ferramenta valiosa para empresas e organizações que necessitam de soluções personalizadas de código de barras.

## Pré-requisitos

Antes de nos aprofundarmos nos detalhes da geração de etiquetas de código de barras personalizadas, vamos garantir que temos os pré-requisitos em vigor:

1. Ambiente de Desenvolvimento Java: Certifique-se de ter Java e um Ambiente de Desenvolvimento Integrado (IDE) instalados em seu sistema.

2.  Aspose.Words para Java: Baixe e instale Aspose.Words para Java em[aqui](https://releases.aspose.com/words/java/).

3. Conhecimento básico de Java: A familiaridade com a programação Java será útil, pois escreveremos código Java para criar etiquetas de código de barras personalizadas.

## Criação de etiquetas de código de barras personalizadas

Agora, vamos começar a criar etiquetas de código de barras personalizadas usando Aspose.Words for Java. Dividiremos o processo em etapas e forneceremos trechos de código Java para cada etapa.

## Configurando a altura do código de barras

Para começar, precisamos definir a altura do nosso código de barras em twips (1/1440 polegadas). Em seguida, converteremos esse valor para milímetros (mm). Aqui está o código para fazer isso:

```java
	// O valor de entrada está em 1/1440 polegadas (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Converter para mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Convertendo a cor da imagem do código de barras

A seguir, converteremos a cor da imagem do código de barras do Word para Aspose.BarCode. A cor de entrada deve estar no formato “0xRRGGBB” (hexadecimal). Aqui está o código para a conversão:

```java
/// <resumo>
/// Converte a cor da imagem do código de barras do Word para Aspose.BarCode.
/// </resumo>
/// <param name="inputColor"></param>
/// <retorna></retorna>
private static Color convertColor(String inputColor) throws Exception {
	// A entrada deve ser de "0x000000" a "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Convertendo fator de escala de código de barras

Agora, converteremos o fator de escala do código de barras de uma porcentagem para um valor flutuante. Este fator de escala determina o tamanho do código de barras. Aqui está o código para a conversão:

```java
/// <resumo>
/// Converte o fator de escala do código de barras de porcentagem para flutuante.
/// </resumo>
/// <param name="scalingFactor"></param>
/// <retorna></retorna>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## Implementando o método GetBarCodeImage()

 Nesta etapa, implementaremos o`getBarcodeImage` método, que gera a imagem do código de barras com base nos parâmetros fornecidos. Lidaremos com diferentes tipos de códigos de barras, definiremos cores, ajustaremos dimensões e muito mais. Aqui está o código para este método:

```java
/// <resumo>
/// Implementação do método GetBarCodeImage() para interface IBarCodeGenerator.
/// </resumo>
/// <param name="parâmetros"></param>
/// <retorna></retorna>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Verifique se o tipo e o valor do código de barras são fornecidos
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Crie um BarcodeGenerator com base no tipo de código de barras
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Lide com outros tipos de código de barras aqui
	}
	
	// Defina o texto do código de barras
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Definir cores de código de barras
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Definir altura e dimensões do símbolo
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Personalize a localização do texto do código
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Ajustes adicionais para códigos QR
	final float SCALE = 2.4f; // Fator de escala empírico para conversão de código de barras do Word em Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Aplicar fator de escala
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Gere e retorne a imagem do código de barras
	return generator.generateBarCodeImage();
}
```

## Implementando o método GetOldBarcodeImage()

 Nesta etapa, implementaremos o`getOldBarcodeImage` método, que gera imagens de código de barras para códigos de barras antigos. Aqui, lidaremos com um tipo específico de código de barras, como POSTNET. Aqui está o código para este método:

```java
/// <resumo>
/// Implementação do método GetOldBarcodeImage() para interface IBarCodeGenerator.
/// </resumo>
/// <param name="parâmetros"></param>
/// <retorna></retorna>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Tipo de código rígido para código de barras antigo
	return generator.generateBarCodeImage();
}
```

## Conclusão

Neste artigo, exploramos o processo de geração de etiquetas de código de barras personalizadas usando Aspose.Words for Java. Abordamos etapas essenciais, desde a definição da altura do código de barras até a implementação de métodos para geração de código de barras. Aspose.Words for Java capacita os desenvolvedores a criar etiquetas de código de barras dinâmicas e personalizadas, tornando-o uma ferramenta valiosa para vários setores.

## Perguntas frequentes

### Como posso ajustar o tamanho do código de barras gerado?

Você pode ajustar o tamanho do código de barras gerado definindo a altura do símbolo do código de barras e o fator de escala nos trechos de código fornecidos. Esses parâmetros permitem controlar as dimensões do código de barras de acordo com suas necessidades.

### Posso alterar as cores do código de barras?

Sim, você pode alterar as cores do código de barras especificando as cores de primeiro e segundo plano no código. Essa personalização permite combinar a aparência do código de barras com o design do seu documento.

### Quais tipos de código de barras são suportados pelo Aspose.Words for Java?

Aspose.Words for Java suporta vários tipos de códigos de barras, incluindo códigos QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 e muito mais. Você pode escolher o tipo de código de barras que atende às necessidades da sua aplicação.

### Como integro o código de barras gerado ao meu documento Word?

Para integrar o código de barras gerado ao seu documento do Word, você pode usar os recursos de manipulação de documentos do Aspose.Words for Java. Você pode inserir a imagem do código de barras em seu documento no local desejado.

### Existe algum código de exemplo disponível para personalização adicional?

 Sim, você pode encontrar trechos de código de amostra e documentação adicional no site de referência do Aspose.Words for Java:[Referência da API Aspose.Words para Java](https://reference.aspose.com/words/java/).