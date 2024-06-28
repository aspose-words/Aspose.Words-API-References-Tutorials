---
title: Zaawansowane opcje zapisywania dokumentów HTML w Aspose.Words Java
linktitle: Zapisywanie dokumentów HTML za pomocą
second_title: Aspose.Words API przetwarzania dokumentów Java
description: W tym samouczku omówiliśmy różne zaawansowane opcje zapisywania dokumentów HTML za pomocą Aspose.Words dla Java. Opcje te umożliwiają tworzenie wysokiej jakości kodu HTML.
type: docs
weight: 16
url: /pl/java/document-loading-and-saving/advance-html-documents-saving-options/
---

W tym samouczku omówimy zaawansowane opcje zapisywania dokumentów HTML udostępniane przez Aspose.Words dla Java. Aspose.Words to potężny interfejs API Java do pracy z dokumentami programu Word, oferujący szeroką gamę funkcji do manipulacji i konwersji dokumentów.

## 1. Wstęp
Aspose.Words for Java umożliwia programową pracę z dokumentami programu Word. W tym samouczku skupimy się na zaawansowanych opcjach zapisywania dokumentów HTML, które pozwalają kontrolować sposób konwersji dokumentów Worda do formatu HTML.

## 2. Eksportuj informacje o podróży w obie strony
 The`exportRoundtripInformation` Metoda umożliwia eksportowanie dokumentów programu Word do formatu HTML przy jednoczesnym zachowaniu informacji o podróży w obie strony. Informacje te mogą być przydatne, gdy chcesz przekonwertować HTML z powrotem do formatu Word bez utraty szczegółów specyficznych dla dokumentu.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Eksportuj czcionki jako Base64
 Z`exportFontsAsBase64` metodą można wyeksportować czcionki użyte w dokumencie jako dane zakodowane w formacie Base64 w formacie HTML. Dzięki temu w reprezentacji HTML zachowane zostaną te same style czcionek, co w oryginalnym dokumencie programu Word.

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
 The`exportResources` Metoda pozwala określić typ arkusza stylów CSS i wyeksportować zasoby czcionek. Możesz także ustawić folder zasobów i alias zasobów w kodzie HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://przykład.com/zasoby");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Konwertuj metapliki na EMF lub WMF
 The`convertMetafilesToEmfOrWmf`Metoda umożliwia konwersję metaplików w dokumencie do formatu EMF lub WMF, zapewniając zgodność i płynne renderowanie w formacie HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 6. Konwertuj metapliki na SVG
 Użyj`convertMetafilesToSvg` metoda konwersji metaplików do formatu SVG. Ten format jest idealny do wyświetlania grafiki wektorowej w dokumentach HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 7. Dodaj przedrostek nazwy klasy CSS
 Z`addCssClassNamePrefix` metodę, możesz dodać przedrostek do nazw klas CSS w wyeksportowanym kodzie HTML. Pomaga to zapobiegać konfliktom z istniejącymi stylami.

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
 The`exportCidUrlsForMhtmlResources` metoda stosowana jest przy zapisywaniu dokumentów w formacie MHTML. Umożliwia eksportowanie adresów URL Content-ID dla zasobów.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 9. Rozwiąż nazwy czcionek
 The`resolveFontNames` Metoda pomaga rozpoznawać nazwy czcionek podczas zapisywania dokumentów w formacie HTML, zapewniając spójne renderowanie na różnych platformach.

```java
@Test
public void resolveFontNames() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 10. Eksportuj pole formularza wprowadzania tekstu jako tekst
 The`exportTextInputFormFieldAsText` Metoda eksportuje pola formularzy jako zwykły tekst w formacie HTML, dzięki czemu są one łatwe do odczytania i edytowania.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Fragment kodu nie został pokazany ze względu na zwięzłość.
}
```

## 11. Wniosek
tym samouczku zbadaliśmy zaawansowane opcje zapisywania dokumentów HTML udostępniane przez Aspose.Words dla Java. Opcje te zapewniają szczegółową kontrolę nad procesem konwersji, umożliwiając tworzenie dokumentów HTML bardzo przypominających oryginalne dokumenty programu Word.

## 12.FAQ
Oto kilka często zadawanych pytań na temat pracy z Aspose.Words dla opcji zapisywania dokumentów Java i HTML:

### P1: Jak mogę przekonwertować HTML z powrotem do formatu Word przy użyciu Aspose.Words dla Java?
 Aby przekonwertować HTML z powrotem do formatu Word, możesz użyć interfejsu API Aspose.Words`load` metoda ładowania dokumentu HTML, a następnie zapisywania go w formacie Word.

### P2: Czy mogę dostosować style CSS podczas eksportowania do formatu HTML?
 Tak, możesz dostosować style CSS, modyfikując arkusze stylów używane w kodzie HTML lub używając`addCssClassNamePrefix` metoda dodawania przedrostka do nazw klas CSS.

### P3: Czy istnieje sposób na optymalizację kodu wyjściowego HTML do wyświetlania w Internecie?
Tak, możesz zoptymalizować dane wyjściowe HTML do wyświetlania w Internecie, konfigurując opcje, takie jak eksportowanie czcionek w formacie Base64 i konwersja metaplików do formatu SVG.

### P4: Czy istnieją jakieś ograniczenia podczas konwertowania złożonych dokumentów programu Word do formatu HTML?
Chociaż Aspose.Words for Java zapewnia potężne możliwości konwersji, złożone dokumenty Word ze skomplikowanymi układami mogą wymagać dodatkowego przetwarzania końcowego, aby osiągnąć pożądany wynik HTML.
