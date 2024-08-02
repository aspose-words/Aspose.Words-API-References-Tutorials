---
title: Dodaj tekstowy znak wodny z określonymi opcjami
linktitle: Dodaj tekstowy znak wodny z określonymi opcjami
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać tekstowy znak wodny z określonymi opcjami do dokumentów programu Word przy użyciu Aspose.Words dla .NET. Z łatwością dostosuj czcionkę, rozmiar, kolor i układ.
type: docs
weight: 10
url: /pl/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## Wstęp

Znaki wodne mogą być stylowym i funkcjonalnym dodatkiem do dokumentów programu Word, służącym do oznaczania dokumentów jako poufnych lub dodawania spersonalizowanego charakteru. W tym samouczku omówimy, jak dodać tekstowy znak wodny do dokumentu programu Word za pomocą Aspose.Words dla .NET. Zagłębimy się w konkretne opcje, które możesz skonfigurować, takie jak rodzina czcionek, rozmiar czcionki, kolor i układ. Na koniec będziesz mógł dostosować znak wodny swojego dokumentu tak, aby dokładnie odpowiadał Twoim potrzebom. Więc chwyć edytor kodu i zaczynajmy!

## Warunki wstępne

Zanim zaczniemy działać, upewnij się, że masz następujące elementy:

1.  Biblioteka Aspose.Words dla .NET: Będziesz potrzebować zainstalowanej biblioteki Aspose.Words. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go ze strony[Link do pobrania Aspose.Words](https://releases.aspose.com/words/net/).
2. Podstawowa znajomość języka C#: W tym samouczku używany będzie język C# jako język programowania. Pomocna będzie podstawowa znajomość składni języka C#.
3. Środowisko programistyczne .NET: Upewnij się, że masz skonfigurowane środowisko programistyczne (takie jak Visual Studio), w którym możesz tworzyć i uruchamiać aplikacje .NET.

## Importuj przestrzenie nazw

Aby pracować z Aspose.Words, musisz uwzględnić w swoim projekcie niezbędne przestrzenie nazw. Oto, co musisz zaimportować:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Krok 1: Skonfiguruj swój dokument

 Najpierw musisz załadować dokument, z którym chcesz pracować. W tym samouczku użyjemy przykładowego dokumentu o nazwie`Document.docx`. Upewnij się, że ten dokument istnieje w określonym katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Na tym etapie definiujesz katalog, w którym znajduje się dokument, i ładujesz go do instancji pliku`Document` klasa.

## Krok 2: Skonfiguruj opcje znaku wodnego

Następnie skonfiguruj opcje tekstowego znaku wodnego. Możesz dostosować różne aspekty, takie jak rodzina czcionek, rozmiar czcionki, kolor i układ. Skonfigurujmy te opcje.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Oto, co robi każda opcja:
- `FontFamily`: Określa czcionkę tekstu znaku wodnego.
- `FontSize`: Ustawia rozmiar tekstu znaku wodnego.
- `Color`: Określa kolor tekstu znaku wodnego.
- `Layout`Określa orientację znaku wodnego (poziomo lub ukośnie).
- `IsSemitrasparent`: Określa, czy znak wodny ma być półprzezroczysty.

## Krok 3: Dodaj tekst znaku wodnego

Teraz zastosuj znak wodny do swojego dokumentu, korzystając z wcześniej skonfigurowanych opcji. W tym kroku ustawisz tekst znaku wodnego na „Test” i zastosujesz zdefiniowane opcje.

```csharp
doc.Watermark.SetText("Test", options);
```

Ta linia kodu dodaje do dokumentu znak wodny z tekstem „Test”, stosując określone opcje.

## Krok 4: Zapisz dokument

Na koniec zapisz dokument z zastosowanym nowym znakiem wodnym. Możesz zapisać go pod nową nazwą, aby uniknąć nadpisania oryginalnego dokumentu.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Ten fragment kodu zapisuje zmodyfikowany dokument w tym samym katalogu z nową nazwą pliku.

## Wniosek

Dodawanie tekstowego znaku wodnego do dokumentów programu Word za pomocą Aspose.Words dla .NET jest prostym procesem, jeśli podzielisz go na łatwe do wykonania kroki. Wykonując ten samouczek, nauczyłeś się konfigurować różne opcje znaku wodnego, w tym czcionkę, rozmiar, kolor, układ i przezroczystość. Dzięki tym umiejętnościom możesz teraz dostosować swoje dokumenty tak, aby lepiej odpowiadały Twoim potrzebom lub zawierały istotne informacje, takie jak poufność lub branding.

 Jeśli masz jakieś pytania lub potrzebujesz dalszej pomocy, nie wahaj się sprawdzić[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/) lub odwiedź[Forum wsparcia Aspose](https://forum.aspose.com/c/words/8) aby uzyskać dodatkową pomoc.

## Często zadawane pytania

### Czy mogę użyć różnych czcionek w znaku wodnym?

 Tak, możesz wybrać dowolną czcionkę zainstalowaną w systemie, określając`FontFamily` nieruchomość w`TextWatermarkOptions`.

### Jak zmienić kolor znaku wodnego?

 Możesz zmienić kolor znaku wodnego, ustawiając opcję`Color` nieruchomość w`TextWatermarkOptions` do każdego`System.Drawing.Color` wartość.

### Czy można dodać wiele znaków wodnych do dokumentu?

Aspose.Words obsługuje dodawanie jednego znaku wodnego na raz. Aby dodać wiele znaków wodnych, należy je utworzyć i zastosować sekwencyjnie.

### Czy mogę dostosować położenie znaku wodnego?

 The`WatermarkLayout`Właściwość określa orientację, ale dokładne dostosowania pozycjonowania nie są obsługiwane bezpośrednio. Dokładne umiejscowienie może wymagać zastosowania innych technik.

### A co jeśli potrzebuję półprzezroczystego znaku wodnego?

 Ustaw`IsSemitrasparent`własność do`true` aby Twój znak wodny był półprzezroczysty.