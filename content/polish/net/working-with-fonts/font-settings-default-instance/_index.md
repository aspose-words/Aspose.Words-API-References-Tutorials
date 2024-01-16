---
title: Domyślne wystąpienie ustawień czcionki
linktitle: Domyślne wystąpienie ustawień czcionki
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak skonfigurować domyślne ustawienia czcionek w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/font-settings-default-instance/
---

W tym samouczku przeprowadzimy Cię przez proces konfigurowania domyślnych ustawień czcionek w dokumencie programu Word przy użyciu biblioteki Aspose.Words dla platformy .NET. Domyślne ustawienia czcionek umożliwiają określenie źródeł czcionek używanych podczas ładowania i renderowania dokumentów. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

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

## Krok 2: Skonfiguruj domyślne ustawienia czcionek
 Następnie utworzymy instancję`FontSettings` za pomocą`FontSettings.DefaultInstance`, a następnie określimy źródła czcionek używanych podczas ładowania i renderowania dokumentów. W tym przykładzie używamy źródła czcionek systemowych i źródła czcionek folderowych.

```csharp
// Skonfiguruj domyślne ustawienia czcionek
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Krok 3: Prześlij dokument z ustawieniami czcionek
 Teraz załadujemy dokument za pomocą`LoadOptions` i określenie ustawień czcionki, która ma być używana.

```csharp
// Załaduj dokument z ustawieniami czcionki
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Przykładowy kod źródłowy dla domyślnej instancji ustawień czcionek przy użyciu Aspose.Words dla .NET 
```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Wniosek
W tym samouczku widzieliśmy, jak skonfigurować domyślne ustawienia czcionek w dokumencie programu Word za pomocą Aspose.Words dla .NET. Określając źródła czcionek używanych podczas ładowania i renderowania dokumentów, możesz kontrolować wygląd czcionek w dokumentach. Możesz skorzystać z tej funkcji, aby dostosować ustawienia czcionek w swoich projektach.

### Często zadawane pytania

#### P: Jak mogę ustawić domyślną czcionkę w Aspose.Words?

 Odp.: Aby ustawić domyślną czcionkę w Aspose.Words, możesz użyć`FontSettings` klasa i`DefaultFontName` właściwość określająca nazwę żądanej czcionki.

#### P: Czy mogę określić domyślny rozmiar czcionki w Aspose.Words?

 O: Tak, możesz określić domyślny rozmiar czcionki w Aspose.Words za pomocą`DefaultFontSize` własność`FontSettings` klasa. Można ustawić żądany rozmiar punktu.

#### P: Czy można ustawić domyślny kolor czcionki w Aspose.Words?

 O: Tak, możesz ustawić domyślny kolor czcionki w Aspose.Words za pomocą`DefaultColor` własność`FontSettings` klasa. Kolor można określić za pomocą wartości RGB lub predefiniowanych nazw.

#### P: Czy domyślne ustawienia czcionek mają zastosowanie do wszystkich dokumentów?

Odp.: Tak, domyślne ustawienia czcionek mają zastosowanie do wszystkich dokumentów utworzonych lub edytowanych w Aspose.Words, chyba że dla konkretnego dokumentu określono określone ustawienia.