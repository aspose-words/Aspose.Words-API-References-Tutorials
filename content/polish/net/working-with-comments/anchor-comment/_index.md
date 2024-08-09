---
title: Komentarz kotwicy
linktitle: Komentarz kotwicy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać komentarze zakotwiczone w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie współpracować nad dokumentami.
type: docs
weight: 10
url: /pl/net/working-with-comments/anchor-comment/
---
## Wstęp

Czy kiedykolwiek znalazłeś się w sytuacji, w której musiałeś programowo dodać komentarze do określonych sekcji tekstu w dokumencie programu Word? Wyobraź sobie, że współpracujesz ze swoim zespołem nad dokumentem i musisz wyróżnić pewne fragmenty za pomocą komentarzy, aby inni mogli je przejrzeć. W tym samouczku szczegółowo omówimy, jak wstawiać komentarze zakotwiczone w dokumentach programu Word za pomocą Aspose.Words dla .NET. Podzielimy ten proces na proste kroki, dzięki czemu łatwiej będzie Ci je śledzić i wdrażać w swoich projektach.

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words. Można go pobrać z[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: dowolne środowisko programistyczne .NET, takie jak Visual Studio.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# pomoże Ci łatwo wykonać poniższe kroki.

Przyjrzyjmy się teraz przestrzeniom nazw, które będziesz musiał zaimportować w celu wykonania tego zadania.

## Importuj przestrzenie nazw

Na początek upewnij się, że zaimportowałeś niezbędne przestrzenie nazw w swoim projekcie. Oto wymagane przestrzenie nazw:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.CommentRangeStart;
using Aspose.Words.CommentRangeEnd;
```

Po usunięciu wymagań wstępnych i przestrzeni nazw przejdźmy do przyjemniejszej części: podzielenia procesu krok po kroku.

## Krok 1: Utwórz nowy dokument

Najpierw utwórzmy nowy dokument Word. Będzie to stanowić kanwę dla naszych komentarzy.

```csharp
// Określ katalog, w którym zostanie zapisany dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";        

// Utwórz instancję klasy Document
Document doc = new Document();
```

 Na tym etapie inicjujemy nowy plik`Document` obiekt, który będzie używany do dodawania naszych komentarzy.

## Krok 2: Dodaj tekst do dokumentu

Następnie dodamy trochę tekstu do dokumentu. Tekst ten będzie przedmiotem naszych komentarzy.

```csharp
// Utwórz pierwszy akapit i działa
Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

// Utwórz drugi akapit i działa
Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

 Tutaj tworzymy dwa akapity z jakimś tekstem. Każdy fragment tekstu jest zamknięty w formacie A`Run` obiekt, który następnie jest dodawany do akapitów.

## Krok 3: Utwórz komentarz

Stwórzmy teraz komentarz, który dołączymy do naszego tekstu.

```csharp
// Utwórz nowy komentarz
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

 Na tym etapie tworzymy plik`Comment` obiekt i dodaj akapit oraz przebieg z tekstem komentarza.

## Krok 4: Zdefiniuj zakres komentarza

Aby zakotwiczyć komentarz w konkretnym tekście, musimy zdefiniować początek i koniec zakresu komentarza.

```csharp
// Zdefiniuj CommentRangeStart i CommentRangeEnd
CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

// Wstaw elementy CommentRangeStart i CommentRangeEnd do dokumentu
run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);

// Dodaj komentarz do dokumentu
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

 Tutaj tworzymy`CommentRangeStart`I`CommentRangeEnd` obiekty, łącząc je z komentarzem za pomocą jego identyfikatora. Następnie wstawiamy te zakresy do dokumentu, skutecznie zakotwiczając nasz komentarz do określonego tekstu.

## Krok 5: Zapisz dokument

Na koniec zapiszmy nasz dokument we wskazanym katalogu.

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

Ten krok powoduje zapisanie dokumentu z zakotwiczonym komentarzem w określonym katalogu.

## Wniosek

I masz to! Pomyślnie nauczyłeś się, jak dodawać komentarze zakotwiczone do określonych sekcji tekstu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Technika ta jest niezwykle przydatna we współpracy nad dokumentami, umożliwiając łatwe wyróżnianie i komentowanie określonych części tekstu. Niezależnie od tego, czy pracujesz nad projektem ze swoim zespołem, czy przeglądasz dokumenty, ta metoda zwiększy Twoją produktywność i usprawni przepływ pracy.

## Często zadawane pytania

### Jaki jest cel używania komentarzy zakotwiczeń w dokumentach programu Word?
Komentarze zakotwiczone służą do wyróżniania i komentowania określonych sekcji tekstu, co ułatwia przekazywanie opinii i współpracę nad dokumentami.

### Czy mogę dodać wiele komentarzy do tej samej sekcji tekstowej?
Tak, możesz dodać wiele komentarzy do tej samej sekcji tekstowej, definiując wiele zakresów komentarzy.

### Czy korzystanie z Aspose.Words dla .NET jest bezpłatne?
Aspose.Words dla .NET oferuje bezpłatną wersję próbną, którą możesz pobrać[Tutaj](https://releases.aspose.com/) . Aby uzyskać pełne funkcje, możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy).

### Czy mogę dostosować wygląd komentarzy?
Chociaż Aspose.Words koncentruje się na funkcjonalności, wygląd komentarzy w dokumentach programu Word jest zazwyczaj kontrolowany przez sam program Word.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/words/net/).