---
title: Generowanie spisu treści w Aspose.Words dla Java
linktitle: Generowanie spisu treści
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak wygenerować i dostosować spis treści (TOC) przy użyciu Aspose.Words dla Java. Twórz zorganizowane i profesjonalne dokumenty bez wysiłku.
type: docs
weight: 21
url: /pl/java/document-manipulation/generating-table-of-contents/
---

## Wprowadzenie do generowania spisu treści w Aspose.Words dla Java

W tym samouczku przeprowadzimy Cię przez proces generowania spisu treści (TOC) przy użyciu Aspose.Words dla Java. Spis treści jest kluczową funkcją tworzenia uporządkowanych dokumentów. Omówimy, jak dostosować wygląd i układ spisu treści.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for Java w swoim projekcie Java.

## Krok 1: Utwórz nowy dokument

Najpierw utwórzmy nowy dokument do pracy.

```java
Document doc = new Document();
```

## Krok 2: Dostosuj style spisu treści

Aby dostosować wygląd spisu treści, możesz modyfikować powiązane z nim style. W tym przykładzie pogrubimy wpisy spisu treści pierwszego poziomu.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Krok 3: Dodaj treść do swojego dokumentu

Możesz dodać swoją treść do dokumentu. Ta treść zostanie wykorzystana do wygenerowania spisu treści.

## Krok 4: Wygeneruj spis treści

Aby wygenerować spis treści, wstaw pole spisu treści w żądanym miejscu w dokumencie. To pole zostanie automatycznie wypełnione na podstawie nagłówków i stylów w dokumencie.

```java
// Wstaw pole spisu treści w żądanym miejscu w dokumencie.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Krok 5: Zapisz dokument

Na koniec zapisz dokument ze spisem treści.

```java
doc.save("your_output_path_here");
```

## Dostosowywanie tabulatorów w spisie treści

Możesz także dostosować tabulatory w spisie treści, aby kontrolować układ numerów stron. Oto jak zmienić tabulatory:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Uzyskaj pierwszą zakładkę używaną w tym akapicie, która wyrównuje numery stron.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Usuń starą zakładkę.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Wstaw nową zakładkę w zmodyfikowanej pozycji (np. 50 jednostek w lewo).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Teraz masz dostosowany spis treści w swoim dokumencie z dostosowanymi tabulatorami w celu wyrównania numerów stron.


## Wniosek

W tym samouczku omówiliśmy, jak wygenerować spis treści (TOC) przy użyciu Aspose.Words dla języka Java, potężnej biblioteki do pracy z dokumentami programu Word. Dobrze zorganizowany spis treści jest niezbędny do organizowania długich dokumentów i poruszania się po nich, a Aspose.Words zapewnia narzędzia do łatwego tworzenia i dostosowywania spisów treści.

## Często zadawane pytania

### Jak zmienić formatowanie wpisów spisu treści?

 Możesz modyfikować style powiązane z poziomami spisu treści za pomocą`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, gdzie X to poziom spisu treści.

### Jak mogę dodać więcej poziomów do mojego spisu treści?

Aby uwzględnić więcej poziomów w spisie treści, możesz zmodyfikować pole spisu treści i określić żądaną liczbę poziomów.

### Czy mogę zmienić pozycje tabulatorów dla określonych wpisów spisu treści?

Tak, jak pokazano w powyższym przykładzie kodu, możesz zmienić pozycje tabulatorów dla określonych wpisów spisu treści, iterując po akapitach i odpowiednio modyfikując tabulatory.