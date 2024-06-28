---
title: Odstęp między tekstem azjatyckim i łacińskim w dokumencie programu Word
linktitle: Odstęp między tekstem azjatyckim i łacińskim w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak automatycznie dostosowywać odstępy między tekstem azjatyckim i łacińskim w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-formatting/space-between-asian-and-latin-text/
---
W tym samouczku pokażemy, jak używać funkcji spacji między tekstem azjatyckim i łacińskim w funkcji dokumentu programu Word w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany.

## Krok 1: Tworzenie i konfiguracja dokumentu

Aby rozpocząć, utwórz nowy dokument i powiązany obiekt DocumentBuilder. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Ustawianie odstępu między tekstem azjatyckim i łacińskim

Skonfigurujemy teraz odstęp między tekstem azjatyckim i łacińskim, korzystając z właściwości obiektu ParagraphFormat. Oto jak:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Krok 3: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Przykładowy kod źródłowy dla spacji między tekstem azjatyckim i łacińskim przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji Space Between Asian and Latin Text w Aspose.Words dla .NET:


```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Za pomocą tego kodu będziesz mógł automatycznie dostosować odstępy między tekstem azjatyckim i łacińskim w swoim dokumencie za pomocą Aspose.Words dla .NET.

## Wniosek

W tym samouczku omówiliśmy proces używania funkcji Spacja do dostosowywania odstępów między tekstem azjatyckim i łacińskim w dokumencie programu Word za pomocą Aspose.Words dla .NET. Wykonując opisane czynności, możesz zapewnić odpowiednie odstępy i wyrównanie, co jest szczególnie przydatne w przypadku mieszanej treści azjatyckiej i łacińskiej.

### Często zadawane pytania

#### P: Jaka jest funkcja spacji między tekstem azjatyckim i łacińskim w dokumencie programu Word?

Odp.: Funkcja odstępu między tekstem azjatyckim i łacińskim w dokumencie programu Word odnosi się do możliwości automatycznego dostosowywania odstępów między tekstem zapisanym różnymi pismami, takimi jak azjatycki (np. chiński, japoński) i łaciński (np. angielski).

#### P: Dlaczego dostosowanie odstępu między tekstem azjatyckim i łacińskim jest ważne?

O: Dostosowanie odstępów między tekstem azjatyckim i łacińskim ma kluczowe znaczenie, aby zapewnić harmonijne połączenie różnych pism w dokumencie. Właściwe odstępy zwiększają czytelność i ogólny wygląd, zapobiegając sprawianiu wrażenia, że tekst jest zbyt ciasny lub rozłożony.

#### P: Czy mogę dostosować odstępy między różnymi skryptami?

 Odp.: Tak, możesz dostosować odstępy między różnymi skryptami za pomocą`AddSpaceBetweenFarEastAndAlpha` I`AddSpaceBetweenFarEastAndDigit` nieruchomości. Włączając lub wyłączając te właściwości, możesz kontrolować odstęp między tekstem azjatyckim i łacińskim, a także między tekstem azjatyckim a liczbami.

#### P: Czy Aspose.Words dla .NET obsługuje inne funkcje formatowania dokumentów?

O: Tak, Aspose.Words dla .NET oferuje szerokie wsparcie dla różnych funkcji formatowania dokumentów. Zawiera funkcje dotyczące stylów czcionek, akapitów, tabel, obrazów i nie tylko. Możesz skutecznie programowo manipulować i formatować dokumenty programu Word.

#### P: Gdzie mogę znaleźć dodatkowe zasoby i dokumentację dla Aspose.Words dla .NET?

 Odp.: Aby zapoznać się z obszernymi zasobami i dokumentacją dotyczącą korzystania z Aspose.Words dla .NET, odwiedź stronę[Dokumentacja API Aspose.Words](https://reference.aspose.com/words/net/). Znajdziesz tam szczegółowe przewodniki, samouczki, przykłady kodu i odniesienia do API, które pomogą Ci efektywnie wykorzystać zaawansowane funkcje Aspose.Words dla .NET.