---
title: Przesuń węzeł w śledzonym dokumencie
linktitle: Przesuń węzeł w śledzonym dokumencie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak przenosić węzły w śledzonym dokumencie programu Word za pomocą Aspose.Words dla .NET, korzystając z naszego szczegółowego przewodnika krok po kroku. Idealny dla programistów.
type: docs
weight: 10
url: /pl/net/working-with-revisions/move-node-in-tracked-document/
---
## Wstęp

Hej, entuzjaści Aspose.Words! Jeśli kiedykolwiek musiałeś przenieść węzeł w dokumencie programu Word podczas śledzenia wersji, jesteś we właściwym miejscu. Dzisiaj zagłębimy się w to, jak to osiągnąć za pomocą Aspose.Words dla .NET. Nie tylko poznasz proces krok po kroku, ale także poznasz wskazówki i triki, dzięki którym manipulacja dokumentami będzie płynna i wydajna.

## Warunki wstępne

Zanim zabrudzimy sobie ręce kodem, upewnijmy się, że mamy wszystko, czego potrzebujemy:

-  Aspose.Words dla .NET: Pobierz[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko .NET: Upewnij się, że masz skonfigurowane kompatybilne środowisko programistyczne .NET.
- Podstawowa znajomość języka C#: w tym samouczku założono, że masz podstawową wiedzę na temat języka C#.

Masz wszystko? Świetnie! Przejdźmy do przestrzeni nazw, które musimy zaimportować.

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw. Są one niezbędne do pracy z Aspose.Words i obsługi węzłów dokumentów.

```csharp
using Aspose.Words;
using System;
```

W porządku, podzielmy proces na łatwe do wykonania etapy. Każdy krok zostanie szczegółowo wyjaśniony, abyś miał pewność, że rozumiesz, co się dzieje w każdym momencie.

## Krok 1: Zainicjuj dokument

 Na początek musimy zainicjować nowy dokument i użyć a`DocumentBuilder` dodać kilka akapitów.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Dodanie kilku akapitów
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Sprawdź początkową liczbę akapitów
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Krok 2: Rozpocznij śledzenie wersji

Następnie musimy rozpocząć śledzenie wersji. Jest to o tyle istotne, że pozwala zobaczyć zmiany wprowadzone w dokumencie.

```csharp
// Rozpocznij śledzenie wersji
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Krok 3: Przenieś węzły

Teraz następuje główna część naszego zadania: przeniesienie węzła z jednej lokalizacji do drugiej. Przeniesiemy trzeci akapit i umieścimy go przed pierwszym akapitem.

```csharp
// Zdefiniuj węzeł, który ma zostać przesunięty i jego końcowy zasięg
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Przesuń węzły w zdefiniowanym zakresie
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Krok 4: Zatrzymaj śledzenie wersji

Po przeniesieniu węzłów musimy zaprzestać śledzenia wersji.

```csharp
// Przestań śledzić wersje
doc.StopTrackRevisions();
```

## Krok 5: Zapisz dokument

Na koniec zapiszmy nasz zmodyfikowany dokument we wskazanym katalogu.

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Wypisz końcową liczbę akapitów
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Wniosek

I masz to! Pomyślnie przeniosłeś węzeł w śledzonym dokumencie za pomocą Aspose.Words dla .NET. Ta potężna biblioteka ułatwia programowe manipulowanie dokumentami programu Word. Niezależnie od tego, czy tworzysz, edytujesz czy śledzisz zmiany, Aspose.Words pomoże Ci. Więc śmiało, spróbuj. Miłego kodowania!

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?

Aspose.Words dla .NET to biblioteka klas do programowej pracy z dokumentami programu Word. Umożliwia programistom tworzenie, edytowanie, konwertowanie i drukowanie dokumentów programu Word w aplikacjach .NET.

### Jak śledzić wersje w dokumencie programu Word za pomocą Aspose.Words?

 Aby śledzić wersje, użyj opcji`StartTrackRevisions` metoda na`Document` obiekt. Umożliwi to śledzenie wersji i pokazanie wszelkich zmian wprowadzonych w dokumencie.

### Czy mogę przenosić wiele węzłów w Aspose.Words?

Tak, możesz przenosić wiele węzłów, iterując po nich i używając metod takich jak`InsertBefore` Lub`InsertAfter` aby umieścić je w żądanym miejscu.

### Jak zatrzymać śledzenie wersji w Aspose.Words?

 Skorzystaj z`StopTrackRevisions` metoda na`Document` sprzeciwić się zaprzestaniu śledzenia wersji.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?

 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/words/net/).