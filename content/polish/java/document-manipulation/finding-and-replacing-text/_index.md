---
title: Znajdowanie i zastępowanie tekstu w Aspose.Words dla Java
linktitle: Znajdowanie i zastępowanie tekstu
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak znajdować i zamieniać tekst w dokumentach programu Word za pomocą Aspose.Words dla Java. Przewodnik krok po kroku z przykładami kodu. Popraw swoje umiejętności manipulowania dokumentami Java.
type: docs
weight: 15
url: /pl/java/document-manipulation/finding-and-replacing-text/
---

## Wprowadzenie do wyszukiwania i zastępowania tekstu w Aspose.Words dla Java

Aspose.Words for Java to potężny interfejs API języka Java, który umożliwia programową pracę z dokumentami programu Word. Jednym z typowych zadań podczas pracy z dokumentami programu Word jest wyszukiwanie i zastępowanie tekstu. Niezależnie od tego, czy chcesz zaktualizować symbole zastępcze w szablonach, czy wykonać bardziej złożone manipulacje tekstem, Aspose.Words dla Java może pomóc Ci efektywnie osiągnąć Twoje cele.

## Warunki wstępne

Zanim zagłębimy się w szczegóły wyszukiwania i zastępowania tekstu, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Aspose.Words dla biblioteki Java
- Przykładowy dokument programu Word do pracy

 Możesz pobrać bibliotekę Aspose.Words dla Java ze strony[Tutaj](https://releases.aspose.com/words/java/).

## Znajdowanie i zastępowanie prostego tekstu

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz narzędzie do tworzenia dokumentów
DocumentBuilder builder = new DocumentBuilder(doc);

// Znajdź i zamień tekst
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

 W tym przykładzie ładujemy dokument Word, tworzymy plik`DocumentBuilder` i użyj`replace` metoda wyszukiwania i zamiany „starego tekstu” na „nowy tekst” w dokumencie.

## Używanie wyrażeń regularnych

Wyrażenia regularne zapewniają zaawansowane możliwości dopasowywania wzorców do wyszukiwania i zastępowania tekstu. Aspose.Words for Java obsługuje wyrażenia regularne dla bardziej zaawansowanych operacji wyszukiwania i zamiany.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz narzędzie do tworzenia dokumentów
DocumentBuilder builder = new DocumentBuilder(doc);

// Używaj wyrażeń regularnych do wyszukiwania i zastępowania tekstu
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

W tym przykładzie używamy wzorca wyrażenia regularnego do wyszukiwania i zastępowania tekstu w dokumencie.

## Ignorowanie tekstu w polach

Możesz skonfigurować Aspose.Words tak, aby ignorował tekst wewnątrz pól podczas wykonywania operacji znajdowania i zamiany.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw IgnoreFields na true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace("text-to-replace", "new-text", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Jest to przydatne, gdy chcesz wykluczyć z zastępowania tekst znajdujący się w polach, np. polach scalających.

## Ignorowanie tekstu w środku Usuń poprawki

Możesz skonfigurować Aspose.Words tak, aby ignorował tekst w usuwanych wersjach podczas operacji znajdowania i zamiany.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw IgnoreDeleted na true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace("text-to-replace", "new-text", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Pozwala to wykluczyć z zastępowania tekst oznaczony do usunięcia w prześledzonych zmianach.

## Ignorowanie tekstu wewnątrz wstawianych wersji

Możesz skonfigurować Aspose.Words tak, aby ignorował tekst wewnątrz wersji wstawiania podczas operacji znajdowania i zamiany.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw IgnoreInserted na true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace("text-to-replace", "new-text", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Umożliwia to wykluczenie z zastępowania tekstu oznaczonego jako wstawiony w prześledzonych zmianach.

## Zamiana tekstu na HTML

Możesz użyć Aspose.Words dla Java, aby zastąpić tekst treścią HTML.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions z niestandardowym wywołaniem zwrotnym zastępującym
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

 W tym przykładzie używamy zwyczaju`ReplaceWithHtmlEvaluator` aby zastąpić tekst treścią HTML.

## Zastępowanie tekstu w nagłówkach i stopkach

Możesz wyszukiwać i zamieniać tekst w nagłówkach i stopkach dokumentu programu Word.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Pobierz kolekcję nagłówków i stopek
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Wybierz typ nagłówka lub stopki, w którym chcesz zastąpić tekst (np. HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Utwórz instancję FindReplaceOptions i zastosuj ją do zakresu stopki
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Umożliwia to zamianę tekstu, szczególnie w nagłówkach i stopkach.

## Wyświetlanie zmian w zamówieniach nagłówków i stopek

Możesz użyć Aspose.Words, aby pokazać zmiany w kolejności nagłówków i stopek w swoim dokumencie.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Zdobądź pierwszą sekcję
Section firstPageSection = doc.getFirstSection();

// Utwórz instancję FindReplaceOptions i zastosuj ją do zakresu dokumentu
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Zastąp tekst wpływający na kolejność nagłówków i stopek
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Dzięki temu możesz wizualizować zmiany związane z kolejnością nagłówków i stopek w dokumencie.

## Zastępowanie tekstu polami

Możesz zastąpić tekst polami za pomocą Aspose.Words dla Java.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw niestandardowe wywołanie zwrotne zastępujące pola
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

 W tym przykładzie zastępujemy tekst polami i określamy typ pola (np.`FieldType.FIELD_MERGE_FIELD`).

## Zastąpienie oceniającego

Możesz użyć niestandardowego narzędzia oceniającego, aby dynamicznie określić tekst zastępczy.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw niestandardowe wywołanie zwrotne zastępujące
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

W tym przykładzie używamy niestandardowego narzędzia oceniającego (`MyReplaceEvaluator`), aby zastąpić tekst.

## Zastąpienie przez Regex

Aspose.Words dla Java umożliwia zamianę tekstu za pomocą wyrażeń regularnych.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Używaj wyrażeń regularnych do wyszukiwania i zastępowania tekstu
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

W tym przykładzie używamy wzorca wyrażenia regularnego do wyszukiwania i zastępowania tekstu w dokumencie.

## Rozpoznawanie i substytucje w ramach wzorców zastępczych

Możesz rozpoznawać i dokonywać podstawień we wzorcach zamiany, używając Aspose.Words dla Java.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

//Utwórz instancję FindReplaceOptions z opcją UseSubstitutions ustawioną na true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Użyj opcji podczas zastępowania tekstu wzorkiem
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Umożliwia to wykonywanie podstawień w ramach wzorców zamiany w celu uzyskania bardziej zaawansowanych zamian.

## Zamiana na ciąg

Możesz zastąpić tekst prostym ciągiem znaków, używając Aspose.Words dla Java.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Zastąp tekst ciągiem
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

W tym przykładzie zamieniamy w dokumencie „tekst do zastąpienia” na „nowy ciąg znaków”.

## Korzystanie ze starszego porządku

Podczas wykonywania operacji znajdowania i zamieniania można używać starszej kolejności.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Utwórz instancję FindReplaceOptions i ustaw wartość UseLegacyOrder na true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Użyj opcji podczas zastępowania tekstu
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Dzięki temu można używać starszej kolejności do operacji wyszukiwania i zamiany.

## Zastępowanie tekstu w tabeli

Możesz znajdować i zamieniać tekst w tabelach w dokumencie programu Word.

```java
// Załaduj dokument
Document doc = new Document("your-document.docx");

// Uzyskaj konkretną tabelę (np. pierwszą tabelę)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Użyj FindReplaceOptions do zamiany tekstu w tabeli
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Zapisz zmodyfikowany dokument
doc.save("modified-document.docx");
```

Umożliwia to zamianę tekstu w obrębie tabel.

## Wniosek

Aspose.Words dla Java zapewnia wszechstronne możliwości wyszukiwania i zastępowania tekstu w dokumentach programu Word. Niezależnie od tego, czy chcesz wykonać proste zastąpienie tekstu, czy bardziej zaawansowane operacje przy użyciu wyrażeń regularnych, manipulacji polami lub niestandardowych ewaluatorów, Aspose.Words dla Java jest dla Ciebie rozwiązaniem. Zapoznaj się z obszerną dokumentacją i przykładami dostarczonymi przez Aspose, aby wykorzystać pełny potencjał tej potężnej biblioteki Java.

## Często zadawane pytania

### Jak pobrać Aspose.Words dla Java?

 Możesz pobrać Aspose.Words dla Java ze strony internetowej, odwiedzając[ten link](https://releases.aspose.com/words/java/).

### Czy mogę używać wyrażeń regularnych do zastępowania tekstu?

Tak, możesz używać wyrażeń regularnych do zastępowania tekstu w Aspose.Words dla Java. Umożliwia to wykonywanie bardziej zaawansowanych i elastycznych operacji wyszukiwania i zamiany.

### Jak mogę zignorować tekst wewnątrz pól podczas zamiany?

 Aby zignorować tekst wewnątrz pól podczas zamiany, możesz ustawić opcję`IgnoreFields` własność`FindReplaceOptions` Do`true`Dzięki temu tekst w polach, takich jak pola scalania, zostanie wykluczony z zamiany.

### Czy mogę zastąpić tekst wewnątrz nagłówków i stopek?

 Tak, możesz zastąpić tekst wewnątrz nagłówków i stopek dokumentu programu Word. Po prostu przejdź do odpowiedniego nagłówka lub stopki i użyj przycisku`replace` metoda z pożądanym`FindReplaceOptions`.

### Do czego służy opcja UseLegacyOrder?

 The`UseLegacyOrder` opcja w`FindReplaceOptions` umożliwia użycie starszej kolejności podczas wykonywania operacji wyszukiwania i zamiany. Może to być przydatne w niektórych scenariuszach, w których pożądane jest zachowanie starszej kolejności.