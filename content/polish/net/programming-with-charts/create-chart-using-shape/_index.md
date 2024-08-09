---
title: Utwórz i dostosuj wykres za pomocą kształtu
linktitle: Utwórz i dostosuj wykres za pomocą kształtu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć i dostosowywać wykresy w dokumentach programu Word za pomocą Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku. Idealny do wizualizacji danych.
type: docs
weight: 10
url: /pl/net/programming-with-charts/create-chart-using-shape/
---
## Wstęp

Tworzenie i dostosowywanie wykresów w dokumentach to kluczowa umiejętność w dzisiejszym świecie opartym na danych. Wykresy mogą pomóc w wizualizacji danych, dzięki czemu złożone informacje stają się bardziej zrozumiałe. Aspose.Words dla .NET to potężna biblioteka, która pozwala programowo tworzyć dokumenty Word i manipulować nimi. W tym samouczku przeprowadzimy Cię przez proces tworzenia i dostosowywania wykresu liniowego za pomocą Aspose.Words dla .NET. Po przeczytaniu tego przewodnika będziesz w stanie z łatwością tworzyć profesjonalnie wyglądające wykresy.

## Warunki wstępne

Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

-  Biblioteka Aspose.Words dla .NET: Możesz ją pobrać[Tutaj](https://releases.aspose.com/words/net/).
- Visual Studio: dowolna wersja obsługująca platformę .NET.
- Podstawowa znajomość języka C#: Zrozumienie podstaw języka C# pomoże ci postępować zgodnie z samouczkiem.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw. Ten krok jest niezbędny, ponieważ pozwala na użycie klas i metod dostarczonych przez Aspose.Words dla .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Krok 1: Utwórz nowy dokument

Najpierw musisz utworzyć nowy dokument Word. Dokument ten posłuży jako płótno dla Twojego wykresu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw wykres

 Następnie wstawisz do dokumentu wykres liniowy. The`DocumentBuilder.InsertChart` W tym celu stosuje się metodę.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Dostosuj tytuł wykresu

Dostosowanie tytułu wykresu może pomóc w zapewnieniu kontekstu wyświetlanych danych. Możesz wyświetlić tytuł i ustawić jego tekst za pomocą następującego kodu:

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
// Należy pamiętać, że jeśli jako tekst tytułu zostanie określona wartość null lub pusta, wyświetlony zostanie tytuł wygenerowany automatycznie.
```

## Krok 4: Dostosuj pozycję legendy

Legenda pomaga zidentyfikować różne serie danych na wykresie. Możesz dostosować jego położenie i ustawienia nakładki w następujący sposób:

```csharp
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Krok 5: Zapisz dokument

Na koniec musisz zapisać dokument. Ten krok gwarantuje, że wszystkie zmiany zostaną zapisane w pliku.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

## Wniosek

W tym samouczku omówiliśmy, jak utworzyć i dostosować wykres liniowy w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz teraz tworzyć atrakcyjne wizualnie wykresy, które skutecznie komunikują Twoje dane. Aspose.Words dla .NET oferuje szeroką gamę opcji dostosowywania, umożliwiając dostosowanie wykresów do Twoich konkretnych potrzeb.

## Często zadawane pytania

### Czy mogę używać Aspose.Words dla .NET do tworzenia wykresów innego typu?

 Tak, Aspose.Words dla .NET obsługuje różne typy wykresów, w tym wykresy słupkowe, wykresy kołowe i inne. Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/words/net/) aby uzyskać więcej szczegółów.

### Jak mogę wypróbować Aspose.Words dla .NET przed zakupem?

 Możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/). Dzięki temu możesz przetestować bibliotekę i jej funkcje przed dokonaniem zakupu.

### Czy istnieje sposób na uzyskanie wsparcia w przypadku napotkania problemów?

 Absolutnie. Dostęp do pomocy technicznej można uzyskać za pośrednictwem forów społeczności Aspose[Tutaj](https://forum.aspose.com/c/words/8)Społeczność i pracownicy Aspose reagują bardzo szybko.

### Jak kupić licencję na Aspose.Words dla .NET?

 Możesz kupić licencję bezpośrednio na stronie Aspose[Tutaj](https://purchase.aspose.com/buy). Istnieją różne opcje licencjonowania dostosowane do różnych potrzeb.

### Co jeśli potrzebuję tymczasowej licencji na projekt krótkoterminowy?

 Aspose oferuje licencje tymczasowe, o które możesz poprosić[Tutaj](https://purchase.aspose.com/temporary-license/).
