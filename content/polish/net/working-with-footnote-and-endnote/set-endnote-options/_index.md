---
title: Ustaw opcje przypisu końcowego
linktitle: Ustaw opcje przypisu końcowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić opcje przypisów końcowych w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Samouczek krok po kroku z przykładowym kodem źródłowym.
type: docs
weight: 10
url: /pl/net/working-with-footnote-and-endnote/set-endnote-options/
---

tym samouczku krok po kroku poprowadzimy Cię, jak używać Aspose.Words dla .NET do ustawiania opcji przypisów końcowych w dokumencie programu Word. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicjowanie obiektu dokumentu

 Najpierw zainicjuj`Document` obiekt, podając ścieżkę do dokumentu źródłowego:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Krok 2: Inicjowanie obiektu DocumentBuilder

 Następnie zainicjuj`DocumentBuilder` obiekt umożliwiający wykonanie operacji na dokumencie:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Dodawanie tekstu i przypisu końcowego

 Użyj`Write` metoda`DocumentBuilder` obiekt, aby dodać tekst do dokumentu, oraz`InsertFootnote` metoda wstawiania przypisu końcowego:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Krok 4: Ustawianie opcji przypisu końcowego

 Uzyskać dostęp do`EndnoteOptions` właściwość dokumentu, aby zmodyfikować opcje przypisu końcowego. W tym przykładzie ustawiamy regułę ponownego uruchamiania na każdej stronie i pozycję na końcu sekcji:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Krok 5: Zapisywanie dokumentu

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Otóż to! Pomyślnie ustawiłeś opcje przypisu końcowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Ustaw opcje przypisu końcowego przy użyciu Aspose.Words dla .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### P: Jak mogę nadać styl przypisom końcowym w Aspose.Words?

 O: Aby nadać styl przypisom końcowym w Aspose.Words, możesz użyć metody`EndnoteOptions` klasa i`SeparatorNoteTextStyle` nieruchomość. Za pomocą tej właściwości możesz określić styl czcionki, rozmiar, kolor itp. dla przypisów końcowych.

#### P: Czy można dostosować numerację przypisów końcowych w dokumencie?

 O: Tak, istnieje możliwość dostosowania numeracji przypisów końcowych w dokumencie. Możesz skorzystać z`RestartRule` I`NumberStyle` właściwości`EndnoteOptions` class, aby zdefiniować określone reguły ponownego uruchamiania i style numerowania.

#### P: Jak mogę umieścić przypisy końcowe w dokumencie?

 Odp.: Aby rozmieścić przypisy końcowe w dokumencie, możesz użyć opcji`Position` własność`EndnoteOptions` klasa. Możesz określić, czy przypisy końcowe mają być umieszczane na dole każdej strony, na końcu każdej sekcji, czy na końcu dokumentu.

#### P: Czy mogę dostosować format numeracji przypisów końcowych?

 O: Tak, możesz dostosować format numeracji przypisów końcowych w Aspose.Words. Użyj`NumberFormat` własność`EndnoteOptions` class, aby ustawić żądany format, taki jak cyfry arabskie, cyfry rzymskie, litery itp.

#### P: Czy można kontynuować numerowanie przypisów końcowych pomiędzy sekcjami dokumentu?

 Odpowiedź: Tak, możliwe jest kontynuowanie numerowania przypisów końcowych pomiędzy sekcjami dokumentu. Użyj`RestartRule` własność`EndnoteOptions` class i ustaw ją na`RestartContinuous` aby umożliwić kontynuację numeracji pomiędzy sekcjami.