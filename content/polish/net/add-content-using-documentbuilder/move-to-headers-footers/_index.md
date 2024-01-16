---
title: Przejdź do nagłówków i stopek w dokumencie programu Word
linktitle: Przejdź do nagłówków i stopek w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać Aspose.Words dla .NET do nawigacji i modyfikowania nagłówków i stopek w dokumentach programu Word, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/move-to-headers-footers/
---
W tym przykładzie omówimy funkcję Przenieś do stopek nagłówków w Aspose.Words dla .NET. Aspose.Words to potężna biblioteka do manipulacji dokumentami, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word. Funkcja Przenieś do nagłówków/stopek umożliwia nam przechodzenie do różnych nagłówków i stopek w dokumencie oraz dodawanie do nich treści.

Przejrzyjmy kod źródłowy krok po kroku, aby zrozumieć, jak korzystać z funkcji Przenieś do nagłówków/stopek przy użyciu Aspose.Words dla .NET.

## Krok 1: Inicjowanie dokumentu i kreatora dokumentów

Najpierw zainicjuj obiekty Document i DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Konfiguracja nagłówków i stopek

Określ ustawienia nagłówka/stopki dokumentu. W tym przykładzie ustawiamy różne nagłówki i stopki dla pierwszej strony oraz dla stron nieparzystych i parzystych:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Krok 3: Tworzenie nagłówków dla różnych stron

Przejdź do każdego typu nagłówka i dodaj do niego treść. W tym przykładzie tworzymy nagłówki dla pierwszej strony, stron parzystych i wszystkich pozostałych stron:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Krok 4: Tworzenie stron w dokumencie
Dodaj treść do dokumentu, aby utworzyć wiele stron. Na przykład:

```csharp
// Utwórz dwie strony w dokumencie.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Krok 5: Zapisanie dokumentu

Zapisz zmodyfikowany dokument w wybranej lokalizacji:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Upewnij się, że podałeś odpowiednią ścieżkę i format pliku (np. DOCX).

### Przykładowy kod źródłowy funkcji Przenieś do nagłówków/stopek przy użyciu Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Określ, że nagłówki i stopki mają być różne dla stron pierwszych, parzystych i nieparzystych.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Utwórz nagłówki.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Utwórz dwie strony w dokumencie.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## Wniosek

tym przykładzie zbadaliśmy funkcję Przenieś do nagłówków/stopek w Aspose.Words dla .NET. Dowiedzieliśmy się, jak nawigować do różnych nagłówków i stopek w dokumencie programu Word oraz dodawać do nich treść za pomocą klasy DocumentBuilder. Ta funkcja umożliwia programistom dostosowywanie nagłówków i stopek dla określonych stron lub sekcji, zapewniając elastyczność w tworzeniu profesjonalnych i uporządkowanych dokumentów. Aspose.Words dla .NET zapewnia potężny zestaw narzędzi do programowego manipulowania dokumentami Word, co czyni go niezbędną biblioteką dla aplikacji do przetwarzania dokumentów.

### Często zadawane pytania dotyczące przenoszenia do nagłówków i stopek w dokumencie programu Word

#### P: Jaki jest cel funkcji Przenieś do nagłówków/stopek w Aspose.Words dla .NET?

Odp.: Funkcja Przenieś do nagłówków/stopek w Aspose.Words dla .NET umożliwia programistom nawigację do różnych nagłówków i stopek w dokumencie programu Word oraz programowe dodawanie do nich treści. Jest to przydatne, gdy trzeba dostosować nagłówki i stopki dla różnych stron lub sekcji dokumentu.

#### P: Czy mogę mieć różne nagłówki i stopki dla różnych stron dokumentu?

O: Tak, możesz określić różne nagłówki i stopki dla pierwszej strony, stron parzystych i nieparzystych, korzystając odpowiednio z właściwości PageSetup.DifferentFirstPageHeaderFooter i PageSetup.OddAndEvenPagesHeaderFooter.

#### P: Jak mogę dodać treść do określonych nagłówków i stopek?

O: Aby dodać treść do określonych nagłówków i stopek, użyj metody MoveToHeaderFooter klasy DocumentBuilder. W zależności od wymagań możesz przejść do nagłówków HeaderFirst, HeaderEven i HeaderPrimary lub do stopek FooterFirst, FooterEven i FooterPrimary.

#### P: Czy mogę utworzyć nagłówki i stopki dla określonej sekcji dokumentu?

O: Tak, możesz użyć metody MoveToSection klasy DocumentBuilder, aby przejść do określonej sekcji dokumentu, a następnie utworzyć w tej sekcji nagłówki i stopki.

#### P: Jak mogę zapisać zmodyfikowany dokument do pliku przy użyciu Aspose.Words dla .NET?

Odp.: Możesz zapisać zmodyfikowany dokument w wybranej lokalizacji i formacie, korzystając z metody Save klasy Document. Pamiętaj, aby określić odpowiednią ścieżkę pliku i format pliku (np. DOCX).