---
title: Ustaw domyślne opcje etykiet danych na wykresie
linktitle: Ustaw domyślne opcje etykiet danych na wykresie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić domyślne opcje etykiet danych na wykresie za pomocą Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby bez wysiłku tworzyć i dostosowywać wykresy.
type: docs
weight: 10
url: /pl/net/programming-with-charts/default-options-for-data-labels/
---
## Wstęp

Hej tam! Czy jesteś podekscytowany zanurzeniem się w świat automatyzacji dokumentów? Dzisiaj przyjrzymy się, jak używać Aspose.Words dla .NET do programowego tworzenia wspaniałych dokumentów. Aspose.Words to potężna biblioteka, która pozwala z łatwością manipulować dokumentami programu Word. W tym samouczku skupimy się na ustawianiu domyślnych opcji etykiet danych na wykresie. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, ten przewodnik przeprowadzi Cię przez każdy krok, dzięki czemu możesz błyskawicznie rozpocząć pracę.

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz, wraz z tym samouczkiem. Oto krótka lista kontrolna:

- Visual Studio lub inne IDE kompatybilne z .NET: tutaj będziesz pisać i uruchamiać swój kod.
-  Aspose.Words dla .NET: Można[pobierz najnowszą wersję](https://releases.aspose.com/words/net/) i zainstaluj go w swoim projekcie.
- Podstawowa znajomość programowania w języku C#: Chociaż ten przewodnik jest przyjazny dla początkujących, pomocna będzie niewielka znajomość języka C#.
- Zainstalowano platformę .NET Framework: Upewnij się, że na komputerze skonfigurowano platformę .NET Framework.
-  Tymczasowa licencja na Aspose.Words: Zdobądź ją[Tutaj](https://purchase.aspose.com/temporary-license/) aby odblokować pełną funkcjonalność.

Po ustaleniu tych wymagań wstępnych jesteśmy gotowi do działania!

## Importuj przestrzenie nazw

Na początek skonfigurujmy nasz projekt i zaimportujmy niezbędne przestrzenie nazw. Te przestrzenie nazw są kluczowe dla dostępu do funkcjonalności Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Krok 1: Utwórz nowy dokument


 Podróż rozpoczyna się od utworzenia nowego dokumentu i zainicjowania pliku`DocumentBuilder` . The`DocumentBuilder` class udostępnia zestaw metod umożliwiających łatwe manipulowanie zawartością dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument
Document doc = new Document();

// Zainicjuj program DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Wyjaśnienie

 Na tym etapie konfigurujemy dokument i kreator, którego będziemy używać do wstawiania i formatowania naszej treści. The`dataDir` zmienna zawiera ścieżkę, w której zapiszemy nasz dokument końcowy.

## Krok 2: Wstaw wykres

 Następnie dodamy wykres kołowy do naszego dokumentu. The`InsertChart` metoda`DocumentBuilder` klasa sprawia, że jest to bardzo łatwe.

```csharp
// Wstaw wykres kołowy
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Uzyskaj dostęp do obiektu wykresu
Chart chart = shape.Chart;
```

### Wyjaśnienie

Tutaj wstawiamy wykres kołowy do naszego dokumentu. The`InsertChart` Metoda wymaga parametrów typu, szerokości i wysokości wykresu. Po wstawieniu wykresu uzyskujemy dostęp do obiektu wykresu w celu dalszej manipulacji nim.

## Krok 3: Dostosuj serię wykresów

Teraz wyczyścimy wszystkie istniejące serie na wykresie i dodamy serię niestandardową. Ta seria będzie reprezentować nasze punkty danych.

```csharp
// Wyczyść istniejącą serię wykresów
chart.Series.Clear();

// Dodaj nową serię do wykresu
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Wyjaśnienie

Na tym etapie upewniamy się, że nasz wykres jest pusty, usuwając wszelkie istniejące serie. Następnie dodajemy nową serię z niestandardowymi kategoriami i wartościami, które zostaną wyświetlone na naszym wykresie kołowym.

## Krok 4: Ustaw domyślne opcje etykiet danych

Etykiety danych mają kluczowe znaczenie, jeśli chcesz, aby wykres był informacyjny. Ustawimy opcje wyświetlania procentu, wartości i dostosowania separatora.

```csharp
// Uzyskaj dostęp do kolekcji etykiet danych
ChartDataLabelCollection labels = series.DataLabels;

// Ustaw opcje etykiet danych
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Wyjaśnienie

 Tutaj mamy dostęp do`DataLabels`właściwość naszej serii umożliwiająca dostosowanie wyglądu i informacji wyświetlanych na każdej etykiecie danych. Zdecydowaliśmy się pokazać zarówno wartość procentową, jak i wartość, ukryć linie odniesienia i ustawić niestandardowy separator.

## Krok 5: Zapisz dokument

Na koniec zapiszemy nasz dokument we wskazanym katalogu. Ten krok gwarantuje, że wszystkie nasze zmiany zostaną zapisane do pliku.

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Wyjaśnienie

 W tym ostatnim kroku zapisujemy nasz dokument za pomocą pliku`Save` metoda. Dokument zostanie zapisany w katalogu wskazanym przez`dataDir`, o nazwie „WorkingWithCharts.DefaultOptionsForDataLabels.docx”.

## Wniosek

I masz to! Pomyślnie utworzyłeś dokument programu Word z dostosowanym wykresem kołowym przy użyciu Aspose.Words dla .NET. Ta potężna biblioteka ułatwia automatyzację tworzenia i manipulowania dokumentami, oszczędzając czas i wysiłek. Niezależnie od tego, czy generujesz raporty, faktury, czy jakikolwiek inny typ dokumentu, Aspose.Words zapewni Ci wsparcie.

 Zapraszamy do eksploracji[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/) aby uzyskać więcej funkcji i przykładów. Miłego kodowania!

## Często zadawane pytania

### Czy mogę używać Aspose.Words za darmo?
Możesz używać Aspose.Words za darmo z[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) lub poznaj jego funkcje za pomocą[bezpłatna wersja próbna](https://releases.aspose.com/).

### Jak uzyskać wsparcie dla Aspose.Words?
 Wsparcie możesz uzyskać poprzez[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8).

### Czy mogę dodać inne typy wykresów?
 Tak, Aspose.Words obsługuje różne typy wykresów, takie jak wykresy słupkowe, liniowe i kolumnowe. Sprawdź[dokumentacja](https://reference.aspose.com/words/net/) aby uzyskać więcej szczegółów.

### Czy Aspose.Words jest kompatybilny z .NET Core?
 Tak, Aspose.Words jest kompatybilny z .NET Core. Więcej informacji znajdziesz w[dokumentacja](https://reference.aspose.com/words/net/).

### Jak mogę kupić licencję na Aspose.Words?
 Licencję można kupić w witrynie[Sklep Aspose](https://purchase.aspose.com/buy).

