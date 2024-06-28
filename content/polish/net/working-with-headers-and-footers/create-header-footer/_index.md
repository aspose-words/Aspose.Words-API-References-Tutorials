---
title: Utwórz stopkę nagłówka
linktitle: Utwórz stopkę nagłówka
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać i dostosowywać nagłówki i stopki w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Ten przewodnik krok po kroku zapewnia profesjonalne formatowanie dokumentu.
type: docs
weight: 10
url: /pl/net/working-with-headers-and-footers/create-header-footer/
---

Dodawanie nagłówków i stopek do dokumentów może zwiększyć ich profesjonalizm i czytelność. Dzięki Aspose.Words dla .NET możesz łatwo tworzyć i dostosowywać nagłówki i stopki dla swoich dokumentów Word. W tym samouczku przeprowadzimy Cię krok po kroku przez proces, upewniając się, że możesz bezproblemowo wdrożyć te funkcje.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

-  Aspose.Words dla .NET: Pobierz i zainstaluj z[link do pobrania](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: takie jak Visual Studio, do pisania i uruchamiania kodu.
- Podstawowa znajomość C#: Zrozumienie C# i frameworku .NET.
- Przykładowy dokument: Przykładowy dokument umożliwiający zastosowanie nagłówków i stopek lub utworzenie nowego, jak pokazano w samouczku.

## Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Krok 1: Zdefiniuj katalog dokumentów

Zdefiniuj katalog, w którym zostanie zapisany dokument. Pomaga to w skutecznym zarządzaniu ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Krok 2: Utwórz nowy dokument

 Utwórz nowy dokument i a`DocumentBuilder` aby ułatwić dodawanie treści.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Skonfiguruj ustawienia strony

Skonfiguruj ustawienia strony, w tym to, czy pierwsza strona będzie miała inny nagłówek/stopkę.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Krok 4: Dodaj nagłówek do pierwszej strony

Przejdź do sekcji nagłówka pierwszej strony i skonfiguruj tekst nagłówka.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Krok 5: Dodaj nagłówek podstawowy

Przejdź do głównej sekcji nagłówka i wstaw obraz i tekst.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Wstaw obraz do nagłówka
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Krok 6: Dodaj główną stopkę

Przejdź do głównej sekcji stopki i utwórz tabelę, aby sformatować zawartość stopki.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Dodaj numerację stron
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
```

## Krok 7: Dodaj treść i podziały stron

Przejdź na koniec dokumentu, dodaj podział strony i utwórz nową sekcję z innymi ustawieniami strony.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Krok 8: Skopiuj nagłówki i stopki z poprzedniej sekcji

Jeśli chcesz ponownie wykorzystać nagłówki i stopki z poprzedniej sekcji, skopiuj je i zastosuj niezbędne modyfikacje.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Wniosek

Wykonując te kroki, możesz skutecznie dodawać i dostosowywać nagłówki i stopki w dokumentach programu Word za pomocą Aspose.Words dla .NET. Poprawia to wygląd i profesjonalizm dokumentu, czyniąc go bardziej czytelnym i wciągającym.

## Często zadawane pytania

### P1: Co to jest Aspose.Words dla .NET?

Aspose.Words dla .NET to biblioteka, która umożliwia programistom programowe tworzenie, edytowanie i konwertowanie dokumentów programu Word w aplikacjach .NET.

### P2: Czy mogę dodać obrazy do nagłówka lub stopki?

 Tak, możesz łatwo dodawać obrazy do nagłówka lub stopki za pomocą`DocumentBuilder.InsertImage` metoda.

### P3: Jak ustawić różne nagłówki i stopki dla pierwszej strony?

 Możesz ustawić różne nagłówki i stopki dla pierwszej strony, korzystając z opcji`DifferentFirstPageHeaderFooter` własność`PageSetup` klasa.

### P4: Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words?

 Obszerną dokumentację można znaleźć na stronie[Strona dokumentacji API Aspose.Words](https://reference.aspose.com/words/net/).

### P5: Czy dostępna jest obsługa Aspose.Words?

 Tak, Aspose oferuje wsparcie za pośrednictwem swoich[forum wsparcia](https://forum.aspose.com/c/words/8).
