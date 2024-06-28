---
title: Używanie nagłówków i stopek w Aspose.Words dla Java
linktitle: Korzystanie z nagłówków i stopek
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się krok po kroku, jak używać nagłówków i stopek w Aspose.Words dla Java. Twórz profesjonalne dokumenty bez wysiłku.
type: docs
weight: 16
url: /pl/java/using-document-elements/using-headers-and-footers/
---

W tym obszernym przewodniku przeprowadzimy Cię przez proces pracy z nagłówkami i stopkami w Aspose.Words dla Java. Nagłówki i stopki są niezbędnymi elementami w formatowaniu dokumentów, a Aspose.Words zapewnia potężne narzędzia do ich tworzenia i dostosowywania do własnych potrzeb.

Przyjrzyjmy się teraz szczegółowo każdemu z tych kroków.

## 1. Wprowadzenie do Aspose.Words

Aspose.Words to potężny interfejs API Java, który umożliwia programowe tworzenie, manipulowanie i renderowanie dokumentów programu Word. Zapewnia rozbudowane funkcje formatowania dokumentów, w tym nagłówków i stopek.

## 2. Konfigurowanie środowiska Java

 Zanim zaczniesz używać Aspose.Words, upewnij się, że masz poprawnie skonfigurowane środowisko programistyczne Java. Niezbędne instrukcje konfiguracji można znaleźć na stronie dokumentacji Aspose.Words:[Dokumentacja Java Aspose.Words](https://reference.aspose.com/words/java/).

## 3. Tworzenie nowego dokumentu

Aby pracować z nagłówkami i stopkami, musisz utworzyć nowy dokument za pomocą Aspose.Words. Poniższy kod demonstruje, jak to zrobić:

```java
// Kod Java do tworzenia nowego dokumentu
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Zrozumienie ustawień strony

 Ustawienia strony mają kluczowe znaczenie dla kontrolowania układu dokumentu. Za pomocą opcji można określić różne właściwości związane z nagłówkami i stopkami`PageSetup` klasa. Na przykład:

```java
// Konfigurowanie właściwości strony
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Inny nagłówek/stopka pierwszej strony

Aspose.Words umożliwia ustawienie różnych nagłówków i stopek na pierwszej stronie dokumentu. Używać`pageSetup.setDifferentFirstPageHeaderFooter(true);` aby włączyć tę funkcję.

## 6. Praca z nagłówkami

### 6.1. Dodawanie tekstu do nagłówków

 Możesz dodać tekst do nagłówków za pomocą`DocumentBuilder`. Oto przykład:

```java
// Dodanie tekstu do nagłówka pierwszej strony
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Wstawianie obrazów do nagłówków

 Aby wstawić obrazy do nagłówków, możesz użyć metody`insertImage` metoda. Oto przykład:

```java
// Wstawianie obrazu do nagłówka
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Dostosowywanie stylów nagłówków

Możesz dostosować style nagłówków, ustawiając różne właściwości, takie jak czcionka, wyrównanie i inne, jak pokazano w powyższych przykładach.

## 7. Praca ze stopkami

### 7.1. Dodawanie tekstu do stopek

 Podobnie jak w przypadku nagłówków, możesz dodać tekst do stopek za pomocą`DocumentBuilder`. Oto przykład:

```java
// Dodawanie tekstu do stopki głównej
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// W razie potrzeby wstaw tekst i pola
```

### 7.2. Wstawianie obrazów do stopek

 Aby wstawić obrazy do stopek, użyj opcji`insertImage` metoda, podobnie jak w nagłówkach.

### 7.3. Dostosowywanie stylów stopek

 Dostosuj style stopek za pomocą`DocumentBuilder`podobnie jak dostosowywanie nagłówków.

## 8. Numeracja stron

 Możesz umieścić numery stron w nagłówkach i stopkach, korzystając z pól takich jak`PAGE` I`NUMPAGES`. Pola te są automatycznie aktualizowane w miarę dodawania lub usuwania stron.

## 9. Informacje o prawach autorskich w stopkach

Aby dodać informacje o prawach autorskich do stopki dokumentu, możesz użyć tabeli składającej się z dwóch komórek, wyrównując jedną do lewej, a drugą do prawej, jak pokazano we fragmencie kodu.

## 10. Praca z wieloma sekcjami

Aspose.Words umożliwia pracę z wieloma sekcjami w dokumencie. Dla każdej sekcji możesz ustawić różne ustawienia strony oraz nagłówki/stopki.

## 11. Orientacja krajobrazowa

W razie potrzeby możesz zmienić orientację określonych sekcji na tryb poziomy.

## 12. Kopiowanie nagłówków/stopek z poprzednich sekcji

Kopiowanie nagłówków i stopek z poprzednich sekcji może zaoszczędzić czas podczas tworzenia złożonych dokumentów.

## 13. Zapisywanie dokumentu

Po utworzeniu i dostosowaniu dokumentu nie zapomnij zapisać go za pomocą`doc.save()` metoda.

## Kompletny kod źródłowy
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Określ, czy chcemy, aby nagłówki/stopki pierwszej strony różniły się od pozostałych stron.
        // Aby określić, możesz także użyć właściwości PageSetup.OddAndEvenPagesHeaderFooter
        // różne nagłówki/stopki dla stron nieparzystych i parzystych.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Wstaw umieszczony obraz w górnym/lewym rogu nagłówka.
        // Odległość od górnej/lewej krawędzi strony jest ustawiona na 10 punktów.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Tablicę z dwiema komórkami wykorzystujemy do utworzenia jednej części tekstu w wierszu (z numeracją stron).
        // Należy wyrównać do lewej, a drugą część tekstu (zgodnie z prawami autorskimi) wyrównać do prawej.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Używa pól PAGE i NUMPAGES do automatycznego obliczenia bieżącego numeru strony i wielu stron.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Zrób podział strony, aby utworzyć drugą stronę, na której będą widoczne główne nagłówki/stopki.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Ta sekcja nie wymaga innego nagłówka/stopki na pierwszej stronie, wystarczy jedna strona tytułowa w dokumencie,
        // nagłówek/stopka tej strony została już zdefiniowana w poprzedniej sekcji.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // W tej sekcji wyświetlane są nagłówki/stopki z poprzedniej sekcji
        // domyślnie wywołaj currentSection.HeadersFooters.LinkToPrevious(false), aby anulować tę szerokość strony
        // jest inna dla nowej sekcji i dlatego musimy ustawić inną szerokość komórek dla tabeli stopki.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Jeśli chcemy użyć już istniejącego zestawu nagłówków/stopek dla tej sekcji.
        // Jednak po niewielkich modyfikacjach celowe może być skopiowanie nagłówków/stopek
        // z poprzedniej sekcji i zastosuj niezbędne modyfikacje tam, gdzie chcemy.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Kod źródłowy metody copyHeadersFootersFromPreviousSection
```java
    /// <podsumowanie>
    /// Klonuje i kopiuje nagłówki/stopki z poprzedniej sekcji do określonej sekcji.
    /// </podsumowanie>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Wniosek

tym samouczku omówiliśmy podstawy pracy z nagłówkami i stopkami w Aspose.Words dla Java. Nauczyłeś się tworzyć, dostosowywać i stylizować nagłówki i stopki, a także znasz inne podstawowe techniki formatowania dokumentów.

 Więcej szczegółów i zaawansowanych funkcji można znaleźć w[Dokumentacja Java Aspose.Words](https://reference.aspose.com/words/java/).

## Często zadawane pytania

### 1. Jak mogę dodać numery stron do stopki mojego dokumentu?
 Możesz dodać numery stron, wstawiając`PAGE` pole w stopce za pomocą Aspose.Words.

### 2. Czy Aspose.Words jest kompatybilny ze środowiskami programistycznymi Java?
Tak, Aspose.Words zapewnia wsparcie dla programowania w języku Java. Upewnij się, że masz niezbędną konfigurację.

### 3. Czy mogę dostosować czcionkę i styl nagłówków i stopek?
Oczywiście możesz dostosować czcionki, wyrównanie i inne style, aby Twoje nagłówki i stopki były atrakcyjne wizualnie.

### 4. Czy można mieć różne nagłówki dla stron parzystych i nieparzystych?
 Tak, możesz skorzystać`PageSetup.OddAndEvenPagesHeaderFooter` aby określić różne nagłówki dla stron nieparzystych i parzystych.

### 5. Jak rozpocząć pracę z Aspose.Words dla Java?
 Na początek odwiedź[Dokumentacja Java Aspose.Words](https://reference.aspose.com/words/java/) aby uzyskać kompleksowe wskazówki dotyczące korzystania z interfejsu API.