---
title: Zapisywanie dokumentów w formacie PDF w Aspose.Words dla Java
linktitle: Zapisywanie dokumentów w formacie PDF
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak zapisywać dokumenty programu Word w formacie PDF przy użyciu Aspose.Words dla Java. Dostosuj czcionki, właściwości i jakość obrazu. Obszerny przewodnik po konwersji plików PDF.
type: docs
weight: 22
url: /pl/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Wprowadzenie do zapisywania dokumentów w formacie PDF w Aspose.Words dla Java

W tym przewodniku krok po kroku omówimy, jak zapisywać dokumenty w formacie PDF przy użyciu Aspose.Words dla Java. Omówimy różne aspekty konwersji plików PDF i podamy przykłady kodu, aby ułatwić ten proces.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Words dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

## Konwersja dokumentu do formatu PDF

Aby przekonwertować dokument Word na format PDF, możesz użyć następującego fragmentu kodu:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Zastępować`"input.docx"` ze ścieżką do dokumentu programu Word i`"output.pdf"` z żądaną ścieżką wyjściowego pliku PDF.

## Kontrolowanie opcji zapisywania plików PDF

 Możesz kontrolować różne opcje zapisywania plików PDF za pomocą`PdfSaveOptions` klasa. Na przykład możesz ustawić wyświetlany tytuł dokumentu PDF w następujący sposób:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Osadzanie czcionek w formacie PDF

Aby osadzić czcionki w wygenerowanym pliku PDF, użyj następującego kodu:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Dostosowywanie właściwości dokumentu

Możesz dostosować właściwości dokumentu w wygenerowanym pliku PDF. Na przykład:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Eksportowanie struktury dokumentu

 Aby wyeksportować strukturę dokumentu, ustaw opcję`exportDocumentStructure` opcja`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Kompresja obrazu

Możesz kontrolować kompresję obrazu za pomocą następującego kodu:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Aktualizowanie ostatnio wydrukowanej właściwości

Aby zaktualizować właściwość „Ostatni wydruk” w pliku PDF, użyj:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Renderowanie efektów 3D DML

Aby uzyskać zaawansowane renderowanie efektów 3D DML, ustaw tryb renderowania:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Interpolacja obrazów

Możesz włączyć interpolację obrazu, aby poprawić jakość obrazu:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Wniosek

Aspose.Words for Java zapewnia wszechstronne możliwości konwersji dokumentów Word do formatu PDF z elastycznością i opcjami dostosowywania. Możesz kontrolować różne aspekty wyjściowego pliku PDF, w tym czcionki, właściwości dokumentu, kompresję obrazu i inne.

## Często zadawane pytania

### Jak przekonwertować dokument programu Word do formatu PDF za pomocą Aspose.Words dla Java?

Aby przekonwertować dokument Word na format PDF, użyj następującego kodu:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Zastępować`"input.docx"` ze ścieżką do dokumentu programu Word i`"output.pdf"` z żądaną ścieżką wyjściowego pliku PDF.

### Czy mogę osadzić czcionki w pliku PDF wygenerowanym przez Aspose.Words dla Java?

 Tak, możesz osadzać czcionki w pliku PDF, ustawiając opcję`setEmbedFullFonts` opcja`true` W`PdfSaveOptions`. Oto przykład:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Jak dostosować właściwości dokumentu w wygenerowanym pliku PDF?

 Możesz dostosować właściwości dokumentu w pliku PDF za pomocą`setCustomPropertiesExport` opcja w`PdfSaveOptions`. Na przykład:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Jaki jest cel kompresji obrazu w Aspose.Words dla Java?

 Kompresja obrazu pozwala kontrolować jakość i rozmiar obrazów w generowanym pliku PDF. Tryb kompresji obrazu można ustawić za pomocą`setImageCompression` W`PdfSaveOptions`.

### Jak zaktualizować właściwość „Ostatni wydruk” w pliku PDF?

 Możesz zaktualizować właściwość „Ostatni wydruk” w pliku PDF, ustawiając`setUpdateLastPrintedProperty` Do`true` W`PdfSaveOptions`. Będzie to odzwierciedlać ostatnią wydrukowaną datę w metadanych PDF.

### Jak mogę poprawić jakość obrazu podczas konwersji do formatu PDF?

 Aby poprawić jakość obrazu, włącz interpolację obrazu poprzez ustawienie`setInterpolateImages` Do`true` W`PdfSaveOptions`. Dzięki temu obrazy w formacie PDF będą płynniejsze i lepszej jakości.