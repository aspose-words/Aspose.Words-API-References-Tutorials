---
title: Grupa podziału linii typografii azjatyckiej w dokumencie programu Word
linktitle: Grupa podziału linii typografii azjatyckiej w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać grupy podziału linii typografii azjatyckiej w dokumencie tekstowym za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-formatting/asian-typography-line-break-group/
---
W tym samouczku pokażemy, jak używać grupy podziału wierszy typografii azjatyckiej w funkcji dokumentu tekstowego w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany w formatowaniu.

## Krok 1: Ładowanie dokumentu

Aby rozpocząć, określ katalog dla swoich dokumentów i załaduj dokument zawierający typografię azjatycką do obiektu Dokument. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Krok 2: Konfiguracja typografii azjatyckiej

Skonfigurujemy teraz ustawienia typografii azjatyckiej dla pierwszego akapitu dokumentu. Oto jak:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Krok 3: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Przykładowy kod źródłowy grupy podziału linii typografii azjatyckiej przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji Asian Typography Line Break Group w Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Za pomocą tego kodu będziesz mógł zastosować grupę podziału linii azjatyckiej typografii przy użyciu Aspose.Words dla .NET.

## Wniosek

 W tym samouczku omówiliśmy funkcję „Grupa podziału linii typografii azjatyckiej” w Aspose.Words dla .NET. Konfigurując`FarEastLineBreakControl`, `WordWrap` , I`HangingPunctuation` właściwości`ParagraphFormat`, byliśmy w stanie kontrolować zachowanie łamania wierszy w typografii azjatyckiej w dokumencie programu Word. Ta funkcja jest przydatna do obsługi znaków azjatyckich oraz zapewniania prawidłowego łamania wierszy i zawijania słów w dokumentach o zawartości języków mieszanych.

### Często zadawane pytania

#### P: Jaka jest funkcja „Grupa podziału linii typografii azjatyckiej” w Aspose.Words dla .NET?

Odp.: Funkcja „Grupa łamania linii typografii azjatyckiej” w Aspose.Words dla .NET umożliwia kontrolowanie zachowania łamania linii dla typografii azjatyckiej w dokumencie programu Word. W szczególności wpływa na sposób łamania i zawijania linii w przypadku znaków azjatyckich w akapitach.

#### P: Jak włączyć „Grupę podziału linii typografii azjatyckiej” w Aspose.Words dla .NET?

 Odp.: Aby włączyć „Grupę podziału linii typografii azjatyckiej”, musisz skonfigurować`FarEastLineBreakControl`, `WordWrap` , I`HangingPunctuation` właściwości`ParagraphFormat` dla odpowiednich akapitów w dokumencie. Ustawienie`FarEastLineBreakControl` Do`false` zapewnia, że znaki azjatyckie są traktowane podobnie jak znaki łacińskie w zakresie łamania linii.`WordWrap` Ustawić`true` umożliwia zawijanie słów w typografii azjatyckiej oraz`HangingPunctuation` Ustawić`false` zapobiega zawieszaniu się znaków interpunkcyjnych w tekście azjatyckim.

#### P: Czy mogę zastosować „Grupę podziału linii typografii azjatyckiej” do określonych akapitów w dokumencie?

Odp.: Tak, możesz zastosować ustawienia „Grupy podziału wierszy typografii azjatyckiej” do określonych akapitów w dokumencie programu Word. W przykładowym kodzie ustawienia są stosowane do pierwszego akapitu dokumentu. W razie potrzeby możesz dostosować kod, aby kierować inne akapity, uzyskując do nich dostęp za pośrednictwem`Paragraphs` zebranie odpowiednich sekcji dokumentu.