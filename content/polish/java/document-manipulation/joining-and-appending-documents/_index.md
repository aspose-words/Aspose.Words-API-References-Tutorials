---
title: Łączenie i dołączanie dokumentów w Aspose.Words dla Java
linktitle: Łączenie i dołączanie dokumentów
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak bez wysiłku łączyć i dołączać dokumenty za pomocą Aspose.Words dla Java. Zachowaj formatowanie, zarządzaj nagłówkami, stopkami i nie tylko.
type: docs
weight: 30
url: /pl/java/document-manipulation/joining-and-appending-documents/
---

## Wprowadzenie do łączenia i dołączania dokumentów w Aspose.Words dla Java

W tym samouczku omówimy, jak łączyć i dołączać dokumenty przy użyciu biblioteki Aspose.Words for Java. Dowiesz się, jak płynnie łączyć wiele dokumentów, zachowując formatowanie i strukturę.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz skonfigurowany Aspose.Words for Java API w swoim projekcie Java.

## Opcje łączenia dokumentów

### Proste dołączanie

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Dołącz z opcjami formatu importu

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Dołącz do pustego dokumentu

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Dołącz z konwersją numeru strony

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Konwertuj pola NUMPAGES
dstDoc.updatePageLayout(); // Zaktualizuj układ strony, aby uzyskać prawidłową numerację
```

## Obsługa różnych ustawień strony

Podczas dołączania dokumentów z różnymi ustawieniami strony:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Upewnij się, że ustawienia strony odpowiadają dokumentowi docelowemu
```

## Łączenie dokumentów o różnych stylach

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Inteligentne zachowanie w stylu

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Wstawianie dokumentów za pomocą DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Zachowanie numeracji źródeł

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Obsługa pól tekstowych

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Zarządzanie nagłówkami i stopkami

### Łączenie nagłówków i stopek

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Odłączanie nagłówków i stopek

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Wniosek

Aspose.Words dla Java zapewnia elastyczne i wydajne narzędzia do łączenia i dołączania dokumentów, niezależnie od tego, czy potrzebujesz zachować formatowanie, obsługiwać różne ustawienia strony, czy zarządzać nagłówkami i stopkami. Eksperymentuj z tymi technikami, aby spełnić określone potrzeby w zakresie przetwarzania dokumentów.

## Często zadawane pytania

### Jak płynnie łączyć dokumenty o różnych stylach?

 Aby połączyć dokumenty o różnych stylach, użyj`ImportFormatMode.USE_DESTINATION_STYLES` podczas dołączania.

### Czy mogę zachować numerację stron podczas dołączania dokumentów?

 Tak, możesz zachować numerację stron za pomocą opcji`convertNumPageFieldsToPageRef` metody i aktualizacji układu strony.

### Co to jest zachowanie inteligentnego stylu?

 Inteligentne zachowanie stylu pomaga zachować spójne style podczas dołączania dokumentów. Użyj go z`ImportFormatOptions` dla lepszych wyników.

### Jak obsługiwać pola tekstowe podczas dołączania dokumentów?

Ustawić`importFormatOptions.setIgnoreTextBoxes(false)` aby uwzględnić pola tekstowe podczas dołączania.

### Co się stanie, jeśli chcę połączyć/odłączyć nagłówki i stopki między dokumentami?

 Możesz łączyć nagłówki i stopki za pomocą`linkToPrevious(true)` lub rozłącz je za pomocą`linkToPrevious(false)` według potrzeb.