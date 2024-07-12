---
title: Pokročilé možnosti ukládání dokumentů HTML pomocí Aspose.Words Java
linktitle: Ukládání HTML dokumentů pomocí
second_title: Aspose.Words Java Document Processing API
description: V tomto tutoriálu jsme se zabývali různými pokročilými možnostmi ukládání dokumentů HTML pomocí Aspose.Words pro Java. Tyto možnosti vám umožňují vytvářet vysoce kvalitní HTML
type: docs
weight: 16
url: /cs/java/document-loading-and-saving/advance-html-documents-saving-options/
---

V tomto tutoriálu prozkoumáme pokročilé možnosti ukládání dokumentů HTML, které poskytuje Aspose.Words pro Java. Aspose.Words je výkonné Java API pro práci s dokumenty Wordu a nabízí širokou škálu funkcí pro manipulaci s dokumenty a jejich převod.

## 1. Úvod
Aspose.Words for Java vám umožňuje pracovat s dokumenty Wordu programově. V tomto tutoriálu se zaměříme na pokročilé možnosti ukládání dokumentů HTML, které vám umožňují řídit, jak se dokumenty aplikace Word převádějí do HTML.

## 2. Exportujte informace o zpáteční cestě
 The`exportRoundtripInformation` umožňuje exportovat dokumenty Wordu do HTML při zachování zpátečních informací. Tyto informace mohou být užitečné, když chcete převést HTML zpět do formátu Word bez ztráty jakýchkoli podrobností specifických pro dokument.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exportujte písma jako Base64
 s`exportFontsAsBase64` můžete exportovat fonty použité v dokumentu jako data kódovaná Base64 do HTML. Tím je zajištěno, že reprezentace HTML zachová stejné styly písem jako původní dokument aplikace Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Export zdrojů
 The`exportResources` umožňuje určit typ šablony stylů CSS a exportovat zdroje písem. Můžete také nastavit složku prostředků a alias pro prostředky v HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Převeďte metasoubory na EMF nebo WMF
 The`convertMetafilesToEmfOrWmf`metoda umožňuje převést metasoubory v dokumentu buď do formátu EMF nebo WMF, což zajišťuje kompatibilitu a plynulé vykreslování v HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Fragment kódu se pro stručnost nezobrazuje.
}
```

## 6. Převeďte metasoubory na SVG
 Použijte`convertMetafilesToSvg` metoda pro převod metasouborů do formátu SVG. Tento formát je ideální pro zobrazování vektorové grafiky v dokumentech HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Fragment kódu se pro stručnost nezobrazuje.
}
```

## 7. Přidejte předponu názvu třídy CSS
 s`addCssClassNamePrefix` můžete přidat předponu k názvům tříd CSS v exportovaném HTML. To pomáhá předcházet konfliktům s existujícími styly.

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

## 8. Exportujte adresy URL CID pro zdroje MHTML
 The`exportCidUrlsForMhtmlResources` metoda se používá při ukládání dokumentů ve formátu MHTML. Umožňuje exportovat adresy URL Content-ID pro zdroje.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Fragment kódu se pro stručnost nezobrazuje.
}
```

## 9. Vyřešte názvy písem
 The`resolveFontNames` Tato metoda pomáhá vyřešit názvy písem při ukládání dokumentů ve formátu HTML a zajišťuje konzistentní vykreslování na různých platformách.

```java
@Test
public void resolveFontNames() throws Exception {
    // Fragment kódu se pro stručnost nezobrazuje.
}
```

## 10. Export textového vstupního pole formuláře jako text
 The`exportTextInputFormFieldAsText` metoda exportuje pole formuláře jako prostý text v HTML, takže je snadno čitelná a upravitelná.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Fragment kódu se pro stručnost nezobrazuje.
}
```

## 11. Závěr
tomto tutoriálu jsme prozkoumali pokročilé možnosti ukládání dokumentů HTML, které poskytuje Aspose.Words pro Java. Tyto možnosti vám poskytují jemnou kontrolu nad procesem převodu a umožňují vám vytvářet dokumenty HTML, které se velmi podobají původním dokumentům aplikace Word.

## 12. Nejčastější dotazy
Zde jsou některé často kladené otázky o práci s Aspose.Words pro Java a možnosti uložení dokumentu HTML:

### Q1: Jak mohu převést HTML zpět do formátu Word pomocí Aspose.Words for Java?
 Chcete-li převést HTML zpět do formátu Word, můžete použít rozhraní API Aspose.Words`load` způsob načtení dokumentu HTML a jeho uložení ve formátu Word.

### Q2: Mohu přizpůsobit styly CSS při exportu do HTML?
 Ano, styly CSS můžete přizpůsobit úpravou šablon stylů používaných v HTML nebo pomocí`addCssClassNamePrefix` metoda pro přidání předpony k názvům tříd CSS.

### Q3: Existuje způsob, jak optimalizovat výstup HTML pro zobrazení na webu?
Ano, výstup HTML můžete optimalizovat pro webové zobrazení konfigurací možností, jako je export písem jako Base64 a převod metasouborů do SVG.

### Q4: Existují nějaká omezení při převodu složitých dokumentů aplikace Word do HTML?
Zatímco Aspose.Words for Java poskytuje výkonné konverzní možnosti, složité dokumenty Wordu se složitým rozvržením mohou vyžadovat dodatečné následné zpracování k dosažení požadovaného výstupu HTML.
