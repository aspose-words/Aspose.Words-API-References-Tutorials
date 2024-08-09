---
title: Uruchom ponownie numer listy
linktitle: Uruchom ponownie numer listy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ponownie uruchomić numery list w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Ten szczegółowy przewodnik zawierający 2000 słów zawiera wszystko, co musisz wiedzieć, od konfiguracji po zaawansowaną personalizację.
type: docs
weight: 10
url: /pl/net/working-with-list/restart-list-number/
---
## Wstęp

Czy chcesz opanować sztukę manipulacji listami w dokumentach programu Word przy użyciu Aspose.Words dla .NET? Cóż, jesteś we właściwym miejscu! W tym samouczku szczegółowo omówimy ponowne uruchamianie numerów list — fajną funkcję, która przeniesie Twoje umiejętności automatyzacji dokumentów na wyższy poziom. Zapnij pasy i zaczynajmy!

## Warunki wstępne

Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.Words dla .NET: Musisz mieć zainstalowany Aspose.Words dla .NET. Jeśli jeszcze go nie zainstalowałeś, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: upewnij się, że masz odpowiednie środowisko programistyczne, takie jak Visual Studio.
3. Podstawowa znajomość języka C#: Podstawowa znajomość języka C# pomoże Ci śledzić tutorial.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Są one niezbędne do uzyskania dostępu do funkcji Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Podzielmy teraz proces na łatwe do wykonania kroki. Omówimy wszystko, od utworzenia listy po ponowne rozpoczęcie jej numeracji.

## Krok 1: Skonfiguruj dokument i kreator

Zanim zaczniesz manipulować listami, potrzebujesz dokumentu i narzędzia DocumentBuilder. DocumentBuilder to podstawowe narzędzie umożliwiające dodawanie treści do dokumentu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Utwórz i dostosuj swoją pierwszą listę

Następnie utworzymy listę na podstawie szablonu i dostosujemy jej wygląd. W tym przykładzie używamy formatu liczb arabskich z nawiasami.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Tutaj ustawiliśmy kolor czcionki na czerwony i wyrównaliśmy tekst do prawej strony.

## Krok 3: Dodaj pozycje do swojej pierwszej listy

 Gdy lista jest już gotowa, czas dodać kilka elementów. Konstruktor dokumentów`ListFormat.List` Właściwość pomaga w zastosowaniu formatu listy do tekstu.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 4: Uruchom ponownie numerację list

Aby ponownie wykorzystać listę i wznowić jej numerację, należy utworzyć kopię oryginalnej listy. Dzięki temu możesz niezależnie modyfikować nową listę.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

W tym przykładzie nowa lista zaczyna się od numeru 10.

## Krok 5: Dodaj pozycje do nowej listy

Podobnie jak poprzednio, dodaj pozycje do nowej listy. To pokazuje, że lista rozpoczyna się ponownie od określonego numeru.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Krok 6: Zapisz swój dokument

Na koniec zapisz dokument w określonym katalogu.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Wniosek

Ponowne uruchamianie numerów list w dokumentach programu Word za pomocą Aspose.Words dla .NET jest proste i niezwykle przydatne. Niezależnie od tego, czy generujesz raporty, tworzysz dokumenty o określonej strukturze, czy po prostu potrzebujesz lepszej kontroli nad swoimi listami, ta technika Ci pomoże.

## Często zadawane pytania

### Czy mogę używać innych szablonów list oprócz NumberArabicParenthesis?

Absolutnie! Aspose.Words oferuje różne szablony list, takie jak punktory, litery, cyfry rzymskie i inne. Możesz wybrać ten, który najlepiej odpowiada Twoim potrzebom.

### Jak zmienić poziom listy?

 Możesz zmienić poziom listy, modyfikując plik`ListLevels` nieruchomość. Na przykład,`list1.ListLevels[1]` odnosiłoby się do drugiego poziomu listy.

### Czy mogę wznowić numerację od dowolnego numeru?

 Tak, możesz ustawić liczbę początkową na dowolną wartość całkowitą za pomocą`StartAt` właściwość poziomu listy.

### Czy możliwe jest różne formatowanie dla różnych poziomów list?

Rzeczywiście! Każdy poziom listy może mieć własne ustawienia formatowania, takie jak czcionka, wyrównanie i styl numeracji.

### Co się stanie, jeśli zamiast zaczynać od nowa, będę chciał kontynuować numerację z poprzedniej listy?

Jeśli chcesz kontynuować numerację, nie musisz tworzyć kopii listy. Po prostu kontynuuj dodawanie elementów do oryginalnej listy.


