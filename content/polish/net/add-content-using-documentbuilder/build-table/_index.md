---
title: Utwórz tabelę w dokumencie programu Word
linktitle: Utwórz tabelę w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zbudować tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/build-table/
---
W tym samouczku krok po kroku dowiesz się, jak zbudować tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł utworzyć tabelę z niestandardowym formatowaniem i zawartością przy użyciu klasy DocumentBuilder.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument
Aby rozpocząć, utwórz nowy dokument, korzystając z klasy Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Uruchom tabelę
Następnie użyj metody StartTable klasy DocumentBuilder, aby rozpocząć budowanie tabeli:

```csharp
Table table = builder.StartTable();
```

## Krok 3: Wstaw komórki i dodaj zawartość
Teraz możesz wstawiać komórki do tabeli i dodawać do nich zawartość, korzystając z metod InsertCell i Write klasy DocumentBuilder. Dostosuj formatowanie komórek według potrzeb:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Krok 4: Zakończ rząd
Po dodaniu treści do komórek pierwszego wiersza należy zastosować metodę EndRow klasy DocumentBuilder, aby zakończyć wiersz:

```csharp
builder.EndRow();
```

## Krok 5: Dostosuj formatowanie wierszy
Możesz dostosować formatowanie wiersza, ustawiając właściwości obiektów RowFormat i CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Krok 6: Zakończ stół
Aby uzupełnić tabelę, użyj metody EndTable klasy DocumentBuilder:

```csharp
builder.EndTable();
```

### Przykładowy kod źródłowy do budowania tabeli przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do budowania tabeli przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak budować tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz tworzyć tabele z niestandardowym formatowaniem.

### Często zadawane pytania dotyczące tabeli kompilacji w dokumencie programu Word

#### P: Co to jest Aspose.Words dla .NET?

O: Aspose.Words dla .NET to potężna biblioteka do przetwarzania dokumentów, która pozwala programistom programowo tworzyć, czytać, edytować i konwertować dokumenty Microsoft Word w aplikacjach .NET. Zapewnia szeroką gamę funkcji do pracy z dokumentami programu Word, takich jak manipulowanie tekstem, tworzenie tabel, ochrona dokumentów, formatowanie i inne.

#### P: Jak mogę zbudować tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby zbudować tabelę w dokumencie programu Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz nową instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Użyj`StartTable` metoda`DocumentBuilder`klasę, aby rozpocząć budowę stołu.
3.  Wstaw komórki do tabeli i dodaj zawartość za pomocą`InsertCell` I`Write` metody`DocumentBuilder` klasa.
4.  Zakończ wiersz za pomocą`EndRow` metoda`DocumentBuilder` klasa.
5.  Dostosuj formatowanie wierszy, ustawiając właściwości pliku`RowFormat` I`CellFormat` obiekty.
6.  Zakończ tabelę za pomocą`EndTable` metoda`DocumentBuilder` klasa.
7. Zapisz dokument.

#### P: Jak mogę dostosować formatowanie tabeli i jej komórek?

 O: Możesz dostosować formatowanie tabeli i jej komórek, ustawiając różne właściwości pliku`RowFormat` I`CellFormat` obiekty. Można na przykład dostosować wyrównanie komórek, orientację tekstu w pionie i poziomie, wysokość komórki, wysokość wiersza i inne. Korzystając z tych właściwości, można uzyskać pożądany wygląd tabeli i jej zawartości.

#### P: Czy mogę tworzyć złożone tabele ze scalonych komórek i innych zaawansowanych funkcji?

 Odp.: Tak, Aspose.Words dla .NET zapewnia zaawansowane funkcje do tworzenia złożonych tabel, w tym obsługę scalonych komórek, zagnieżdżonych tabel i złożonych układów tabel. Możesz skorzystać z`MergeCells` metoda łączenia komórek,`StartTable`metoda tworzenia tabel zagnieżdżonych i inne metody osiągania pożądanej struktury tabeli.

#### P: Czy Aspose.Words dla .NET jest kompatybilny z różnymi formatami dokumentów programu Word?

Odp.: Tak, Aspose.Words dla .NET jest kompatybilny z różnymi formatami dokumentów Word, w tym DOC, DOCX, RTF i innymi. Obsługuje zarówno starsze formaty (DOC), jak i nowoczesne formaty oparte na XML (DOCX) i umożliwia bezproblemową pracę z dokumentami w różnych formatach.

#### P: Gdzie mogę znaleźć więcej informacji i dokumentacji dla Aspose.Words dla .NET?

 O: Obszerną dokumentację i przykłady kodu można znaleźć na stronie[Referencje API](https://reference.aspose.com/words/net/). Dokumentacja zawiera szczegółowe informacje na temat funkcji biblioteki i sposobu ich wykorzystania w aplikacjach .NET.