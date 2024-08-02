---
title: Ustaw względną pozycję poziomą lub pionową
linktitle: Ustaw względną pozycję poziomą lub pionową
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić względne położenie poziome i pionowe tabel w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---
## Wstęp

Czy kiedykolwiek miałeś wrażenie, że utknąłeś w miejscu, w którym chcesz ustawić tabele w dokumentach programu Word? Cóż, nie jesteś sam. Niezależnie od tego, czy tworzysz profesjonalny raport, czy stylową broszurę, dopasowanie tabel może mieć ogromne znaczenie. Właśnie tam przydaje się Aspose.Words dla .NET. Ten samouczek poprowadzi Cię krok po kroku, jak ustawić względne położenie poziome lub pionowe tabel w dokumentach programu Word. Zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Aspose.Words dla .NET: Jeśli jeszcze tego nie zrobiłeś, możesz go pobrać[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Visual Studio lub dowolne inne IDE kompatybilne z .NET.
3. Podstawowa znajomość języka C#: W tym samouczku założono, że znasz podstawy programowania w języku C#.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw. Jest to niezbędne do uzyskania dostępu do funkcjonalności Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Krok 1: Załaduj swój dokument

Aby rozpocząć, musisz załadować dokument Word do programu. Oto jak możesz to zrobić:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Ten fragment kodu ustawia ścieżkę do katalogu dokumentów i ładuje konkretny dokument, nad którym chcesz pracować. Upewnij się, że ścieżka dokumentu jest poprawna, aby uniknąć problemów z ładowaniem.

## Krok 2: Uzyskaj dostęp do tabeli

Następnie musimy uzyskać dostęp do tabeli w dokumencie. Zazwyczaj chcesz pracować z pierwszą tabelą w sekcji treści.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

Ta linia kodu pobiera pierwszą tabelę z treści dokumentu. Jeśli dokument zawiera wiele tabel, możesz odpowiednio dostosować indeks.

## Krok 3: Ustaw pozycję poziomą

Teraz ustalmy poziome położenie tabeli względem konkretnego elementu. W tym przykładzie ustawimy go względem kolumny.

```csharp
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
```

 Ustawiając`HorizontalAnchor` Do`RelativeHorizontalPosition.Column`, mówisz tabeli, aby wyrównała się poziomo względem kolumny, w której się znajduje.

## Krok 4: Ustaw pozycję pionową

Podobnie jak w przypadku pozycjonowania poziomego, można również ustawić pozycję pionową. Tutaj pozycjonujemy go względem strony.

```csharp
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Ustawianie`VerticalAnchor` Do`RelativeVerticalPosition.Page` zapewnia wyrównanie tabeli w pionie względem strony.

## Krok 5: Zapisz swój dokument

Na koniec zapisz zmiany w nowym dokumencie. Jest to kluczowy krok zapewniający zachowanie zmian.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

To polecenie zapisuje zmodyfikowany dokument pod nową nazwą, zapewniając, że oryginalny plik nie zostanie nadpisany.

## Wniosek

I masz to! Pomyślnie ustawiłeś względne położenie poziome i pionowe tabeli w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Dzięki tej nowo odkrytej umiejętności możesz poprawić układ i czytelność swoich dokumentów, czyniąc je bardziej profesjonalnymi i dopracowanymi. Eksperymentuj z różnymi pozycjami i zobacz, która najlepiej odpowiada Twoim potrzebom.

## Często zadawane pytania

### Czy mogę pozycjonować tabele względem innych elementów?  
Tak, Aspose.Words umożliwia pozycjonowanie tabel względem różnych elementów, takich jak marginesy, strony, kolumny i inne.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?  
 Tak, możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy) lub zdobądź licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?  
 Absolutnie! Możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Czy mogę używać Aspose.Words z innymi językami programowania?  
Aspose.Words jest przeznaczony głównie dla .NET, ale dostępne są wersje dla Java, Python i innych platform.

### Gdzie mogę znaleźć bardziej szczegółową dokumentację?  
Aby uzyskać bardziej szczegółowe informacje, zapoznaj się z dokumentacją Aspose.Words[Tutaj](https://reference.aspose.com/words/net/).