---
title: Sprawdź efekt tekstowy DrawingML
linktitle: Sprawdź efekt tekstowy DrawingML
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak sprawdzić efekty tekstowe DrawingML w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/check-drawingml-text-effect/
---

tym samouczku przeprowadzimy Cię przez proces sprawdzania efektów tekstowych DrawingML w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla .NET. Sprawdzanie efektów tekstowych DrawingML pozwala określić, czy do części tekstu zastosowano określony efekt. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie
- Dokument programu Word zawierający efekty tekstowe DrawingML

## Krok 1: Zdefiniuj katalog dokumentów
 Najpierw musisz ustawić ścieżkę katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument i sprawdź efekty tekstowe
Następnie załadujemy dokument Word i uzyskamy dostęp do kolekcji przebiegów (sekwencji znaków) w pierwszym akapicie treści dokumentu. Następnie sprawdzimy, czy do czcionki pierwszego uruchomienia zastosowano jakieś konkretne efekty tekstowe DrawingML.

```csharp
// Załaduj dokument
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Sprawdź efekty tekstowe DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Przykładowy kod źródłowy dla efektu Sprawdź DMLText przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Do jednego uruchomienia może zostać zastosowanych kilka efektów tekstowych DML.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Wniosek
tym samouczku widzieliśmy, jak sprawdzić efekty tekstowe DrawingML w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Sprawdzanie efektów tekstowych DrawingML pozwala zidentyfikować części tekstu, do których zastosowano określone efekty. Możesz swobodnie używać tej funkcji do manipulowania i analizowania efektów tekstowych w dokumentach programu Word.

### Często zadawane pytania

#### P: Jak mogę uzyskać dostęp do efektów tekstowych DrawingML w dokumencie programu Word za pomocą Aspose.Words?

Odp.: Dzięki Aspose.Words możesz uzyskać dostęp do efektów tekstowych DrawingML w dokumencie Word za pomocą dostarczonego interfejsu API. Możesz przeglądać elementy tekstowe i sprawdzać określone właściwości efektów tekstowych, takie jak kolor, rozmiar itp.

#### P: Jakie typy efektów tekstowych DrawingML są powszechnie używane w dokumentach programu Word?

Odp.: Powszechnie używane typy efektów tekstowych DrawingML w dokumentach programu Word obejmują cienie, odbicia, poświaty, gradienty itp. Efekty te można zastosować w celu poprawy wyglądu i formatowania tekstu.

#### P: Jak mogę sprawdzić kolor efektu tekstowego DrawingML w dokumencie programu Word?

Odp.: Aby sprawdzić kolor efektu tekstowego DrawingML w dokumencie programu Word, możesz skorzystać z metod dostarczonych przez Aspose.Words, aby uzyskać dostęp do właściwości koloru efektu tekstowego. W ten sposób możesz uzyskać kolor używany dla konkretnego efektu tekstowego.

#### P: Czy można sprawdzić efekty tekstowe w dokumentach programu Word zawierających wiele sekcji?

Odp.: Tak, Aspose.Words umożliwia sprawdzanie efektów tekstowych w dokumentach Word zawierających wiele sekcji. Możesz poruszać się po każdej sekcji dokumentu i uzyskiwać dostęp do efektów tekstowych dla każdej sekcji indywidualnie.

#### P: Jak mogę sprawdzić przezroczystość efektu tekstowego DrawingML w dokumencie programu Word?

Odp.: Aby sprawdzić krycie efektu tekstowego DrawingML w dokumencie programu Word, możesz skorzystać z metod dostarczonych przez Aspose.Words, aby uzyskać dostęp do właściwości krycia efektu tekstowego. Umożliwi to zastosowanie wartości krycia do określonego efektu tekstowego.