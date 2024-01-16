---
title: Przerwij łącze do przodu w dokumencie programu Word
linktitle: Przerwij łącze do przodu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łamać łącza do przodu w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-textboxes/break-a-link/
---

Aspose.Words dla .NET to potężna biblioteka oferująca różne funkcje programowego przetwarzania słów z dokumentami Microsoft Word. Jedną z jego przydatnych funkcji jest możliwość dzielenia linków do przodu w dokumencie Word. W tym samouczku przyjrzymy się kodowi źródłowemu w języku C#, który demonstruje, jak przerwać łącze do przodu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

## Krok 1: Podgląd kodu źródłowego C#

Dostarczony kod źródłowy C# skupia się na funkcji „Przerwij łącze” w Aspose.Words dla .NET. Pokazuje, jak przerwać łącze w kształcie TextBox wewnątrz dokumentu. Kod przedstawia różne scenariusze zrywania linków i dostarcza jasnych instrukcji, jak osiągnąć pożądane rezultaty.

## Krok 2: Konfigurowanie dokumentu i tworzenie kształtu TextBox

 Na początek musimy skonfigurować dokument i utworzyć kształt TextBox. Poniższy kod inicjuje nowe wystąpienie`Document` class i tworzy kształt pola tekstowego:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Krok 3: Przerwij łącze do przodu w polu tekstowym

 Aby przerwać łącze do przodu w polu tekstowym, możemy użyć metody`BreakForwardLink()` metoda. Ta metoda przerywa łącze do następnego kształtu w sekwencji. Poniższy kod pokazuje, jak przerwać łącze przekierowujące:

```csharp
textBox.BreakForwardLink();
```

## Krok 4: Przerwij łącze przekierowujące, ustawiając wartość null

 Alternatywnie możemy przerwać łącze do przodu, ustawiając pola tekstowe`Next`własność do`null`. To skutecznie usuwa połączenie z następnym kształtem. Poniższy kod demonstruje to podejście:

```csharp
textBox. Next = null;
```

## Krok 5: Przerwij łącze prowadzące do pola tekstowego

 W niektórych przypadkach musimy przerwać łącze prowadzące do kształtu TextBox. Możemy to osiągnąć dzwoniąc do`BreakForwardLink()` metoda na`Previous` formularz, który przerywa łącze do TextBox. Oto przykład, jak przerwać takie łącze:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Przykładowy kod źródłowy umożliwiający zerwanie łącza za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Przerwij łącze do przodu.
textBox.BreakForwardLink();

// Przerwij łącze przekierowujące, ustawiając wartość null.
textBox. Next = null;

// Przerwij łącze prowadzące do tego pola tekstowego.
textBox.Previous?.BreakForwardLink();
```

## Wniosek

Gratulacje! Nauczyłeś się teraz, jak łamać linki przekierowujące w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla .NET. Wykonując kroki opisane w tym przewodniku, udało Ci się skonfigurować dokument, utworzyć kształt TextBox i rozbić linki przekierowujące przy użyciu różnych metod.

### Często zadawane pytania dotyczące łącza do przesyłania dalej w dokumencie programu Word

#### P: Jaka jest biblioteka używana do przerywania linków przekierowujących w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby przerwać łącza przekierowania w dokumencie programu Word przy użyciu Aspose.Words dla .NET, używana jest biblioteka Aspose.Words dla .NET.

#### P: Jak przerwać link przekierowujący w polu tekstowym?

 Odp.: Aby przerwać łącze do przodu w polu tekstowym, możesz użyć metody`BreakForwardLink()` metoda. Ta metoda przerywa łącze do następnego kształtu w sekwencji.

#### P: Jak przerwać link przekierowujący, ustawiając wartość null?

Odp.: Alternatywnie możesz przerwać link przekierowujący, ustawiając opcję`Next` właściwość TextBox do`null`. To skutecznie usuwa połączenie z następnym kształtem.

#### P: Jak przerwać łącze prowadzące do pola tekstowego?

 Odp.: W niektórych przypadkach trzeba przerwać łącze prowadzące do pola tekstowego. Można to osiągnąć dzwoniąc pod numer`BreakForwardLink()` metoda na`Previous` formularz, który przerywa łącze do TextBox.

#### P: Czy możemy przerwać linki przekierowujące na elementach innych niż TextBox?

Odp.: Tak, dzięki Aspose.Words dla .NET możliwe jest przerwanie linków przekierowujących na różne elementy, takie jak akapity, tabele, obrazy itp. Proces może się różnić w zależności od konkretnego elementu, dla którego chcesz przerwać łącze.