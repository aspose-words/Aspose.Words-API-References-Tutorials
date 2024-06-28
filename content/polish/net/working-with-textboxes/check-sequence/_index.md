---
title: Sprawdź sekwencję
linktitle: Sprawdź sekwencję
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak sprawdzić kolejność pól tekstowych w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-textboxes/check-sequence/
---
Ten przewodnik krok po kroku wyjaśnia, jak sprawdzić kolejność pól tekstowych w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla platformy .NET. Dowiesz się jak skonfigurować dokument, stworzyć kształt TextBox, uzyskać dostęp do TextBoxów i sprawdzić ich położenie w sekwencji.

## Krok 1: Konfigurowanie dokumentu i tworzenie kształtu TextBox

 Na początek musimy skonfigurować dokument i utworzyć kształt TextBox. Poniższy kod inicjuje nowe wystąpienie`Document` class i tworzy kształt pola tekstowego:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Krok 2: Sprawdzanie sekwencji TextBox

 Sprawdzimy teraz sekwencję pola tekstowego za pomocą`if` warunki. Dostarczony kod źródłowy zawiera trzy oddzielne warunki umożliwiające sprawdzenie położenia TextBox względem poprzednich i kolejnych kształtów.

## Krok 3: Sprawdzanie głowicy sekwencji:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Jeśli TextBox ma następny kształt (`Next`), ale bez poprzedniego kształtu (`Previous`), co oznacza, że jest głową sekwencji. Wyświetli się komunikat „Nagłówek sekwencji”.

## Krok 4: Sprawdzanie środka sekwencji:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Jeśli TextBox ma zarówno kształt Następny (`Next`) i Poprzedni kształt (`Previous`), oznacza to, że znajduje się w środku sekwencji. Wyświetli się komunikat „Środek sekwencji”.

## Krok 5: Weryfikacja końca ciągu:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Jeśli TextBox nie ma następnego kształtu (`Next`), ale ma poprzedni kształt (`Previous`), czyli jest to koniec sekwencji. Wyświetli się komunikat „Koniec sekwencji”.

### Przykładowy kod źródłowy do weryfikacji sekwencji za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

## Wniosek

Gratulacje! Teraz wiesz, jak sprawdzić kolejność pól tekstowych w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla platformy .NET. Wykonując kroki opisane w tym przewodniku, udało Ci się skonfigurować dokument, utworzyć kształt TextBox i sprawdzić, czy znajduje się on na początku, w środku czy na końcu sekwencji.

### Często zadawane pytania dotyczące sprawdzania sekwencji

#### P: Jaka jest biblioteka używana do sprawdzania sekwencji pól tekstowych przy użyciu Aspose.Words dla .NET?

Odp.: Aby sprawdzić sekwencję pól tekstowych przy użyciu Aspose.Words dla .NET, używaną biblioteką jest Aspose.Words dla .NET.

#### P: Jak ustalić, czy TextBox jest nagłówkiem sekwencji?

O: Aby ustalić, czy TextBox jest nagłówkiem sekwencji, możesz sprawdzić, czy ma następną formę (`Next`), ale nie poprzednia forma (`Previous`). Jeśli tak, oznacza to, że jest głową serii.

#### P: Jak sprawdzić, czy TextBox znajduje się w środku sekwencji?

Odp.: Aby ustalić, czy TextBox znajduje się w środku sekwencji, musisz sprawdzić, czy ma oba kolejne kształty (`Next`) i poprzedni kształt (`Previous`). Jeśli tak, oznacza to, że znajduje się w środku sekwencji.

#### P: Jak sprawdzić, czy TextBox jest końcem sekwencji?

O: Aby sprawdzić, czy TextBox jest końcem sekwencji, możesz sprawdzić, czy nie ma on następnej formy (`Next`), ale ma poprzednią formę (`Previous`). Jeśli tak, oznacza to koniec sekwencji.

#### P: Czy możemy sprawdzić sekwencję elementów innych niż TextBoxy?

O: Tak, używając biblioteki Aspose.Words dla .NET, możliwe jest sprawdzenie sekwencji innych elementów, takich jak akapity, tabele, obrazy itp. Proces będzie się różnić w zależności od konkretnego elementu, który chcesz sprawdzić.
