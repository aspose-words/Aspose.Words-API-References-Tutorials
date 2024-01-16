---
title: Przejdź do początku i końca dokumentu w dokumencie programu Word
linktitle: Przejdź do początku i końca dokumentu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak korzystać z Aspose.Words dla .NET, aby przejść do początku i końca dokumentu w dokumentach programu Word, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/move-to-document-start-end/
---
W tym przykładzie omówimy funkcję Przenieś do początku/końca dokumentu w Aspose.Words dla .NET. Aspose.Words to potężna biblioteka do manipulacji dokumentami, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word. Funkcja Przenieś na początek/koniec dokumentu umożliwia nam przejście na początek lub koniec dokumentu przy użyciu klasy DocumentBuilder.

## Wyjaśnienie kodu źródłowego krok po kroku

Przyjrzyjmy się krok po kroku kodowi źródłowemu, aby zrozumieć, jak używać funkcji Przenieś do początku/końca dokumentu przy użyciu Aspose.Words dla .NET.


## Krok 1: Inicjowanie dokumentu i kreatora dokumentów

Następnie zainicjuj obiekty Document i DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Przejście do początku dokumentu

Aby przenieść pozycję kursora na początek dokumentu, należy skorzystać z metody MoveToDocumentStart klasy DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Krok 3: Przejście na koniec dokumentu

Aby przenieść pozycję kursora na koniec dokumentu, należy skorzystać z metody MoveToDocumentEnd klasy DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Krok 4: Wyprowadzanie pozycji kursora

Możesz wyprowadzić pozycję kursora za pomocą Console.WriteLine lub dowolnej innej żądanej metody. Na przykład:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Przykładowy kod źródłowy dla opcji Przenieś na początek/koniec dokumentu przy użyciu Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Przesuń kursor na początek dokumentu.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Przesuń kursor na koniec dokumentu.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Wniosek

W tym przykładzie zbadaliśmy funkcję Przenieś na początek/koniec dokumentu w Aspose.Words dla .NET. Dowiedzieliśmy się, jak nawigować na początek i na koniec dokumentu, korzystając z klasy DocumentBuilder. Ta funkcja jest przydatna podczas programowego przetwarzania tekstu w dokumentach programu Word i konieczności manipulowania lub wstawiania treści w określonych miejscach w dokumencie.

### Często zadawane pytania

#### P: Jaki jest cel funkcji Przenieś na początek/koniec dokumentu w Aspose.Words dla .NET?

Odp.: Funkcja Przenieś na początek/koniec dokumentu w Aspose.Words dla .NET umożliwia programistom nawigację na początek lub koniec dokumentu programu Word przy użyciu klasy DocumentBuilder. Jest to przydatne do programowego manipulowania lub wstawiania treści w określonych miejscach dokumentu.

#### P: Czy mogę używać tej funkcji z istniejącym dokumentem programu Word?

O: Tak, możesz użyć funkcji Przenieś na początek/koniec dokumentu zarówno w przypadku nowych, jak i istniejących dokumentów programu Word. Wystarczy zainicjalizować obiekt DocumentBuilder odpowiednim obiektem Document, a następnie użyć metod MoveToDocumentStart i MoveToDocumentEnd, jak pokazano w przykładowym kodzie źródłowym.

#### P: W jaki sposób metoda DocumentBuilder.MoveToDocumentStart/MoveToDocumentEnd wpływa na zawartość dokumentu?

Odp.: Metoda DocumentBuilder.MoveToDocumentStart przesuwa kursor na początek dokumentu bez zmiany istniejącej zawartości. Podobnie metoda DocumentBuilder.MoveToDocumentEnd przesuwa kursor na koniec dokumentu bez zmiany jego zawartości.

#### P: Czy mogę wykonać inne operacje po przesunięciu kursora na koniec dokumentu?

O: Tak, po przesunięciu kursora na koniec dokumentu, możesz kontynuować korzystanie z narzędzia DocumentBuilder, aby dodać lub zmodyfikować treść w tym miejscu. Pozycja kursora pozostaje na końcu dokumentu, dopóki nie zostanie wyraźnie przesunięta.

#### P: Jak mogę wyświetlić pozycję kursora za pomocą Aspose.Words dla .NET?

O: Możesz wyprowadzić pozycję kursora za pomocą metod takich jak Console.WriteLine, logowanie lub dowolny inny pożądany mechanizm wyjściowy. W podanym przykładowym kodzie źródłowym Console.WriteLine służy do wyświetlania komunikatów na początku i na końcu dokumentu.