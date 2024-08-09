---
title: Format linii poziomej w dokumencie programu Word
linktitle: Format linii poziomej w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać konfigurowalne linie poziome w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Zwiększ automatyzację dokumentów.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## Wstęp

W środowisku programowania .NET programowe manipulowanie i formatowanie dokumentów programu Word może być trudnym zadaniem. Na szczęście Aspose.Words dla .NET zapewnia solidne rozwiązanie, umożliwiające programistom łatwą automatyzację tworzenia, edytowania i zarządzania dokumentami. W tym artykule omówiono jedną z podstawowych funkcji: wstawianie poziomych linii do dokumentów programu Word. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz z Aspose.Words, opanowanie tej możliwości usprawni proces generowania dokumentów.

## Warunki wstępne

Zanim zaczniesz wdrażać reguły horyzontalne przy użyciu Aspose.Words dla .NET, upewnij się, że spełniasz następujące wymagania wstępne:

- Visual Studio: Zainstaluj Visual Studio IDE do programowania .NET.
- Aspose.Words dla .NET: Pobierz i zainstaluj Aspose.Words dla .NET z[Tutaj](https://releases.aspose.com/words/net/).
- Podstawowa znajomość języka C#: Znajomość podstaw języka programowania C#.
-  Klasa DocumentBuilder: Zrozumienie`DocumentBuilder` klasa w Aspose.Words do manipulacji dokumentami.

## Importuj przestrzenie nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Words;
using System.Drawing;
```

Te przestrzenie nazw zapewniają dostęp do klas Aspose.Words do manipulowania dokumentami i standardowych klas .NET do obsługi kolorów.

Podzielmy proces dodawania linii poziomej w dokumencie programu Word za pomocą Aspose.Words dla .NET na kompleksowe kroki:

## Krok 1: Zainicjuj DocumentBuilder i ustaw katalog

 Najpierw zainicjuj a`DocumentBuilder` obiekt i ustaw ścieżkę katalogu, w którym dokument zostanie zapisany.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Wstaw linię poziomą

 Skorzystaj z`InsertHorizontalRule()` metoda`DocumentBuilder` class, aby dodać linię poziomą.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## Krok 3: Dostosuj format linii poziomej

 Uzyskaj dostęp do`HorizontalRuleFormat` właściwość wstawionego kształtu, aby dostosować wygląd linii poziomej.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- Wyrównanie: Określa wyrównanie linii poziomej (`HorizontalRuleAlignment.Center` w tym przykładzie).
- SzerokośćPercent: Ustawia szerokość linii poziomej jako procent szerokości strony (w tym przykładzie 70%).
- Wysokość: Określa wysokość linii poziomej w punktach (w tym przykładzie 3 punkty).
- Kolor: Ustawia kolor linii poziomej (`Color.Blue` w tym przykładzie).
- NoShade: Określa, czy linia pozioma powinna mieć cień (`true` w tym przykładzie).

## Krok 4: Zapisz dokument

 Na koniec zapisz zmodyfikowany dokument za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## Wniosek

Opanowanie wstawiania linii poziomych w dokumentach Word przy użyciu Aspose.Words dla .NET zwiększa możliwości automatyzacji dokumentów. Wykorzystując elastyczność i możliwości Aspose.Words, programiści mogą efektywnie usprawnić procesy generowania i formatowania dokumentów.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowej pracy z dokumentami Word w aplikacjach .NET.

### Jak mogę pobrać Aspose.Words dla .NET?
 Możesz pobrać Aspose.Words dla .NET z[Tutaj](https://releases.aspose.com/words/net/).

### Czy mogę dostosować wygląd linii poziomych w Aspose.Words?
Tak, możesz dostosować różne aspekty, takie jak wyrównanie, szerokość, wysokość, kolor i cieniowanie linii poziomych, używając Aspose.Words.

### Czy Aspose.Words nadaje się do przetwarzania dokumentów na poziomie przedsiębiorstwa?
Tak, Aspose.Words jest szeroko stosowany w środowiskach korporacyjnych ze względu na jego niezawodne możliwości manipulowania dokumentami.

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Words dla .NET?
 Aby uzyskać wsparcie i zaangażowanie społeczności, odwiedź stronę[Forum Aspose.Words](https://forum.aspose.com/c/words/8).
