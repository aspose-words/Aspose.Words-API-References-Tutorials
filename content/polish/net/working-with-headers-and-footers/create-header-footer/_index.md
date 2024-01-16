---
title: Utwórz stopkę nagłówka
linktitle: Utwórz stopkę nagłówka
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć nagłówki i stopki w dokumentach programu Word za pomocą Aspose.Words dla .NET. Dostosuj nagłówki i stopki dla każdej strony.
type: docs
weight: 10
url: /pl/net/working-with-headers-and-footers/create-header-footer/
---

Oto przewodnik krok po kroku wyjaśniający następujący kod źródłowy C# do tworzenia nagłówków i stopek przy użyciu funkcjonalności Aspose.Words dla .NET. Zanim użyjesz tego kodu, upewnij się, że w swoim projekcie umieściłeś bibliotekę Aspose.Words.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów, w którym zostanie zapisany edytowany dokument.

## Krok 2: Utwórz dokument i generator dokumentów

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj tworzymy instancję`Document` klasa i instancja`DocumentBuilder` klasa, która pozwoli nam manipulować dokumentem i dodawać elementy.

## Krok 3: Ustaw parametry strony i pierwszy nagłówek

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Określ, czy chcemy, aby nagłówki/stopki pierwszej strony różniły się od pozostałych stron.
// Do określenia można również użyć właściwości PageSetup.OddAndEvenPagesHeaderFooter
// różne nagłówki/stopki dla stron nieparzystych i parzystych.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Ustawiamy parametry strony, w tym odległość nagłówka, a następnie przechodzimy do głównego nagłówka (`HeaderPrimary`). Do dodawania tekstu i formatowania nagłówka używamy generatora dokumentów.

## Krok 4: Wstaw obraz i tekst w głównym nagłówku

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Używamy generatora dokumentów, aby wstawić obraz w lewym górnym rogu głównego nagłówka, a następnie dodajemy tekst wyrównany do prawej strony.

## Krok 5: Wstaw tabelę w stopce głównej

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Krok 6: Dodaj nową stronę i ustaw nagłówki/stopki

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Ta sekcja nie potrzebuje innego nagłówka/stopki dla pierwszej strony, potrzebujemy tylko jednej strony tytułowej w dokumencie,
// nagłówek/stopka tej strony została już zdefiniowana w poprzedniej sekcji.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Ta sekcja domyślnie wyświetla nagłówki/stopki z poprzedniej sekcji. Wywołaj currentSection.HeadersFooters.LinkToPrevious(false), aby przerwać to łącze,
// szerokość strony jest inna dla nowej sekcji, dlatego musimy ustawić inną szerokość komórek dla tabeli stopki.
currentSection.HeadersFooters.LinkToPrevious(false);

// Jeśli chcemy wykorzystać już istniejące nagłówki/stopki w tej sekcji,
//ale po wprowadzeniu kilku drobnych zmian sensowne może być skopiowanie nagłówków/stopek
// z poprzedniej sekcji i zastosuj niezbędne zmiany tam, gdzie chcemy.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Zapisz dokument
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Dodajemy podział strony i podział sekcji, aby utworzyć nową stronę, na której widoczne będą główne nagłówki/stopki. Ustawiamy parametry nowej sekcji, następnie używamy`CopyHeadersFootersFromPreviousSection` metoda kopiowania nagłówków/stopek z poprzedniej sekcji. Na koniec ustawiamy odpowiednie szerokości komórek dla głównej tabeli stopki i zapisujemy dokument.

### Przykładowy kod źródłowy do tworzenia nagłówków i stopek za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Określ, czy chcemy, aby nagłówki/stopki pierwszej strony różniły się od pozostałych stron.
// Aby określić, możesz także użyć właściwości PageSetup.OddAndEvenPagesHeaderFooter
// różne nagłówki/stopki dla stron nieparzystych i parzystych.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Wstaw umieszczony obraz w górnym/lewym rogu nagłówka.
// Odległość od górnej/lewej krawędzi strony jest ustawiona na 10 punktów.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Tablicę z dwiema komórkami wykorzystujemy do utworzenia jednej części tekstu w wierszu (z numeracją stron).
// Należy wyrównać do lewej, a drugą część tekstu (zgodnie z prawami autorskimi) do prawej.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Używa pól PAGE i NUMPAGES do automatycznego obliczenia bieżącego numeru strony i wielu stron.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Zrób podział strony, aby utworzyć drugą stronę, na której będą widoczne główne nagłówki/stopki.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Ta sekcja nie wymaga innego nagłówka/stopki pierwszej strony, wystarczy jedna strona tytułowa w dokumencie,
// nagłówek/stopka tej strony została już zdefiniowana w poprzedniej sekcji.
pageSetup.DifferentFirstPageHeaderFooter = false;

// W tej sekcji wyświetlane są nagłówki/stopki z poprzedniej sekcji
// domyślnie wywołaj currentSection.HeadersFooters.LinkToPrevious(false), aby anulować tę szerokość strony
// jest inna dla nowej sekcji i dlatego musimy ustawić inną szerokość komórek dla tabeli stopki.
currentSection.HeadersFooters.LinkToPrevious(false);

// Jeśli chcemy użyć już istniejącego zestawu nagłówków/stopek dla tej sekcji.
// Jednak po niewielkich modyfikacjach celowe może być skopiowanie nagłówków/stopek
// z poprzedniej sekcji i zastosuj niezbędne modyfikacje tam, gdzie chcemy.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Często zadawane pytania

#### P: Jak mogę dodać nagłówek do mojego dokumentu w Aspose.Words?

 O: Aby dodać nagłówek do swojego dokumentu w Aspose.Words, możesz użyć metody`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` metoda. Ta metoda dodaje główny nagłówek do pierwszej sekcji dokumentu.

#### P: Jak mogę dodać stopkę do mojego dokumentu w Aspose.Words?

 O: Aby dodać stopkę do dokumentu w Aspose.Words, możesz użyć metody`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`metoda. Ta metoda dodaje podstawową stopkę do pierwszej sekcji dokumentu.

#### P: Jak mogę dodać tekst do nagłówka lub stopki w Aspose.Words?

 O: Aby dodać tekst do nagłówka lub stopki w Aspose.Words, możesz użyć metody`HeaderFooter.Paragraphs` aby uzyskać zbiór akapitów nagłówka lub stopki, a następnie dodaj akapit zawierający tekst do tego zbioru za pomocą metody`ParagraphCollection.Add` metoda.

#### P: Czy mogę dostosować zawartość nagłówka lub stopki za pomocą obrazów i numerów stron w Aspose.Words?

 Odp.: Tak, możesz dostosować zawartość nagłówka lub stopki za pomocą obrazów i numerów stron w Aspose.Words. Możesz używać obiektów takich jak`Shape` aby dodać obrazy i obiekty, takie jak`Field` , aby dodać numery stron do nagłówka lub stopki.

#### P: Czy mogę zmienić czcionkę, rozmiar i kolor tekstu w nagłówku lub stopce w Aspose.Words?

 O: Tak, możesz zmienić czcionkę, rozmiar i kolor tekstu w nagłówku lub stopce w Aspose.Words. Można uzyskać dostęp do właściwości formatowania tekstu, takich jak`Font` zmienić czcionkę,`Size` dostosować rozmiar i`Color`aby ustawić kolor tekstu.