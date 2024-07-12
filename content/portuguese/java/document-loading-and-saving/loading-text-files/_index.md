---
title: Carregando arquivos de texto com Aspose.Words para Java
linktitle: Carregando arquivos de texto com
second_title: API de processamento de documentos Java Aspose.Words
description: Desbloqueie o poder do Aspose.Words para Java. Aprenda a carregar documentos de texto, gerenciar listas, manipular espaços e controlar a direção do texto.
type: docs
weight: 13
url: /pt/java/document-loading-and-saving/loading-text-files/
---

## Introdução ao carregamento de arquivos de texto com Aspose.Words para Java

Neste guia, exploraremos como carregar arquivos de texto usando Aspose.Words for Java e manipulá-los como documentos do Word. Abordaremos vários aspectos, como detecção de listas, manipulação de espaços e controle da direção do texto.

## Etapa 1: detectando listas

Para carregar um documento de texto e detectar listas, você pode seguir estas etapas:

```java
// Crie um documento de texto simples na forma de uma string com partes que podem ser interpretadas como listas.
// Ao carregar, as três primeiras listas serão sempre detectadas pelo Aspose.Words,
// e os objetos List serão criados para eles após o carregamento.
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
// quarta lista, com espaços em branco entre o número da lista e o conteúdo do item da lista,
// só será detectado como uma lista se "DetectNumberingWithWhitespaces" em um objeto LoadOptions estiver definido como verdadeiro,
// para evitar que parágrafos que começam com números sejam erroneamente detectados como listas.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// Carregue o documento aplicando LoadOptions como parâmetro e verifique o resultado.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Este código demonstra como carregar um documento de texto com vários formatos de lista e usar o`DetectNumberingWithWhitespaces` opção para detectar listas corretamente.

## Etapa 2: Tratamento de opções de espaços

Para controlar os espaços iniciais e finais ao carregar um documento de texto, você pode usar o seguinte código:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 Neste exemplo, carregamos um documento de texto e cortamos os espaços iniciais e finais usando`TxtLeadingSpacesOptions.TRIM`e`TxtTrailingSpacesOptions.TRIM`.

## Etapa 3: Controlando a direção do texto

Para especificar a direção do texto ao carregar um documento de texto, você pode usar o seguinte código:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

Este código define a direção do documento para detecção automática (`DocumentDirection.AUTO`e carrega um documento de texto com texto em hebraico. Você pode ajustar a direção do documento conforme necessário.

## Código-fonte completo para carregar arquivos de texto com Aspose.Words para Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Crie um documento de texto simples na forma de uma string com partes que podem ser interpretadas como listas.
	// Ao carregar, as três primeiras listas serão sempre detectadas pelo Aspose.Words,
	// e os objetos List serão criados para eles após o carregamento.
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// A quarta lista, com espaços em branco entre o número da lista e o conteúdo do item da lista,
	// só será detectado como uma lista se "DetectNumberingWithWhitespaces" em um objeto LoadOptions estiver definido como verdadeiro,
	// para evitar que parágrafos que começam com números sejam erroneamente detectados como listas.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// Carregue o documento aplicando LoadOptions como parâmetro e verifique o resultado.
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## Conclusão

Neste guia, exploramos como carregar arquivos de texto usando Aspose.Words para Java, detectar listas, manipular espaços e controlar a direção do texto. Essas técnicas permitem manipular documentos de texto de maneira eficaz em seus aplicativos Java.

## Perguntas frequentes

### O que é Aspose.Words para Java?

Aspose.Words for Java é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, manipular e converter documentos do Word programaticamente em aplicativos Java. Ele fornece uma ampla gama de recursos para trabalhar com texto, tabelas, imagens e outros elementos de documentos.

### Como posso começar a usar Aspose.Words para Java?

Para começar a usar Aspose.Words para Java, siga estas etapas:
1. Baixe e instale a biblioteca Aspose.Words para Java.
2.  Consulte a documentação em[Referência da API Aspose.Words para Java](https://reference.aspose.com/words/java/)para obter informações detalhadas e exemplos.
3. Explore o código de exemplo e os tutoriais para aprender como usar a biblioteca de maneira eficaz.

### Como carrego um documento de texto usando Aspose.Words for Java?

 Para carregar um documento de texto usando Aspose.Words for Java, você pode usar o`TxtLoadOptions` classe e o`Document` aula. Certifique-se de especificar as opções apropriadas para lidar com espaços e direção do texto conforme necessário. Consulte o guia passo a passo neste artigo para obter um exemplo detalhado.

### Posso converter um documento de texto carregado para outros formatos?

 Sim, Aspose.Words for Java permite converter um documento de texto carregado em vários formatos, incluindo DOCX, PDF e muito mais. Você pode usar o`Document` classe para realizar conversões. Verifique a documentação para exemplos de conversão específicos.

### Como lidar com espaços em documentos de texto carregados?

 Você pode controlar como os espaços iniciais e finais são tratados em documentos de texto carregados usando`TxtLoadOptions` . Opções como`TxtLeadingSpacesOptions`e`TxtTrailingSpacesOptions`permitem que você corte ou preserve espaços conforme necessário. Consulte a seção "Opções de tratamento de espaços" neste guia para obter um exemplo.

### Qual é o significado da direção do texto em Aspose.Words for Java?

A direção do texto é essencial para documentos que contenham escritas ou idiomas mistos, como hebraico ou árabe. Aspose.Words for Java oferece opções para especificar a direção do texto, garantindo renderização e formatação adequadas do texto nessas linguagens. A seção "Controlando a direção do texto" neste guia demonstra como definir a direção do texto.

### Onde posso encontrar mais recursos e suporte para Aspose.Words for Java?

 Para recursos adicionais, documentação e suporte, visite o[Documentação Aspose.Words para Java](https://reference.aspose.com/words/java/). Você também pode participar dos fóruns da comunidade Aspose.Words ou entrar em contato com o suporte do Aspose para obter assistência com questões ou dúvidas específicas.

### O Aspose.Words for Java é adequado para projetos comerciais?

Sim, Aspose.Words for Java é adequado para projetos pessoais e comerciais. Oferece opções de licenciamento para acomodar vários cenários de uso. Certifique-se de revisar os termos de licenciamento e preços no site Aspose para escolher a licença apropriada para o seu projeto.