---
title: Przejdź do sekcji w dokumencie programu Word
linktitle: Przejdź do sekcji w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący korzystania z funkcji Przenieś do sekcji w dokumencie programu Word w Aspose.Words dla platformy .NET manipuluje sekcjami i akapitami w dokumentach programu Word.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/move-to-section/
---
W tym przykładzie przeprowadzimy Cię krok po kroku przez proces korzystania z funkcji Przenieś do sekcji w dokumencie programu Word w Aspose.Words dla .NET, korzystając z dostarczonego kodu źródłowego C#. Ta funkcja umożliwia nawigację i manipulowanie różnymi sekcjami dokumentu programu Word. Wykonaj poniższe kroki, aby zintegrować tę funkcjonalność z aplikacją.

## Krok 1: Utwórz nowy dokument i dodaj sekcję

Najpierw musimy utworzyć nowy dokument i dodać do niego sekcję. Aby wykonać ten krok, użyj poniższego kodu:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Ten kod tworzy nowy pusty dokument i dodaje sekcję do tego dokumentu.

## Krok 2: Przenieś DocumentBuilder do drugiej sekcji i dodaj tekst

Następnie musimy przenieść DocumentBuilder do drugiej sekcji dokumentu i dodać tam trochę tekstu. Aby wykonać ten krok, użyj poniższego kodu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Ten kod tworzy DocumentBuilder na podstawie istniejącego dokumentu, a następnie przesuwa kursor z DocumentBuilder do drugiej sekcji dokumentu. Na koniec dodaje określony tekst do tej sekcji.

## Krok 3: Załaduj dokument z istniejącymi akapitami

Jeśli chcesz pracować z istniejącym dokumentem zawierającym akapity, możesz załadować ten dokument, używając następującego kodu:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Ten kod ładuje określony dokument (zamień „MyDir + „Paragraphs.docx„” z rzeczywistą ścieżką do dokumentu) i uzyskuje dostęp do zbioru akapitów z pierwszej części dokumentu. Linia`Assert.AreEqual(22, paragraphs.Count);` sprawdza, czy dokument zawiera 22 akapity.

## Krok 4: utwórz narzędzie DocumentBuilder dla dokumentu

Możesz utworzyć kursor DocumentBuilder do określonego akapitu, używając indeksów pozycyjnych.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Krok 5: Przesuń kursor do określonego akapitu


Możesz przenieść kursor DocumentBuilder do określonego akapitu, używając indeksów pozycyjnych. Oto jak to zrobić:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Ten kod przesuwa kursor DocumentBuilder do trzeciego akapitu drugiej sekcji (akapit w indeksie 2) i do pozycji 10. Następnie dodaje nowy akapit z jakimś tekstem i sprawdza, czy kursor jest dobrze ustawiony w tym nowym akapicie.

### Przykładowy kod źródłowy dla opcji Przenieś do sekcji Przenieś do przy użyciu Aspose.Words dla .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Przenieś DocumentBuilder do drugiej sekcji i dodaj tekst.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Utwórz dokument z akapitami.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Kiedy tworzymy DocumentBuilder dla dokumentu, jego kursor domyślnie znajduje się na samym początku dokumentu,
// a cała treść dodana przez DocumentBuilder zostanie po prostu dodana do dokumentu.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//Możesz przesunąć kursor w dowolne miejsce w akapicie.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

To wszystko ! Teraz zrozumiałeś, jak korzystać z funkcji przenoszenia do sekcji Aspose.Words dla .NET, korzystając z dostarczonego kodu źródłowego. Możesz teraz zintegrować tę funkcjonalność ze swoją własną aplikacją i dynamicznie manipulować sekcjami i akapitami dokumentów Word.

## Wniosek

W tym przykładzie zbadaliśmy funkcję Przenieś do sekcji w Aspose.Words dla .NET. Dowiedzieliśmy się, jak utworzyć nowy dokument, dodać do niego sekcje i używać klasy DocumentBuilder do nawigacji do określonych sekcji i akapitów w dokumencie Word. Ta funkcja zapewnia programistom potężne narzędzia do programowego manipulowania zawartością i strukturą dokumentów programu Word przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania dotyczące przejścia do sekcji w dokumencie programu Word

#### P: Jaki jest cel funkcji Przenieś do sekcji w Aspose.Words dla .NET?

Odp.: Funkcja Przenieś do sekcji w Aspose.Words dla .NET umożliwia programistom nawigację i programowe manipulowanie różnymi sekcjami w dokumencie programu Word. Zapewnia możliwość wstawiania, modyfikowania lub usuwania treści w określonych sekcjach dokumentu.

#### P: Jak przenieść moduł DocumentBuilder do określonej sekcji dokumentu programu Word?

O: Aby przenieść moduł DocumentBuilder do określonej sekcji dokumentu programu Word, można użyć metody MoveToSection klasy DocumentBuilder. Ta metoda przyjmuje indeks sekcji docelowej jako parametr i umieszcza kursor na początku tej sekcji.

#### P: Czy mogę dodać lub zmodyfikować treść po przejściu do określonej sekcji za pomocą funkcji Przenieś do sekcji?

O: Tak, po umieszczeniu modułu DocumentBuilder w żądanej sekcji za pomocą funkcji MoveToSection, można użyć różnych metod klasy DocumentBuilder, takich jak Writeln, Write lub InsertHtml, aby dodać lub zmodyfikować zawartość tej sekcji.

#### P: Jak mogę pracować z istniejącymi akapitami w dokumencie, korzystając z funkcji Przenieś do sekcji?

Odpowiedź: Możesz załadować istniejący dokument zawierający akapity za pomocą konstruktora Document, a następnie uzyskać dostęp do zbioru akapitów z żądanej sekcji za pomocą właściwości FirstSection.Body.Paragraphs.

#### P: Czy mogę przenieść kursor programu DocumentBuilder do określonego akapitu w sekcji, korzystając z funkcji Przenieś do sekcji?

O: Tak, możesz przenieść kursor programu DocumentBuilder do określonego akapitu w sekcji, korzystając z metody MoveToParagraph. Ta metoda przyjmuje jako parametry indeksy akapitu docelowego i pozycję znaku (przesunięcie) w akapicie.