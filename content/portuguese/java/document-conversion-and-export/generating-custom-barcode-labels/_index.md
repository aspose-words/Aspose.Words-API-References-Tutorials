---
title: Gerando etiquetas de código de barras personalizadas no Aspose.Words para Java
linktitle: Gerando etiquetas de código de barras personalizadas
second_title: API de processamento de documentos Java Aspose.Words
description: Gere Etiquetas de Código de Barras Personalizadas no Aspose.Words para Java. Aprenda a criar soluções de código de barras personalizadas usando o Aspose.Words para Java neste guia passo a passo.
type: docs
weight: 10
url: /pt/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Introdução à geração de etiquetas de código de barras personalizadas no Aspose.Words para Java

Neste guia abrangente, vamos nos aprofundar no processo de geração de etiquetas de código de barras personalizadas usando o Aspose.Words para Java. O Aspose.Words para Java é uma API poderosa que permite que os desenvolvedores manipulem documentos do Word programaticamente. Um de seus recursos notáveis é a capacidade de trabalhar com etiquetas de código de barras, tornando-o uma ferramenta valiosa para empresas e organizações que exigem soluções de código de barras personalizadas.

## Pré-requisitos

Antes de nos aprofundarmos nos detalhes da geração de etiquetas de código de barras personalizadas, vamos garantir que temos os pré-requisitos em vigor:

1. Ambiente de desenvolvimento Java: certifique-se de ter o Java e um Ambiente de Desenvolvimento Integrado (IDE) instalados no seu sistema.

2.  Aspose.Words para Java: Baixe e instale o Aspose.Words para Java em[aqui](https://releases.aspose.com/words/java/).

3. Conhecimento básico de Java: familiaridade com programação Java será útil, pois escreveremos código Java para criar etiquetas de código de barras personalizadas.

## Criação de etiquetas de código de barras personalizadas

Agora, vamos começar a criar etiquetas de código de barras personalizadas usando Aspose.Words para Java. Vamos dividir o processo em etapas e fornecer trechos de código Java para cada etapa.

## Definindo a altura do código de barras

Para começar, precisamos definir a altura do nosso código de barras em twips (1/1440 polegadas). Então, converteremos esse valor para milímetros (mm). Aqui está o código para fazer isso:

```java
	// O valor de entrada está em 1/1440 polegadas (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Converter para mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Convertendo a cor da imagem do código de barras

Em seguida, converteremos a cor da imagem do código de barras do Word para Aspose.BarCode. A cor de entrada deve estar no formato "0xRRGGBB" (hexadecimal). Aqui está o código para a conversão:

```java
/// <resumo>
/// Converte a cor da imagem do código de barras do Word para Aspose.BarCode.
/// </resumo>
/// <param nome="inputColor"></param>
/// <retorna></retorna>
private static Color convertColor(String inputColor) throws Exception {
	// A entrada deve ser de "0x000000" a "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Convertendo Fator de Escala de Código de Barras

Agora, converteremos o fator de escala do código de barras de uma porcentagem para um valor flutuante. Esse fator de escala determina o tamanho do código de barras. Aqui está o código para a conversão:

```java
/// <resumo>
/// Converte o fator de escala do código de barras de porcentagem para flutuante.
/// </resumo>
/// <param nome="scalingFactor"></param>
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

 Nesta etapa, implementaremos o`getBarcodeImage`método, que gera a imagem do código de barras com base nos parâmetros fornecidos. Lidaremos com diferentes tipos de código de barras, definiremos cores, ajustaremos dimensões e muito mais. Aqui está o código para este método:

```java
/// <resumo>
/// Implementação do método GetBarCodeImage() para a interface IBarCodeGenerator.
/// </resumo>
/// <param name="parâmetros"></param>
/// <retorna></retorna>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Verifique se o tipo de código de barras e o valor são fornecidos
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
		// Manuseie outros tipos de código de barras aqui
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
	
	// Personalizar a localização do texto do código
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Ajustes adicionais para códigos QR
	final float SCALE = 2.4f; // Fator de escala empírico para converter código de barras do Word em Aspose.BarCode
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
	
	// Gerar e retornar a imagem do código de barras
	return generator.generateBarCodeImage();
}
```

## Implementando o método GetOldBarcodeImage()

 Nesta etapa, implementaremos o`getOldBarcodeImage`método, que gera imagens de código de barras para códigos de barras antigos. Aqui, lidaremos com um tipo de código de barras específico, como POSTNET. Aqui está o código para este método:

```java
/// <resumo>
/// Implementação do método GetOldBarcodeImage() para a interface IBarCodeGenerator.
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

Neste artigo, exploramos o processo de geração de etiquetas de código de barras personalizadas usando o Aspose.Words para Java. Cobrimos etapas essenciais, desde a configuração da altura do código de barras até a implementação de métodos para geração de código de barras. O Aspose.Words para Java capacita os desenvolvedores a criar etiquetas de código de barras dinâmicas e personalizadas, tornando-o uma ferramenta valiosa para vários setores.

## Perguntas frequentes

### Como posso ajustar o tamanho do código de barras gerado?

Você pode ajustar o tamanho do código de barras gerado definindo a altura do símbolo do código de barras e o fator de escala nos snippets de código fornecidos. Esses parâmetros permitem que você controle as dimensões do código de barras conforme suas necessidades.

### Posso alterar as cores do código de barras?

Sim, você pode alterar as cores do código de barras especificando as cores de primeiro plano e de fundo no código. Essa personalização permite que você combine a aparência do código de barras com o design do seu documento.

### Quais tipos de código de barras são suportados pelo Aspose.Words para Java?

O Aspose.Words para Java suporta vários tipos de código de barras, incluindo códigos QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 e mais. Você pode escolher o tipo de código de barras que atende às necessidades do seu aplicativo.

### Como faço para integrar o código de barras gerado no meu documento do Word?

Para integrar o código de barras gerado em seu documento do Word, você pode usar os recursos de manipulação de documentos do Aspose.Words for Java. Você pode inserir a imagem do código de barras em seu documento no local desejado.

### Existe algum código de exemplo disponível para personalização adicional?

 Sim, você pode encontrar trechos de código de exemplo e documentação adicional no site de referência do Aspose.Words para Java:[Aspose.Words para referência da API Java](https://reference.aspose.com/words/java/).