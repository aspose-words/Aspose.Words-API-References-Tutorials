---
title: Geavanceerde HTML-documenten Opslaan van opties met Aspose.Words Java
linktitle: HTML-documenten opslaan met
second_title: Aspose.Words Java-documentverwerkings-API
description: In deze zelfstudie hebben we verschillende geavanceerde opties voor het opslaan van HTML-documenten besproken met Aspose.Words voor Java. Met deze opties kunt u HTML van hoge kwaliteit maken
type: docs
weight: 16
url: /nl/java/document-loading-and-saving/advance-html-documents-saving-options/
---

In deze zelfstudie verkennen we de geavanceerde opties voor het opslaan van HTML-documenten die Aspose.Words voor Java biedt. Aspose.Words is een krachtige Java API voor het werken met Word-documenten en biedt een breed scala aan functies voor documentmanipulatie en -conversie.

## 1. Inleiding
Met Aspose.Words voor Java kunt u programmatisch met Word-documenten werken. In deze zelfstudie concentreren we ons op geavanceerde opties voor het opslaan van HTML-documenten, waarmee u kunt bepalen hoe Word-documenten naar HTML worden geconverteerd.

## 2. Retourinformatie exporteren
 De`exportRoundtripInformation` Met deze methode kunt u Word-documenten naar HTML exporteren terwijl de retourinformatie behouden blijft. Deze informatie kan handig zijn als u HTML terug naar Word-indeling wilt converteren zonder dat documentspecifieke details verloren gaan.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exporteer lettertypen als Base64
 Met de`exportFontsAsBase64` Met deze methode kunt u de in het document gebruikte lettertypen exporteren als Base64-gecodeerde gegevens in de HTML. Dit zorgt ervoor dat de HTML-weergave dezelfde lettertypestijlen behoudt als het originele Word-document.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Hulpbronnen exporteren
 De`exportResources` Met de methode kunt u het type CSS-stylesheet opgeven en lettertypebronnen exporteren. U kunt ook een bronmap en een alias voor bronnen in de HTML instellen.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://voorbeeld.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Converteer metabestanden naar EMF of WMF
 De`convertMetafilesToEmfOrWmf`Met de methode kunt u metabestanden in het document converteren naar EMF- of WMF-indeling, waardoor compatibiliteit en een soepele weergave in HTML worden gegarandeerd.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Codefragment niet weergegeven vanwege beknoptheid.
}
```

## 6. Converteer metabestanden naar SVG
 Gebruik de`convertMetafilesToSvg` methode om metabestanden naar SVG-formaat te converteren. Dit formaat is ideaal voor het weergeven van vectorafbeeldingen in HTML-documenten.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Codefragment niet weergegeven vanwege beknoptheid.
}
```

## 7. Voeg het CSS-klassenaamvoorvoegsel toe
 Met de`addCssClassNamePrefix` methode kunt u een voorvoegsel toevoegen aan CSS-klassenamen in de geëxporteerde HTML. Dit helpt conflicten met bestaande stijlen te voorkomen.

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

## 8. Exporteer CID-URL's voor MHTML-bronnen
 De`exportCidUrlsForMhtmlResources` methode wordt gebruikt bij het opslaan van documenten in MHTML-indeling. Hiermee kunt u Content-ID-URL's voor bronnen exporteren.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Codefragment niet weergegeven vanwege beknoptheid.
}
```

## 9. Lettertypenamen oplossen
 De`resolveFontNames` -methode helpt bij het oplossen van lettertypenamen bij het opslaan van documenten in HTML-indeling, waardoor een consistente weergave op verschillende platforms wordt gegarandeerd.

```java
@Test
public void resolveFontNames() throws Exception {
    // Codefragment niet weergegeven vanwege beknoptheid.
}
```

## 10. Exporteer het tekstinvoerformulierveld als tekst
 De`exportTextInputFormFieldAsText` methode exporteert formuliervelden als platte tekst in HTML, waardoor ze gemakkelijk leesbaar en bewerkbaar worden.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Codefragment niet weergegeven vanwege beknoptheid.
}
```

## 11. Conclusie
In deze zelfstudie hebben we de geavanceerde opties voor het opslaan van HTML-documenten onderzocht die Aspose.Words voor Java biedt. Deze opties geven u nauwkeurige controle over het conversieproces, waardoor u HTML-documenten kunt maken die sterk lijken op de originele Word-documenten.

## 12. Veelgestelde vragen
Hier vindt u enkele veelgestelde vragen over het werken met Aspose.Words voor opties voor het opslaan van Java- en HTML-documenten:

### V1: Hoe kan ik HTML terug naar Word-formaat converteren met Aspose.Words voor Java?
 Om HTML terug naar Word-formaat te converteren, kunt u de Aspose.Words API's gebruiken`load` methode om het HTML-document te laden en vervolgens op te slaan in Word-formaat.

### Vraag 2: Kan ik de CSS-stijlen aanpassen bij het exporteren naar HTML?
 Ja, u kunt CSS-stijlen aanpassen door de stylesheets die in de HTML worden gebruikt te wijzigen of door de`addCssClassNamePrefix` methode om een voorvoegsel toe te voegen aan CSS-klassenamen.

### Vraag 3: Is er een manier om de HTML-uitvoer voor webweergave te optimaliseren?
Ja, u kunt de HTML-uitvoer voor webweergave optimaliseren door opties te configureren zoals het exporteren van lettertypen als Base64 en het converteren van metabestanden naar SVG.

### Vraag 4: Zijn er beperkingen bij het converteren van complexe Word-documenten naar HTML?
Hoewel Aspose.Words voor Java krachtige conversiemogelijkheden biedt, kunnen complexe Word-documenten met ingewikkelde lay-outs extra nabewerking vereisen om de gewenste HTML-uitvoer te verkrijgen.
