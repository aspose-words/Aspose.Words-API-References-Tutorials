---
title: Przejdź, aby scalić pole w dokumencie programu Word
linktitle: Przejdź, aby scalić pole w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zaimplementować funkcję Przenieś do pola scalania w dokumencie tekstowym Aspose.Words dla .NET, korzystając z przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/move-to-merge-field/
---
tym przykładzie omówimy funkcję Przenieś do pola scalania w dokumencie programu Word w Aspose.Words dla .NET. Aspose.Words to potężna biblioteka do manipulacji dokumentami, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word. Funkcja Przenieś do pola scalania pozwala nam nawigować w celu scalania pól w dokumencie i wykonywać na nich różne operacje.


## Wyjaśnienie kodu źródłowego krok po kroku

Przejrzyjmy kod źródłowy krok po kroku, aby zrozumieć, jak korzystać z funkcji Przenieś do pola scalania przy użyciu Aspose.Words dla .NET.

## Krok 1: Inicjowanie dokumentu i kreatora dokumentów

Najpierw zainicjuj obiekty Document i DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2 Wstawienie pola scalającego i dodanie po nim tekstu

Użyj metody InsertField klasy DocumentBuilder, aby wstawić pole scalania, a następnie dodaj po nim tekst:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Krok 3: Kursor konstruktora znajduje się obecnie na końcu dokumentu.

```csharp
Assert.Null(builder.CurrentNode);
```
## Krok 4: Przesunięcie kursora narzędzia do tworzenia dokumentów do pola scalania

Aby przenieść kursor konstruktora dokumentów do pola scalania, użyj metody MoveToField klasy DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Dodanie tekstu bezpośrednio po polu scalania

Gdy kursor narzędzia do tworzenia dokumentów znajdzie się w polu scalania, możesz dodać tekst bezpośrednio po nim, korzystając z metody Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Przykładowy kod źródłowy dla pola Move To Merge przy użyciu Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pole za pomocą narzędzia DocumentBuilder i dodaj po nim ciąg tekstu.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Kursor konstruktora znajduje się obecnie na końcu dokumentu.
Assert.Null(builder.CurrentNode);
// Możemy przenieść konstruktora do takiego pola, umieszczając kursor bezpośrednio za polem.
builder.MoveToField(field, true);

// Należy zauważyć, że kursor znajduje się w miejscu za węzłem FieldEnd pola, co oznacza, że w rzeczywistości nie znajdujemy się w polu.
// Jeśli chcemy przenieść DocumentBuilder do wnętrza pola,
// będziemy musieli przenieść go do węzła FieldStart lub FieldSeparator pola przy użyciu metody DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Wniosek

sprawdziliśmy funkcję Move To Merge Field w Aspose.Words dla .NET. Dowiedzieliśmy się, jak nawigować w celu scalania pól w dokumencie za pomocą klasy DocumentBuilder i wykonywać na nich operacje. Ta funkcja jest przydatna podczas programowego przetwarzania słów z łączeniem

### Często zadawane pytania dotyczące przejścia do pola scalania w dokumencie programu Word

#### P: Jaki jest cel funkcji Move To Merge Field w Aspose.Words dla .NET?

O: Funkcja Move To Merge Field w Aspose.Words dla .NET umożliwia programistom nawigację w celu scalania pól w dokumencie programu Word i programowe wykonywanie na nich różnych operacji. Pola scalania to specjalne symbole zastępcze używane w dokumentach programu Word do operacji korespondencji seryjnej.

#### P: Jak mogę wstawić pole scalania do dokumentu programu Word przy użyciu Aspose.Words dla .NET?

O: Możesz użyć metody InsertField klasy DocumentBuilder, aby wstawić pole scalające do dokumentu. Po wstawieniu pola scalającego możesz dodać treść, na przykład tekst, przed lub po polu, korzystając z metody Write.

#### P: Jak przenieść kursor narzędzia do tworzenia dokumentów do określonego pola scalania?

O: Aby przenieść kursor narzędzia do tworzenia dokumentów do określonego pola scalania, użyj metody MoveToField klasy DocumentBuilder i przekaż pole jako parametr. Spowoduje to umieszczenie kursora bezpośrednio za polem scalania.

#### P: Czy mogę dodać tekst do pola scalania, korzystając z funkcji Przenieś do pola scalania?

O: Nie, funkcja Przenieś do pola scalania umieszcza kursor narzędzia do tworzenia dokumentów bezpośrednio za polem scalania. Aby dodać tekst do pola scalania, można użyć metody DocumentBuilder.MoveTo w celu przesunięcia kursora do węzła FieldStart lub FieldSeparator pola scalania.

#### P: Jak mogę wykonywać operacje korespondencji seryjnej przy użyciu Aspose.Words dla .NET?

Odp.: Aspose.Words dla .NET zapewnia szerokie wsparcie dla operacji korespondencji seryjnej. Za pomocą klasy MailMerge można wykonywać korespondencję seryjną przy użyciu danych z różnych źródeł, takich jak tablice, zestawy danych lub niestandardowe źródła danych.