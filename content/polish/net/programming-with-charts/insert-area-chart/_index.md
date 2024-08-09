---
title: Wstaw wykres warstwowy do dokumentu programu Word
linktitle: Wstaw wykres warstwowy do dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić wykres warstwowy do dokumentu za pomocą Aspose.Words dla .NET. Dodaj dane serii i zapisz dokument z wykresem.
type: docs
weight: 10
url: /pl/net/programming-with-charts/insert-area-chart/
---
## Wstęp

Witamy w tym przewodniku krok po kroku dotyczącym wstawiania wykresu warstwowego do dokumentu programu Word za pomocą Aspose.Words dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek przeprowadzi Cię przez wszystko, co musisz wiedzieć, aby tworzyć wspaniałe i pouczające wykresy warstwowe w dokumentach programu Word. Omówimy wymagania wstępne, pokażemy, jak zaimportować niezbędne przestrzenie nazw i przeprowadzimy Cię przez każdy etap procesu za pomocą jasnych, łatwych do wykonania instrukcji.

## Warunki wstępne

Zanim zagłębimy się w szczegóły, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć:

1.  Aspose.Words dla .NET: Upewnij się, że masz zainstalowany Aspose.Words dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/words/net/).
2. .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.
3. IDE: Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio, do pisania i wykonywania kodu.
4. Podstawowa znajomość języka C#: Pomocna będzie podstawowa znajomość programowania w języku C#.

Po spełnieniu tych wymagań wstępnych można przystąpić do tworzenia pięknych wykresów warstwowych w dokumentach programu Word.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Te przestrzenie nazw zapewniają klasy i metody wymagane do pracy z dokumentami i wykresami programu Word w Aspose.Words dla .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Teraz, gdy zaimportowaliśmy już podstawowe przestrzenie nazw, przejdźmy do tworzenia naszego dokumentu i krok po kroku wstawiania wykresu warstwowego.

## Krok 1: Utwórz nowy dokument Word

Zacznijmy od utworzenia nowego dokumentu Word. To będzie baza, w której umieścimy nasz wykres warstwowy.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Na tym etapie inicjujemy nowy plik`Document` obiekt reprezentujący nasz dokument programu Word.

## Krok 2: Użyj narzędzia DocumentBuilder, aby wstawić wykres

 Następnie użyjemy`DocumentBuilder` class, aby wstawić wykres warstwowy do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Tutaj tworzymy`DocumentBuilder` obiektu i za jego pomocą wstawić do naszego dokumentu wykres warstwowy o określonych wymiarach (432x252).

## Krok 3: Uzyskaj dostęp do obiektu wykresu

 Po wstawieniu wykresu musimy uzyskać dostęp do pliku`Chart` obiekt, aby dostosować nasz wykres warstwowy.

```csharp
Chart chart = shape.Chart;
```

 Ta linia kodu pobiera plik`Chart` obiekt z kształtu, który właśnie wprowadziliśmy.

## Krok 4: Dodaj dane serii do wykresu

Czas teraz dodać trochę danych do naszego wykresu. Dodamy serię z datami i odpowiadającymi im wartościami.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

tym kroku dodajemy serię o nazwie „Aspose Series 1” z zestawem dat i odpowiadających im wartości.

## Krok 5: Zapisz dokument

Na koniec zapiszemy nasz dokument z wstawionym wykresem warstwowym.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Ta linia kodu zapisuje dokument w określonym katalogu z podaną nazwą pliku.

## Wniosek

Gratulacje! Pomyślnie wstawiłeś wykres warstwowy do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Ten przewodnik poprowadził Cię przez każdy etap, od skonfigurowania środowiska po zapisanie ostatecznego dokumentu. Dzięki Aspose.Words dla .NET możesz tworzyć szeroką gamę wykresów i innych złożonych elementów w dokumentach programu Word, dzięki czemu Twoje raporty i prezentacje będą bardziej dynamiczne i pouczające.

## Często zadawane pytania

### Czy mogę używać Aspose.Words dla .NET z innymi językami .NET?
Tak, Aspose.Words dla .NET obsługuje inne języki .NET, takie jak VB.NET.

### Czy można dostosować wygląd wykresu?
Absolutnie! Aspose.Words dla .NET zapewnia rozbudowane opcje dostosowywania wyglądu wykresów.

### Czy mogę dodać wiele wykresów do jednego dokumentu programu Word?
Tak, możesz wstawić dowolną liczbę wykresów do jednego dokumentu programu Word.

### Czy Aspose.Words dla .NET obsługuje inne typy wykresów?
Tak, Aspose.Words dla .NET obsługuje różne typy wykresów, w tym słupkowe, liniowe, kołowe i inne.

### Gdzie mogę uzyskać tymczasową licencję na Aspose.Words dla .NET?
 Licencję tymczasową można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).