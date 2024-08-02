---
title: Sformatowana tabela
linktitle: Sformatowana tabela
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć i formatować tabele w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając ze szczegółowego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-tables/formatted-table/
---
## Wstęp

Programowe tworzenie i formatowanie tabel w dokumentach programu Word może wydawać się trudnym zadaniem, ale dzięki Aspose.Words dla .NET staje się to proste i łatwe w zarządzaniu. W tym samouczku przeprowadzimy Cię przez proces tworzenia sformatowanej tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Omówimy wszystko, od skonfigurowania środowiska po zapisanie dokumentu w pięknie sformatowanej tabeli.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnijmy się, że mamy wszystko, czego potrzebujemy:

1. Aspose.Words dla biblioteki .NET: Pobierz ją z[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: IDE takie jak Visual Studio.
3. .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.

## Importuj przestrzenie nazw

Przed napisaniem właściwego kodu musisz zaimportować niezbędne przestrzenie nazw:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Krok 1: Skonfiguruj katalog dokumentów

Najpierw musisz zdefiniować ścieżkę, w której zostanie zapisany dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać dokument.

## Krok 2: Zainicjuj dokument i narzędzie DocumentBuilder

Teraz zainicjuj nowy dokument i obiekt DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 The`DocumentBuilder` to klasa pomocnicza, która upraszcza proces tworzenia dokumentów.

## Krok 3: Uruchom tabelę

 Następnie rozpocznij tworzenie tabeli za pomocą`StartTable` metoda.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

Aby rozpocząć tabelę, konieczne jest wstawienie komórki.

## Krok 4: Zastosuj formatowanie całej tabeli

Możesz zastosować formatowanie wpływające na całą tabelę. Na przykład ustawienie lewego wcięcia:

```csharp
table.LeftIndent = 20.0;
```

## Krok 5: Sformatuj wiersz nagłówka

Ustaw wysokość, wyrównanie i inne właściwości wiersza nagłówka.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

Na tym etapie wyróżniamy wiersz nagłówka, ustawiając kolor tła, rozmiar czcionki i wyrównanie.

## Krok 6: Wstaw dodatkowe komórki nagłówka

Wstaw więcej komórek do wiersza nagłówka:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Krok 7: Sformatuj wiersze treści

Po ustawieniu nagłówka sformatuj treść tabeli:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Krok 8: Wstaw wiersze treści

Wstaw wiersze treści z treścią:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Powtórz dla dodatkowych rzędów:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## Krok 9: Zapisz dokument

Na koniec zapisz dokument we wskazanym katalogu:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Spowoduje to utworzenie i zapisanie dokumentu programu Word ze sformatowaną tabelą.

## Wniosek

I masz to! Wykonując poniższe kroki, możesz utworzyć dobrze sformatowaną tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Ta potężna biblioteka ułatwia programowe manipulowanie dokumentami programu Word, oszczędzając czas i wysiłek.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowego tworzenia, edytowania i konwertowania dokumentów programu Word.

### Czy mogę używać różnych kolorów w różnych rzędach?
Tak, możesz zastosować różne formatowanie, w tym kolory, do różnych wierszy lub komórek.

### Czy Aspose.Words dla .NET jest darmowy?
 Aspose.Words dla .NET jest biblioteką płatną, ale możesz ją pobrać[bezpłatna wersja próbna](https://releases.aspose.com/).

### Jak uzyskać wsparcie dla Aspose.Words dla .NET?
 Możesz uzyskać wsparcie od[Fora społeczności Aspose](https://forum.aspose.com/c/words/8).

### Czy mogę tworzyć inne typy dokumentów za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET obsługuje różne formaty dokumentów, w tym PDF, HTML i TXT.