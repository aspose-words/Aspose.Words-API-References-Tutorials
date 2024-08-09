---
title: Ustaw położenie przypisu dolnego i przypisu końcowego
linktitle: Ustaw położenie przypisu dolnego i przypisu końcowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić pozycje przypisów dolnych i końcowych w dokumentach programu Word za pomocą Aspose.Words dla .NET, korzystając ze szczegółowego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## Wstęp

Jeśli pracujesz z dokumentami programu Word i chcesz efektywnie zarządzać przypisami dolnymi i końcowymi, biblioteka Aspose.Words dla .NET jest Twoją ulubioną biblioteką. Ten samouczek przeprowadzi Cię przez proces ustawiania pozycji przypisów dolnych i końcowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Podzielimy każdy krok, aby ułatwić jego wykonanie i wdrożenie.

## Warunki wstępne

Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:

-  Biblioteka Aspose.Words dla .NET: Możesz ją pobrać z[Tutaj](https://releases.aspose.com/words/net/).
- Visual Studio: każda najnowsza wersja będzie działać poprawnie.
- Podstawowa znajomość języka C#: Zrozumienie podstaw pomoże Ci z łatwością kontynuować naukę.

## Importuj przestrzenie nazw

Najpierw zaimportuj niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using System;
using Aspose.Words;
```

## Krok 1: Załaduj dokument Word

Aby rozpocząć, musisz załadować dokument Word do obiektu Aspose.Words Document. Umożliwi to manipulowanie zawartością dokumentu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 W tym kodzie zamień`"YOUR DOCUMENT DIRECTORY"` rzeczywistą ścieżką, w której znajduje się dokument.

## Krok 2: Ustaw położenie przypisu

Następnie ustaw położenie przypisów. Aspose.Words dla .NET umożliwia umieszczanie przypisów na dole strony lub pod tekstem.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 Tutaj ustawiliśmy, że przypisy będą pojawiać się pod tekstem. Jeśli wolisz je na dole strony, użyj`FootnotePosition.BottomOfPage`.

## Krok 3: Ustaw pozycję przypisu końcowego

Podobnie możesz ustawić położenie przypisów końcowych. Przypisy końcowe można umieszczać na końcu sekcji lub na końcu dokumentu.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 W tym przykładzie przypisy końcowe są umieszczane na końcu każdej sekcji. Aby umieścić je na końcu dokumentu, użyj`EndnotePosition.EndOfDocument`.

## Krok 4: Zapisz dokument

Na koniec zapisz dokument, aby zastosować zmiany. Upewnij się, że podałeś poprawną ścieżkę pliku i nazwę dokumentu wyjściowego.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Ta linia zapisuje zmodyfikowany dokument w określonym katalogu.

## Wniosek

Ustawianie pozycji przypisów dolnych i końcowych w dokumentach programu Word przy użyciu Aspose.Words dla .NET jest proste, jeśli znasz kroki. Postępując zgodnie z tym przewodnikiem, możesz dostosować dokumenty do swoich potrzeb, zapewniając, że przypisy dolne i końcowe będą umieszczone dokładnie tam, gdzie chcesz.

## Często zadawane pytania

### Czy mogę ustawić różne pozycje poszczególnych przypisów dolnych i końcowych?

Nie, Aspose.Words dla .NET ustawia jednolitą pozycję wszystkich przypisów dolnych i końcowych w dokumencie.

### Czy Aspose.Words dla .NET jest kompatybilny ze wszystkimi wersjami dokumentów Word?

Tak, Aspose.Words dla .NET obsługuje szeroką gamę formatów dokumentów Word, w tym DOC, DOCX, RTF i inne.

### Czy mogę używać Aspose.Words dla .NET z innymi językami programowania?

Aspose.Words dla .NET jest przeznaczony dla aplikacji .NET, ale można go używać z dowolnym językiem obsługiwanym przez .NET, takim jak C#, VB.NET itp.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?

 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć bardziej szczegółową dokumentację Aspose.Words dla .NET?

 Dostępna jest szczegółowa dokumentacja[Tutaj](https://reference.aspose.com/words/net/).