---
title: Format wiersza Wyłącz podział stron
linktitle: Format wiersza Wyłącz podział stron
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyłączyć podziały wierszy na stronach w dokumentach programu Word za pomocą Aspose.Words dla .NET, aby zachować czytelność i formatowanie tabeli.
type: docs
weight: 10
url: /pl/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Wstęp

Pracując z tabelami w dokumentach programu Word, warto upewnić się, że wiersze nie dzielą się na strony, co może mieć istotne znaczenie dla zachowania czytelności i formatowania dokumentów. Aspose.Words dla .NET zapewnia łatwy sposób wyłączania podziału wierszy na stronach.

W tym samouczku przeprowadzimy Cię przez proces wyłączania podziałów wierszy na stronach w dokumencie programu Word za pomocą Aspose.Words dla .NET.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Zainstalowana biblioteka Aspose.Words dla .NET.
- Dokument programu Word z tabelą obejmującą wiele stron.

## Importuj przestrzenie nazw

Najpierw zaimportuj niezbędne przestrzenie nazw do swojego projektu:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Krok 1: Załaduj dokument

Załaduj dokument zawierający tabelę zajmującą wiele stron.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Krok 2: Uzyskaj dostęp do tabeli

Uzyskaj dostęp do pierwszej tabeli w dokumencie. Zakłada się, że tabela, którą chcesz zmodyfikować, jest pierwszą tabelą w dokumencie.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Krok 3: Wyłącz dzielenie stron dla wszystkich wierszy

 Wykonaj pętlę przez każdy wiersz tabeli i ustaw opcję`AllowBreakAcrossPages`własność do`false`. Dzięki temu wiersze nie będą się rozdzielać na stronach.

```csharp
// Wyłącz dzielenie stron dla wszystkich wierszy w tabeli.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Krok 4: Zapisz dokument

Zapisz zmodyfikowany dokument w określonym katalogu.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Wniosek

W tym samouczku pokazaliśmy, jak wyłączyć podziały wierszy na stronach w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując czynności opisane powyżej, możesz mieć pewność, że wiersze tabeli pozostaną nienaruszone i nie zostaną podzielone na strony, zachowując czytelność i formatowanie dokumentu.

## Często zadawane pytania

### Czy mogę wyłączyć podział wierszy na stronach dla określonego wiersza zamiast dla wszystkich wierszy?  
 Tak, możesz wyłączyć podział wierszy dla określonych wierszy, uzyskując dostęp do żądanego wiersza i ustawiając go`AllowBreakAcrossPages`własność do`false`.

### Czy ta metoda działa w przypadku tabel ze scalonymi komórkami?  
 Tak, ta metoda działa w przypadku tabel ze scalonymi komórkami. Nieruchomość`AllowBreakAcrossPages` dotyczy całego wiersza, niezależnie od scalania komórek.

### Czy ta metoda zadziała, jeśli tabela jest zagnieżdżona w innej tabeli?  
Tak, możesz uzyskać dostęp do zagnieżdżonych tabel i je modyfikować w ten sam sposób. Upewnij się, że poprawnie odwołujesz się do zagnieżdżonej tabeli poprzez jej indeks lub inne właściwości.

### Jak mogę sprawdzić, czy wiersz umożliwia dzielenie stron?  
 Możesz sprawdzić, czy wiersz umożliwia dzielenie stron, uzyskując dostęp do`AllowBreakAcrossPages` własność`RowFormat` i sprawdzenie jego wartości.

### Czy istnieje sposób na zastosowanie tego ustawienia do wszystkich tabel w dokumencie?  
Tak, możesz przeglądać wszystkie tabele w dokumencie i zastosować to ustawienie do każdej z nich.