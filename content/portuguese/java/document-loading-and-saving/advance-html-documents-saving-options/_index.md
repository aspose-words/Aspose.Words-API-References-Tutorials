---
title: Opções avançadas de salvamento de documentos HTML com Aspose.Words Java
linktitle: Salvando documentos HTML com
second_title: API de processamento de documentos Java Aspose.Words
description: Neste tutorial, cobrimos várias opções avançadas de salvamento de documentos HTML com Aspose.Words para Java. Essas opções permitem que você crie HTML de alta qualidade
type: docs
weight: 16
url: /pt/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Neste tutorial, exploraremos as opções avançadas de salvamento de documentos HTML fornecidas pelo Aspose.Words para Java. O Aspose.Words é uma API Java poderosa para trabalhar com documentos do Word e oferece uma ampla gama de recursos para manipulação e conversão de documentos.

## 1. Introdução
Aspose.Words para Java permite que você trabalhe com documentos do Word programaticamente. Neste tutorial, focaremos em opções avançadas de salvamento de documentos HTML, que permitem que você controle como os documentos do Word são convertidos para HTML.

## 2. Exportar informações de ida e volta
O`exportRoundtripInformation` O método permite que você exporte documentos do Word para HTML enquanto preserva informações de ida e volta. Essas informações podem ser úteis quando você deseja converter HTML de volta para o formato Word sem perder nenhum detalhe específico do documento.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exportar fontes como Base64
 Com o`exportFontsAsBase64` método, você pode exportar fontes usadas no documento como dados codificados em Base64 no HTML. Isso garante que a representação HTML retenha os mesmos estilos de fonte do documento original do Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Exportar Recursos
O`exportResources` O método permite que você especifique o tipo de folha de estilo CSS e exporte recursos de fonte. Você também pode definir uma pasta de recursos e um alias para recursos no HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://exemplo.com/recursos");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Converta Metafiles para EMF ou WMF
O`convertMetafilesToEmfOrWmf` método permite que você converta metarquivos no documento para o formato EMF ou WMF, garantindo compatibilidade e renderização suave em HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Trecho de código não mostrado por questões de brevidade.
}
```

## 6. Converter Metafiles para SVG
 Use o`convertMetafilesToSvg` método para converter metafiles para o formato SVG. Este formato é ideal para exibir gráficos vetoriais em documentos HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Trecho de código não mostrado por questões de brevidade.
}
```

## 7. Adicionar prefixo de nome de classe CSS
 Com o`addCssClassNamePrefix` método, você pode adicionar um prefixo aos nomes de classe CSS no HTML exportado. Isso ajuda a evitar conflitos com estilos existentes.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Exportar URLs CID para recursos MHTML
O`exportCidUrlsForMhtmlResources` O método é usado ao salvar documentos no formato MHTML. Ele permite exportar URLs Content-ID para recursos.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Trecho de código não mostrado por questões de brevidade.
}
```

## 9. Resolva nomes de fontes
O`resolveFontNames` O método ajuda a resolver nomes de fontes ao salvar documentos no formato HTML, garantindo uma renderização consistente em diferentes plataformas.

```java
@Test
public void resolveFontNames() throws Exception {
    // Trecho de código não mostrado por questões de brevidade.
}
```

## 10. Exportar campo de entrada de texto como texto
O`exportTextInputFormFieldAsText` O método exporta campos de formulário como texto simples em HTML, tornando-os facilmente legíveis e editáveis.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Trecho de código não mostrado por questões de brevidade.
}
```

## 11. Conclusão
Neste tutorial, exploramos as opções avançadas de salvamento de documentos HTML fornecidas pelo Aspose.Words para Java. Essas opções dão a você controle refinado sobre o processo de conversão, permitindo que você crie documentos HTML que se assemelham muito aos documentos originais do Word.

## 12. Perguntas frequentes
Aqui estão algumas perguntas frequentes sobre como trabalhar com o Aspose.Words para opções de salvamento de documentos Java e HTML:

### P1: Como posso converter HTML de volta para o formato Word usando o Aspose.Words para Java?
 Para converter HTML de volta para o formato Word, você pode usar a API do Aspose.Words`load` método para carregar o documento HTML e salvá-lo no formato Word.

### P2: Posso personalizar os estilos CSS ao exportar para HTML?
 Sim, você pode personalizar os estilos CSS modificando as folhas de estilo usadas no HTML ou usando o`addCssClassNamePrefix` método para adicionar um prefixo aos nomes de classes CSS.

### P3: Existe uma maneira de otimizar a saída HTML para exibição na web?
Sim, você pode otimizar a saída HTML para exibição na web configurando opções como exportar fontes como Base64 e converter metarquivos para SVG.

### P4: Há alguma limitação ao converter documentos complexos do Word para HTML?
Embora o Aspose.Words para Java forneça recursos de conversão poderosos, documentos complexos do Word com layouts intrincados podem exigir pós-processamento adicional para obter a saída HTML desejada.
