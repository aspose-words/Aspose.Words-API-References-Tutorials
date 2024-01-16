---
title: Usando propriedades do documento em Aspose.Words para Java
linktitle: Usando propriedades do documento
second_title: API de processamento de documentos Java Aspose.Words
description: Otimize o gerenciamento de documentos com Aspose.Words for Java. Aprenda a trabalhar com propriedades de documentos, adicionar metadados personalizados e muito mais neste tutorial abrangente.
type: docs
weight: 32
url: /pt/java/document-manipulation/using-document-properties/
---

## Introdução às propriedades do documento

As propriedades do documento são uma parte vital de qualquer documento. Eles fornecem informações adicionais sobre o próprio documento, como título, autor, assunto, palavras-chave e muito mais. No Aspose.Words for Java, você pode manipular propriedades integradas e personalizadas do documento.

## Enumerando propriedades do documento

### Propriedades integradas

Para recuperar e trabalhar com propriedades integradas do documento, você pode usar o seguinte trecho de código:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Este código exibirá o nome do documento e as propriedades integradas, incluindo propriedades como “Título”, “Autor” e “Palavras-chave”.

### Propriedades personalizadas

Para trabalhar com propriedades personalizadas do documento, você pode usar o seguinte trecho de código:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Este trecho de código demonstra como adicionar propriedades personalizadas ao documento, incluindo um valor booleano, uma string, uma data, um número de revisão e um valor numérico.

## Removendo propriedades do documento

Para remover propriedades específicas do documento, você pode usar o seguinte código:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Este código remove a propriedade customizada "Data Autorizada" do documento.

## Configurando link para conteúdo

Em alguns casos, você pode querer criar links no seu documento. Veja como você pode fazer isso:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Adicione vinculado à propriedade de conteúdo.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Este trecho de código demonstra como criar um marcador em seu documento e adicionar uma propriedade de documento personalizada vinculada a esse marcador.

## Convertendo entre unidades de medida

No Aspose.Words for Java, você pode converter unidades de medida facilmente. Aqui está um exemplo de como fazer isso:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Defina as margens em polegadas.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Este trecho de código define várias margens e distâncias em polegadas, convertendo-as em pontos.

## Usando caracteres de controle

Os caracteres de controle podem ser úteis ao lidar com texto. Veja como substituir um caractere de controle em seu texto:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Substitua o caractere de controle "\r" por "\r\n".
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

Neste exemplo, substituímos o retorno de carro (`\r`) com um retorno de carro seguido por um avanço de linha (`\r\n`).

## Conclusão

As propriedades do documento desempenham um papel significativo no gerenciamento e organização eficaz de seus documentos no Aspose.Words for Java. Seja trabalhando com propriedades integradas, propriedades personalizadas ou usando caracteres de controle, você tem uma variedade de ferramentas à sua disposição para aprimorar seus recursos de gerenciamento de documentos.

## Perguntas frequentes

### Como acesso as propriedades internas do documento?

 Para acessar as propriedades integradas do documento no Aspose.Words for Java, você pode usar o`getBuiltInDocumentProperties` método no`Document` objeto. Este método retorna uma coleção de propriedades integradas pelas quais você pode iterar.

### Posso adicionar propriedades personalizadas de documento a um documento?

 Sim, você pode adicionar propriedades personalizadas de documento a um documento usando o`CustomDocumentProperties` coleção. Você pode definir propriedades customizadas com vários tipos de dados, incluindo strings, booleanos, datas e valores numéricos.

### Como posso remover uma propriedade específica de documento personalizado?

 Para remover uma propriedade de documento personalizada específica, você pode usar o comando`remove` método no`CustomDocumentProperties`coleção, passando como parâmetro o nome da propriedade que deseja remover.

### Qual é o propósito de vincular ao conteúdo de um documento?

Vincular ao conteúdo de um documento permite criar referências dinâmicas a partes específicas do documento. Isto pode ser útil para criar documentos interativos ou referências cruzadas entre seções.

### Como posso converter entre diferentes unidades de medida em Aspose.Words for Java?

 Você pode converter entre diferentes unidades de medida em Aspose.Words for Java usando o`ConvertUtil` aula. Ele fornece métodos para converter unidades como polegadas em pontos, pontos em centímetros e muito mais.