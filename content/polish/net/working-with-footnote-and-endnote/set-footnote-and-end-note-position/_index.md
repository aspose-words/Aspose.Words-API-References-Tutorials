---
title: Ustaw położenie przypisu dolnego i przypisu końcowego
linktitle: Ustaw położenie przypisu dolnego i przypisu końcowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić położenie przypisów dolnych i końcowych w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak używać Aspose.Words dla .NET do ustawiania pozycji przypisów dolnych i końcowych w dokumencie programu Word. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Inicjowanie obiektu dokumentu

 Najpierw zainicjuj`Document` obiekt, podając ścieżkę do dokumentu źródłowego:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Krok 2: Ustawianie pozycji przypisu dolnego i przypisu końcowego

 Następnie uzyskaj dostęp do`FootnoteOptions`I`EndnoteOptions`właściwości dokumentu, aby ustawić położenie przypisów dolnych i końcowych. W tym przykładzie ustawiamy położenie przypisów pod tekstem, a położenie przypisów końcowych na końcu sekcji:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Krok 3: Zapisywanie dokumentu

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Otóż to! Pomyślnie ustawiłeś położenie przypisów dolnych i końcowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Ustaw pozycję przypisu dolnego i przypisu końcowego przy użyciu Aspose.Words dla .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### P: Jak mogę rozmieścić przypisy dolne i końcowe w Aspose.Words?

 O: Aby rozmieścić przypisy dolne i końcowe w Aspose.Words, musisz użyć opcji`FootnoteOptions` klasa i`Position` nieruchomość. Możesz ustawić tę właściwość na dowolną wartość, np`BottomOfPage` (na dole strony) lub`EndOfSection` (na końcu sekcji).

#### P: Czy można dostosować położenie przypisów dolnych i końcowych dla każdej strony lub sekcji dokumentu?

O: Tak, możliwe jest dostosowanie położenia przypisów dolnych i końcowych dla każdej strony lub sekcji dokumentu. Możesz użyć metod manipulacji sekcjami i stronami Aspose.Words, aby zdefiniować określone pozycje przypisów dolnych i końcowych.

#### P: Jak usunąć przypisy dolne i końcowe z dokumentu?

 Odp.: Aby usunąć przypisy dolne lub końcowe z dokumentu w Aspose.Words, możesz użyć odpowiednich metod, takich jak`RemoveAllFootnotes` aby usunąć wszystkie przypisy lub`RemoveAllEndnotes` , aby usunąć wszystkie przypisy końcowe. Po wykonaniu tych operacji pamiętaj o zapisaniu dokumentu.

#### P: Czy przypisy dolne i końcowe można umieszczać poza marginesami strony?

Nie, domyślnie przypisy dolne i końcowe nie mogą być umieszczane poza marginesami strony w Aspose.Words. Można jednak dostosować marginesy dokumentu, aby w razie potrzeby zapewnić więcej miejsca na przypisy dolne i końcowe.

#### P: Czy przypisy dolne i końcowe można dostosować za pomocą określonej czcionki lub stylu formatowania?

Odp.: Tak, możesz dostosować przypisy dolne i końcowe za pomocą określonej czcionki lub stylów formatowania w Aspose.Words. Możesz użyć dostępnych metod i właściwości, aby zastosować style czcionek, kolory, rozmiary czcionek itp. przypisy i przypisy końcowe.