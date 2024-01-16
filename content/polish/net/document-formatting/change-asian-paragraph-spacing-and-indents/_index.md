---
title: Zmień azjatyckie odstępy między akapitami i wcięcia w dokumencie programu Word
linktitle: Zmień azjatyckie odstępy między akapitami i wcięcia w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmieniać azjatyckie odstępy między akapitami i wcięcia w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
W tym samouczku przeprowadzimy Cię przez proces zmiany odstępów i wcięć w akapicie azjatyckim za pomocą Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany.

## Krok 1: Ładowanie dokumentu

Aby rozpocząć, określ katalog dla swoich dokumentów i załaduj dokument zawierający typografię azjatycką do obiektu Dokument. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Krok 2: Zmiana odstępów i wcięć akapitów

Zmodyfikujemy teraz odstępy i wcięcia pierwszego akapitu dokumentu azjatyckiego. Oto jak:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Zaktualizuj ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Zaktualizuj ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Zaktualizuj ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Zaktualizuj ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Zaktualizuj ParagraphFormat.SpaceAfter
```

## Krok 3: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Przykładowy kod źródłowy zmiany odstępów i wcięć akapitów azjatyckich przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji Edytuj azjatyckie odstępy i wcięcia akapitów w Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent zostanie zaktualizowany
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent zostanie zaktualizowany
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent zostanie zaktualizowany
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore zostanie zaktualizowany
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter zostanie zaktualizowany

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Za pomocą tego kodu będziesz mógł zmienić odstępy i wcięcia akapitu azjatyckiego za pomocą Aspose.Words dla .NET.

## Wniosek

 W tym samouczku nauczyliśmy się zmieniać odstępy i wcięcia akapitu azjatyckiego za pomocą Aspose.Words dla .NET. Modyfikując odpowiednie właściwości pliku`ParagraphFormat`możemy kontrolować układ i wygląd akapitów azjatyckich w dokumencie Word. Ta funkcja jest przydatna do dostosowywania formatowania tekstu przy użyciu znaków azjatyckich i uzyskiwania pożądanej prezentacji wizualnej w dokumentach o zawartości w różnych językach.

### Często zadawane pytania

#### P: Do czego służy funkcja „Zmień odstępy i wcięcia akapitów azjatyckich” w Aspose.Words dla .NET?

Odp.: Funkcja „Zmień odstępy i wcięcia akapitów azjatyckich” w Aspose.Words dla .NET umożliwia modyfikowanie właściwości odstępów i wcięć akapitu azjatyckiego w dokumencie programu Word. Możesz dostosować wartości wcięcia lewego i prawego, wcięcia pierwszego wiersza, odstępu przed i odstępu po wartościach, aby kontrolować układ i wygląd akapitu.

#### P: Jak zmienić odstępy i wcięcia akapitu azjatyckiego za pomocą Aspose.Words dla .NET?

 O: Aby zmienić odstępy i wcięcia w akapicie azjatyckim, musisz uzyskać dostęp do pliku`ParagraphFormat`docelowego akapitu i zmodyfikuj jego odpowiednie właściwości. W podanym przykładowym kodzie uzyskujemy dostęp do pierwszego akapitu dokumentu i ustawiamy`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , I`LineUnitAfter` właściwości umożliwiające dostosowanie odstępów i wcięć.

#### P: Czy mogę zastosować te zmiany do innych akapitów dokumentu?

 O: Tak, możesz zastosować te zmiany do innych akapitów dokumentu, uzyskując dostęp do odpowiednich akapitów`ParagraphFormat` obiekty. Przykładowy kod dotyczy pierwszego akapitu dokumentu, ale możesz modyfikować inne akapity, dostosowując indeks w pliku`Paragraphs` gromadzenia lub korzystania z innych kryteriów w celu wybrania żądanych akapitów.