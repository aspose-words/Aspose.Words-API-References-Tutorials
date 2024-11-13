---
title: Geavanceerde HTML-documenten opslaan opties met Aspose.Words Java
linktitle: HTML-documenten opslaan met
second_title: Aspose.Words Java Documentverwerkings-API
description: In deze tutorial hebben we verschillende geavanceerde HTML-documentopslagopties behandeld met Aspose.Words voor Java. Deze opties stellen u in staat om HTML van hoge kwaliteit te maken
type: docs
weight: 16
url: /nl/java/document-loading-and-saving/advance-html-documents-saving-options/
---

In deze tutorial verkennen we de geavanceerde HTML-documentopslagopties die Aspose.Words voor Java biedt. Aspose.Words is een krachtige Java API voor het werken met Word-documenten en biedt een breed scala aan functies voor documentmanipulatie en -conversie.

## 1. Inleiding
Met Aspose.Words voor Java kunt u programmatisch met Word-documenten werken. In deze tutorial richten we ons op geavanceerde opties voor het opslaan van HTML-documenten, waarmee u kunt bepalen hoe Word-documenten worden omgezet naar HTML.

## 2. Exporteer retourinformatie
De`exportRoundtripInformation` methode kunt u Word-documenten exporteren naar HTML terwijl roundtrip-informatie behouden blijft. Deze informatie kan handig zijn wanneer u HTML terug wilt converteren naar Word-formaat zonder dat u documentspecifieke details verliest.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Lettertypen exporteren als Base64
 Met de`exportFontsAsBase64` methode, kunt u lettertypen die in het document worden gebruikt exporteren als Base64-gecodeerde gegevens in de HTML. Dit zorgt ervoor dat de HTML-weergave dezelfde lettertypestijlen behoudt als het originele Word-document.

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
De`exportResources` Met de methode kunt u het type CSS-stijlblad opgeven en lettertypebronnen exporteren. U kunt ook een bronmap en een alias voor bronnen in de HTML instellen.

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

## 5. Metafiles converteren naar EMF of WMF
De`convertMetafilesToEmfOrWmf`Met deze methode kunt u metabestanden in het document converteren naar EMF- of WMF-indeling, waardoor compatibiliteit en soepele weergave in HTML worden gegarandeerd.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Omwille van de beknoptheid wordt het codefragment niet weergegeven.
}
```

## 6. Metafiles naar SVG converteren
 Gebruik de`convertMetafilesToSvg` methode om metafiles naar SVG-formaat te converteren. Dit formaat is ideaal voor het weergeven van vectorafbeeldingen in HTML-documenten.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Omwille van de beknoptheid wordt het codefragment niet weergegeven.
}
```

## 7. Voeg CSS-klassenaamvoorvoegsel toe
 Met de`addCssClassNamePrefix` methode, kunt u een voorvoegsel toevoegen aan CSS-klassenamen in de geëxporteerde HTML. Dit helpt conflicten met bestaande stijlen te voorkomen.

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
De`exportCidUrlsForMhtmlResources` methode wordt gebruikt bij het opslaan van documenten in MHTML-formaat. Hiermee kunnen Content-ID URL's voor bronnen worden geëxporteerd.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Omwille van de beknoptheid wordt het codefragment niet weergegeven.
}
```

## 9. Lettertypenamen oplossen
De`resolveFontNames` Met deze methode kunt u lettertypenamen omzetten bij het opslaan van documenten in HTML-formaat, waardoor een consistente weergave op verschillende platforms wordt gegarandeerd.

```java
@Test
public void resolveFontNames() throws Exception {
    // Omwille van de beknoptheid wordt het codefragment niet weergegeven.
}
```

## 10. Exporteer tekstinvoerformulierveld als tekst
De`exportTextInputFormFieldAsText` Met deze methode worden formuliervelden geëxporteerd als platte tekst in de HTML-code, waardoor ze gemakkelijk leesbaar en bewerkbaar zijn.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Omwille van de beknoptheid wordt het codefragment niet weergegeven.
}
```

## 11. Conclusie
In deze tutorial hebben we de geavanceerde HTML-documentopslagopties van Aspose.Words voor Java onderzocht. Deze opties geven u nauwkeurige controle over het conversieproces, zodat u HTML-documenten kunt maken die sterk lijken op de originele Word-documenten.

## 12. Veelgestelde vragen
Hier volgen enkele veelgestelde vragen over het werken met Aspose.Words voor Java- en HTML-documentopslagopties:

### V1: Hoe kan ik HTML terug converteren naar Word-formaat met Aspose.Words voor Java?
 Om HTML terug te converteren naar Word-formaat, kunt u de Aspose.Words API's gebruiken`load` Methode om het HTML-document te laden en vervolgens op te slaan in Word-formaat.

### V2: Kan ik de CSS-stijlen aanpassen bij het exporteren naar HTML?
 Ja, u kunt CSS-stijlen aanpassen door de stylesheets die in de HTML worden gebruikt te wijzigen of door de`addCssClassNamePrefix` Methode om een voorvoegsel toe te voegen aan CSS-klassenamen.

### V3: Is er een manier om de HTML-uitvoer te optimaliseren voor weergave op internet?
Ja, u kunt de HTML-uitvoer optimaliseren voor weergave op het web door opties te configureren zoals het exporteren van lettertypen als Base64 en het converteren van metabestanden naar SVG.

### V4: Zijn er beperkingen bij het converteren van complexe Word-documenten naar HTML?
Hoewel Aspose.Words voor Java krachtige conversiemogelijkheden biedt, hebben complexe Word-documenten met een ingewikkelde lay-out mogelijk extra nabewerking nodig om de gewenste HTML-uitvoer te verkrijgen.
