---
title: Advance HTML dokumentumok mentési lehetőségek Aspose.Words Java
linktitle: HTML dokumentumok mentése ezzel
second_title: Aspose.Words Java Document Processing API
description: Ebben az oktatóanyagban az Aspose.Words for Java különféle fejlett HTML-dokumentummentési lehetőségeivel foglalkozunk. Ezek a lehetőségek kiváló minőségű HTML létrehozását teszik lehetővé
type: docs
weight: 16
url: /hu/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Ebben az oktatóanyagban megvizsgáljuk az Aspose.Words for Java által biztosított speciális HTML-dokumentummentési lehetőségeket. Az Aspose.Words egy hatékony Java API Word-dokumentumokkal való munkavégzéshez, és funkciók széles skáláját kínálja a dokumentumok kezeléséhez és konvertálásához.

## 1. Bevezetés
Az Aspose.Words for Java lehetővé teszi, hogy programozottan dolgozzon Word dokumentumokkal. Ebben az oktatóanyagban a speciális HTML-dokumentummentési lehetőségekre összpontosítunk, amelyek lehetővé teszik a Word-dokumentumok HTML-formátumba való konvertálásának szabályozását.

## 2. Oda-vissza információk exportálása
A`exportRoundtripInformation` módszer lehetővé teszi a Word-dokumentumok exportálását HTML-be, miközben megőrzi az oda-vissza információk. Ez az információ akkor lehet hasznos, ha a HTML-t vissza kívánja konvertálni Word formátumba anélkül, hogy elveszítené a dokumentumspecifikus részleteket.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Betűtípusok exportálása Base64-ként
 A`exportFontsAsBase64` módszerrel a dokumentumban használt betűtípusokat Base64-kódolású adatként exportálhatja a HTML-be. Ez biztosítja, hogy a HTML-ábrázolás megőrizze ugyanazokat a betűstílusokat, mint az eredeti Word-dokumentum.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Erőforrások exportálása
A`exportResources` metódus lehetővé teszi a CSS-stíluslap típusának megadását és a betűkészlet-erőforrások exportálását. A HTML-ben erőforrásmappát és álnevet is beállíthat az erőforrásokhoz.

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

## 5. Konvertálja a metafájlokat EMF-re vagy WMF-re
A`convertMetafilesToEmfOrWmf` módszer lehetővé teszi a dokumentumban lévő metafájlok konvertálását EMF vagy WMF formátumba, ezzel biztosítva a kompatibilitást és a sima HTML-megjelenítést.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // A kódrészlet a rövidség kedvéért nem látható.
}
```

## 6. Konvertálja a metafájlokat SVG formátumba
 Használja a`convertMetafilesToSvg` módszer a metafájlok SVG formátumba konvertálására. Ez a formátum ideális vektorgrafikák megjelenítésére HTML dokumentumokban.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // A kódrészlet a rövidség kedvéért nem látható.
}
```

## 7. Adja hozzá a CSS-osztálynév előtagot
 A`addCssClassNamePrefix` módszerrel előtagot adhat a CSS-osztályok nevéhez az exportált HTML-ben. Ez segít megelőzni az ütközéseket a meglévő stílusokkal.

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

## 8. Exportáljon CID URL-eket az MHTML-erőforrásokhoz
A`exportCidUrlsForMhtmlResources` módszert használjuk dokumentumok MHTML formátumba mentésekor. Lehetővé teszi a Content ID URL-ek exportálását erőforrásokhoz.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // A kódrészlet a rövidség kedvéért nem látható.
}
```

## 9. A betűtípusnevek feloldása
A`resolveFontNames` A metódus segít a betűtípusnevek feloldásában dokumentumok HTML formátumba mentésekor, biztosítva a konzisztens megjelenítést a különböző platformokon.

```java
@Test
public void resolveFontNames() throws Exception {
    // A kódrészlet a rövidség kedvéért nem látható.
}
```

## 10. Szövegbeviteli űrlap mező exportálása szövegként
A`exportTextInputFormFieldAsText` metódus az űrlapmezőket egyszerű szövegként exportálja a HTML-be, így könnyen olvashatóvá és szerkeszthetővé teszi őket.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // A kódrészlet a rövidség kedvéért nem látható.
}
```

## 11. Következtetés
Ebben az oktatóanyagban az Aspose.Words for Java által biztosított speciális HTML-dokumentummentési lehetőségeket fedeztük fel. Ezek a beállítások lehetővé teszik az átalakítási folyamat finom vezérlését, lehetővé téve olyan HTML-dokumentumok létrehozását, amelyek nagyon hasonlítanak az eredeti Word-dokumentumokra.

## 12. GYIK
Íme néhány gyakran ismételt kérdés az Aspose.Words for Java és HTML-dokumentummentési beállításokkal kapcsolatban:

### 1. kérdés: Hogyan konvertálhatom vissza a HTML-t Word formátumba az Aspose.Words for Java használatával?
 A HTML Word formátumba való visszaállításához használhatja az Aspose.Words API-t`load` módszerrel töltheti be a HTML-dokumentumot, majd mentheti Word formátumban.

### 2. kérdés: Testreszabhatom a CSS-stílusokat HTML-be exportáláskor?
 Igen, testreszabhatja a CSS-stílusokat a HTML-ben használt stíluslapok módosításával vagy a`addCssClassNamePrefix` módszer előtag hozzáadásához a CSS-osztálynevekhez.

### 3. kérdés: Van mód a HTML-kimenet optimalizálására webes megjelenítéshez?
Igen, optimalizálhatja a HTML-kimenetet a webes megjelenítéshez az olyan opciók konfigurálásával, mint a betűtípusok Base64-ként való exportálása és a metafájlok SVG formátumba való konvertálása.

### 4. kérdés: Vannak-e korlátozások az összetett Word dokumentumok HTML formátumba konvertálásakor?
Míg az Aspose.Words for Java hatékony konverziós képességeket biztosít, a bonyolult elrendezésű Word dokumentumok további utófeldolgozást igényelhetnek a kívánt HTML-kimenet eléréséhez.
