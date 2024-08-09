---
title: Przekreślenie
linktitle: Przekreślenie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zastosować formatowanie przekreślone do tekstu za pomocą Aspose.Words dla .NET, korzystając z naszego przewodnika krok po kroku. Zwiększ swoje umiejętności przetwarzania dokumentów.
type: docs
weight: 10
url: /pl/net/working-with-markdown/strikethrough/
---
## Wstęp

Witamy w tym szczegółowym przewodniku na temat stosowania formatowania przekreślonego do tekstu za pomocą Aspose.Words dla .NET. Jeśli chcesz udoskonalić swoje umiejętności przetwarzania dokumentów i nadać tekstowi niepowtarzalny charakter, jesteś we właściwym miejscu. Zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

-  Aspose.Words dla .NET: Pobierz[Tutaj](https://releases.aspose.com/words/net/).
- .NET Framework: Upewnij się, że masz zainstalowaną platformę .NET Framework w swoim systemie.
- Środowisko programistyczne: IDE takie jak Visual Studio.
- Podstawowa znajomość języka C#: Konieczna jest znajomość programowania w języku C#.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw. Są one niezbędne do uzyskania dostępu do biblioteki Aspose.Words i jej funkcji.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Zainicjuj narzędzie DocumentBuilder

 The`DocumentBuilder` class to potężne narzędzie w Aspose.Words, które pozwala z łatwością dodawać treść do dokumentu.

```csharp
// Zainicjuj narzędzie DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Ustaw właściwość przekreślenia

Teraz zastosujmy właściwość przekreślenia do naszego tekstu. Wiąże się to z ustawieniem`StrikeThrough` własność`Font` oponować`true`.

```csharp
// Zrób przekreślenie tekstu.
builder.Font.StrikeThrough = true;
```

## Krok 3: Napisz tekst przekreśleniem

 Po ustawieniu właściwości przekreślenia możemy teraz dodać nasz tekst. The`Writeln` metoda doda tekst do dokumentu.

```csharp
// Wpisz tekst za pomocą przekreślenia.
builder.Writeln("This text will be StrikeThrough");
```

## Wniosek

I masz to! Pomyślnie dodałeś przekreślenie do swojego tekstu przy użyciu Aspose.Words dla .NET. Ta potężna biblioteka otwiera świat możliwości przetwarzania i dostosowywania dokumentów. Niezależnie od tego, czy tworzysz raporty, listy, czy inny rodzaj dokumentów, opanowanie tych funkcji niewątpliwie zwiększy Twoją produktywność i jakość wyników.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do przetwarzania dokumentów, która umożliwia programistom programowe tworzenie, manipulowanie i konwertowanie dokumentów programu Word.

### Czy mogę używać Aspose.Words dla .NET w projekcie komercyjnym?
 Tak, możesz używać Aspose.Words dla .NET w projektach komercyjnych. Aby zapoznać się z opcjami zakupu, odwiedź stronę[kup stronę](https://purchase.aspose.com/buy).

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Jak uzyskać wsparcie dla Aspose.Words dla .NET?
Możesz uzyskać wsparcie od społeczności Aspose i ekspertów ds[forum wsparcia](https://forum.aspose.com/c/words/8).

### Czy mogę zastosować inne opcje formatowania tekstu za pomocą Aspose.Words dla .NET?
Absolutnie! Aspose.Words dla .NET obsługuje szeroką gamę opcji formatowania tekstu, w tym pogrubienie, kursywę, podkreślenie i inne.