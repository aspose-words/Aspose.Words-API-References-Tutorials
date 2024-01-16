---
title: Uzyskaj podstawienie bez przyrostków
linktitle: Uzyskaj podstawienie bez przyrostków
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak uzyskać zastąpienia bez sufiksów w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/get-substitution-without-suffixes/
---

W tym samouczku pokażemy, jak uzyskać zastąpienia bez przyrostków w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla .NET. Zastąpienia bez przyrostków służą do rozwiązywania problemów z zastępowaniem czcionek podczas wyświetlania lub drukowania dokumentów. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie

## Krok 1: Zdefiniuj katalog dokumentów
 Najpierw musisz ustawić ścieżkę katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument i skonfiguruj podstawienia bez przyrostków
 Następnie załadujemy dokument za pomocą metody`Document` class i skonfiguruj podstawienia bez sufiksów za pomocą`DocumentSubstitutionWarnings` klasa. Dodamy także źródło czcionek, określając folder zawierający czcionki.

```csharp
// Załaduj dokument i skonfiguruj podstawienia bez przyrostków
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Krok 3: Zapisz dokument
Na koniec zapiszemy dokument z zastosowanymi zastąpieniami bez przyrostka.

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Przykładowy kod źródłowy funkcji Uzyskaj podstawienie bez przyrostków przy użyciu Aspose.Words dla .NET 
```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Wniosek
W tym samouczku widzieliśmy, jak uzyskać zastąpienia bez przyrostków w dokumencie programu Word za pomocą Aspose.Words dla .NET. Podstawienia bez przyrostków są przydatne przy rozwiązywaniu problemów z zastępowaniem czcionek. Możesz skorzystać z tej funkcji, aby ulepszyć wyświetlanie i drukowanie dokumentów.

### Często zadawane pytania

#### P: Dlaczego Aspose.Words dodaje przyrostki do podstawień czcionek?

Odp.: Aspose.Words dodaje przyrostki do zastępowań czcionek, aby uniknąć konfliktów między czcionkami oryginalnymi i czcionkami podstawionymi. Pomaga to zapewnić maksymalną kompatybilność podczas konwertowania dokumentów i manipulowania nimi.

#### P: Jak mogę pobrać podstawienia czcionek bez przyrostków w Aspose.Words?

 O: Aby pobrać podstawienia czcionek bez przyrostków w Aspose.Words, możesz użyć metody`FontSubstitutionSettings` klasa i`RemoveSuffixes` nieruchomość. Ustawienie tej właściwości na`true` otrzyma podstawienia czcionek bez dodanych przyrostków.

#### P: Czy można wyłączyć dodawanie przyrostków do podstawień czcionek w Aspose.Words?

O: Nie, nie można wyłączyć dodawania przyrostków do podstawień czcionek w Aspose.Words. Przyrostki są dodawane domyślnie, aby zapewnić zgodność i spójność dokumentu.

#### P: Jak mogę odfiltrować niechciane przyrostki w podstawieniach czcionek w Aspose.Words?

 O: Aby odfiltrować niechciane sufiksy w podstawieniach czcionek w Aspose.Words, możesz użyć technik przetwarzania ciągów, takich jak użycie`Replace` Lub`Substring` metody usuwania określonych przyrostków, których nie chcesz dołączać.