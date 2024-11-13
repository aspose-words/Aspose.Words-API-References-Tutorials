---
title: Zaawansowane opcje zapisywania dokumentów HTML z Aspose.Words Java
linktitle: Zapisywanie dokumentów HTML za pomocą
second_title: Aspose.Words API przetwarzania dokumentów Java
description: W tym samouczku omówiliśmy różne zaawansowane opcje zapisywania dokumentów HTML za pomocą Aspose.Words dla Java. Opcje te umożliwiają tworzenie wysokiej jakości dokumentów HTML
type: docs
weight: 16
url: /pl/java/document-loading-and-saving/advance-html-documents-saving-options/
---

W tym samouczku przyjrzymy się zaawansowanym opcjom zapisywania dokumentów HTML udostępnianym przez Aspose.Words dla Java. Aspose.Words to potężne API Java do pracy z dokumentami Word, oferujące szeroki zakres funkcji do manipulacji dokumentami i konwersji.

## 1. Wprowadzenie
Aspose.Words for Java pozwala programowo pracować z dokumentami Word. W tym samouczku skupimy się na zaawansowanych opcjach zapisywania dokumentów HTML, które umożliwiają kontrolowanie sposobu konwersji dokumentów Word na HTML.

## 2. Informacje o eksporcie w obie strony
Ten`exportRoundtripInformation` Metoda ta pozwala eksportować dokumenty Word do HTML, zachowując jednocześnie informacje o obiegu zamkniętym. Informacje te mogą być przydatne, gdy chcesz przekonwertować HTML z powrotem do formatu Word bez utraty szczegółów specyficznych dla dokumentu.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Eksportuj czcionki jako Base64
 Z`exportFontsAsBase64` metodą, możesz eksportować czcionki używane w dokumencie jako dane zakodowane w Base64 w HTML. Zapewnia to, że reprezentacja HTML zachowuje te same style czcionek, co oryginalny dokument Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Eksportuj zasoby
Ten`exportResources` Metoda ta pozwala określić typ arkusza stylów CSS i eksportować zasoby czcionek. Można również ustawić folder zasobów i alias dla zasobów w HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/zasoby");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Konwertuj metapliki do formatu EMF lub WMF
Ten`convertMetafilesToEmfOrWmf`Metoda ta umożliwia konwersję metaplików w dokumencie do formatu EMF lub WMF, zapewniając zgodność i płynne renderowanie w formacie HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 6. Konwertuj metapliki do formatu SVG
 Użyj`convertMetafilesToSvg` metoda konwersji metaplików do formatu SVG. Ten format jest idealny do wyświetlania grafiki wektorowej w dokumentach HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 7. Dodaj prefiks nazwy klasy CSS
 Z`addCssClassNamePrefix` metodą, możesz dodać prefiks do nazw klas CSS w eksportowanym HTML. Pomaga to zapobiegać konfliktom z istniejącymi stylami.

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

## 8. Eksportuj adresy URL CID dla zasobów MHTML
Ten`exportCidUrlsForMhtmlResources` Metoda jest używana podczas zapisywania dokumentów w formacie MHTML. Pozwala ona na eksportowanie adresów URL Content-ID dla zasobów.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 9. Rozwiąż nazwy czcionek
Ten`resolveFontNames` Metoda ta pomaga rozpoznawać nazwy czcionek podczas zapisywania dokumentów w formacie HTML, zapewniając spójne renderowanie na różnych platformach.

```java
@Test
public void resolveFontNames() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 10. Eksportuj pole formularza wprowadzania tekstu jako tekst
Ten`exportTextInputFormFieldAsText` Metoda eksportuje pola formularza jako zwykły tekst w formacie HTML, dzięki czemu można je łatwo odczytać i edytować.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 11. Wnioski
tym samouczku przyjrzeliśmy się zaawansowanym opcjom zapisywania dokumentów HTML udostępnianym przez Aspose.Words dla Java. Opcje te dają Ci szczegółową kontrolę nad procesem konwersji, umożliwiając tworzenie dokumentów HTML, które ściśle przypominają oryginalne dokumenty Word.

## 12. Najczęściej zadawane pytania
Poniżej znajdują się najczęściej zadawane pytania dotyczące pracy z opcjami zapisywania dokumentów Java i HTML w Aspose.Words:

### P1: W jaki sposób mogę przekonwertować HTML z powrotem do formatu Word za pomocą Aspose.Words dla Java?
 Aby przekonwertować HTML z powrotem do formatu Word, możesz skorzystać z interfejsu API Aspose.Words`load` metoda ładowania dokumentu HTML i zapisywania go w formacie Word.

### P2: Czy mogę dostosować style CSS podczas eksportowania do HTML?
 Tak, możesz dostosować style CSS, modyfikując arkusze stylów używane w kodzie HTML lub korzystając z`addCssClassNamePrefix` metoda dodawania prefiksu do nazw klas CSS.

### P3: Czy istnieje sposób na optymalizację wyjścia HTML do wyświetlania w sieci?
Tak, możesz zoptymalizować wyjście HTML do wyświetlania w Internecie, konfigurując opcje takie jak eksportowanie czcionek jako Base64 i konwersja metaplików do SVG.

### P4: Czy istnieją jakieś ograniczenia przy konwersji złożonych dokumentów Word do formatu HTML?
Chociaż Aspose.Words for Java oferuje zaawansowane możliwości konwersji, złożone dokumenty Word ze skomplikowanymi układami mogą wymagać dodatkowego przetwarzania końcowego w celu uzyskania pożądanego wyniku HTML.
