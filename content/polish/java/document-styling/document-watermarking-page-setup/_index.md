---
title: Znak wodny dokumentu i konfiguracja strony
linktitle: Znak wodny dokumentu i konfiguracja strony
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak stosować znaki wodne i konfigurować konfiguracje strony za pomocą Aspose.Words dla Java. Obszerny przewodnik z kodem źródłowym.
type: docs
weight: 13
url: /pl/java/document-styling/document-watermarking-page-setup/
---
## Wstęp

W dziedzinie manipulacji dokumentami Aspose.Words dla Java jest potężnym narzędziem, pozwalającym programistom sprawować kontrolę nad każdym aspektem przetwarzania dokumentów. W tym obszernym przewodniku zagłębimy się w zawiłości związane ze znakami wodnymi dokumentów i konfiguracją strony za pomocą Aspose.Words dla Java. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero wkraczasz w świat przetwarzania dokumentów w języku Java, ten przewodnik krok po kroku zapewni Ci potrzebną wiedzę i kod źródłowy.

## Znak wodny dokumentu

### Dodawanie znaków wodnych

Dodawanie znaków wodnych do dokumentów może mieć kluczowe znaczenie dla budowania marki lub zabezpieczania treści. Aspose.Words for Java sprawia, że to zadanie jest proste. Oto jak:

```java
// Załaduj dokument
Document doc = new Document("document.docx");

// Utwórz znak wodny
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// Ustaw znak wodny
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// Wstaw znak wodny
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Zapisz dokument
doc.save("document_with_watermark.docx");
```

### Dostosowywanie znaków wodnych

Możesz dodatkowo dostosować znaki wodne, dostosowując czcionkę, rozmiar, kolor i obrót. Dzięki tej elastyczności znak wodny będzie idealnie dopasowany do stylu dokumentu.

## Ustawienia strony

### Rozmiar strony i orientacja

Konfiguracja strony ma kluczowe znaczenie w formatowaniu dokumentu. Aspose.Words dla Java oferuje pełną kontrolę nad rozmiarem i orientacją strony:

```java
// Załaduj dokument
Document doc = new Document("document.docx");

// Ustaw rozmiar strony na A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// Zmień orientację strony na poziomą
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// Zapisz zmodyfikowany dokument
doc.save("formatted_document.docx");
```

### Marginesy i numeracja stron

Precyzyjna kontrola marginesów i numeracji stron jest niezbędna w przypadku profesjonalnych dokumentów. Osiągnij to dzięki Aspose.Words dla Java:

```java
// Załaduj dokument
Document doc = new Document("document.docx");

// Ustaw marginesy
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// Włącz numerację stron
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// Zapisz sformatowany dokument
doc.save("formatted_document.docx");
```

## Często zadawane pytania

### Jak usunąć znak wodny z dokumentu?

Aby usunąć znak wodny z dokumentu, możesz przeglądać kształty dokumentu i usuwać te reprezentujące znaki wodne. Oto fragment:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### Czy mogę dodać wiele znaków wodnych do jednego dokumentu?

Tak, możesz dodać wiele znaków wodnych do dokumentu, tworząc dodatkowe obiekty Shape i umieszczając je według potrzeb.

### Jak zmienić rozmiar strony na legalny w orientacji poziomej?

Aby ustawić legalny rozmiar strony w orientacji poziomej, zmodyfikuj szerokość i wysokość strony w następujący sposób:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### Jaka jest domyślna czcionka znaków wodnych?

Domyślną czcionką znaków wodnych jest Calibri o rozmiarze czcionki 36.

### Jak dodać numery stron zaczynając od konkretnej strony?

Można to osiągnąć ustawiając numer strony początkowej w dokumencie w następujący sposób:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### Jak wyśrodkować tekst w nagłówku lub stopce?

Tekst w nagłówku lub stopce można wyśrodkować, korzystając z metody setAlignment na obiekcie Akapit w nagłówku lub stopce.

## Wniosek

tym obszernym przewodniku zgłębiliśmy sztukę znakowania wodnego dokumentów i konfigurowania strony za pomocą Aspose.Words dla Java. Uzbrojeni w dostarczone fragmenty kodu źródłowego i spostrzeżenia, posiadasz teraz narzędzia do finezyjnego manipulowania i formatowania dokumentów. Aspose.Words for Java umożliwia tworzenie profesjonalnych, markowych dokumentów dostosowanych do Twoich dokładnych specyfikacji.

Opanowanie manipulacji dokumentami to cenna umiejętność dla programistów, a Aspose.Words for Java jest Twoim zaufanym towarzyszem w tej podróży. Zacznij tworzyć wspaniałe dokumenty już dziś!