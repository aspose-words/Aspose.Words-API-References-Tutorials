---
title: Pobierz preferowany typ szerokości
linktitle: Pobierz preferowany typ szerokości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pobrać typ i preferowaną wartość szerokości komórki w tabeli programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/retrieve-preferred-width-type/
---

tym samouczku dowiemy się, jak pobrać preferowany typ szerokości i jego wartość z komórki tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł pobrać preferowany typ szerokości (bezwzględny, względny lub automatyczny) i jego wartość dla określonej komórki w tabelach dokumentów programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załaduj dokument
Aby rozpocząć przetwarzanie tekstu w dokumencie, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów i podać poprawną nazwę pliku.

## Krok 3: Pobieranie preferowanego typu i wartości szerokości
Następnie pobierzemy preferowany typ szerokości i jego wartość dla określonej komórki tabeli. Użyj następującego kodu:

```csharp
// Odzyskaj stół
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Aktywuj automatyczną regulację stołu
table. AllowAutoFit = true;

// Pobierz pierwszą komórkę pierwszego wiersza
Cell firstCell = table.FirstRow.FirstCell;

// Pobierz preferowany typ szerokości i jego wartość
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Tutaj używamy dokumentu do pobrania pierwszej tabeli, następnie umożliwiamy automatyczne dopasowanie tabeli za pomocą`AllowAutoFit` nieruchomość. Następnie pobieramy pierwszą komórkę pierwszego wiersza tabeli. Z tej komórki możemy pobrać preferowany typ szerokości za pomocą`PreferredWidth.Type` nieruchomość i jej wartość`PreferredWidth.Value` nieruchomość.

### Przykładowy kod źródłowy dla opcji Pobierz preferowany typ szerokości przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Wniosek
W tym samouczku nauczyliśmy się, jak pobrać preferowany typ szerokości i jego wartość z komórki tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz pobrać te informacje dla określonych komórek w tabelach dokumentów programu Word.