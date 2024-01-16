---
title: Uzyskaj listę dostępnych czcionek
linktitle: Uzyskaj listę dostępnych czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak uzyskać listę czcionek dostępnych w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/get-list-of-available-fonts/
---
tym samouczku wyjaśnimy, jak uzyskać listę czcionek dostępnych w Aspose.Words dla .NET. Lista dostępnych czcionek informuje, jakich czcionek można używać w dokumentach. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

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

## Krok 2: Skonfiguruj źródła czcionek
 Następnie utworzymy instancję`FontSettings` i pobierz istniejące źródła czcionek za pomocą`GetFontsSources()` metoda. Dodamy także nowe źródło czcionek poprzez określenie folderu zawierającego czcionki.

```csharp
// Skonfiguruj źródła czcionek
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Dodaj nowe źródło czcionki
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Krok 3: Uzyskaj listę dostępnych czcionek
 Teraz będziemy przeglądać dostępne czcionki za pomocą`GetAvailableFonts()` metodę na pierwszym zaktualizowanym źródle czcionek.

```csharp
// Uzyskaj listę dostępnych czcionek
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Przykładowy kod źródłowy funkcji Pobierz listę dostępnych czcionek przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Dodaj nowe źródło folderu, które poinstruuje Aspose.Words, aby przeszukał następujący folder w poszukiwaniu czcionek.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Dodaj niestandardowy folder zawierający nasze czcionki do listy istniejących źródeł czcionek.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Wniosek
tym samouczku widzieliśmy, jak uzyskać listę czcionek dostępnych w Aspose.Words dla .NET. Dzięki temu wiesz, jakich czcionek możesz używać w swoich dokumentach. Możesz skorzystać z tej funkcji, aby wybrać odpowiednie czcionki do swoich potrzeb.

### Często zadawane pytania

#### P: Jak mogę pobrać listę czcionek dostępnych w Aspose.Words?

 O: Aby pobrać listę czcionek dostępnych w Aspose.Words, możesz użyć metody`FontsProvider` klasa i`GetAvailableFonts` metoda. Ta metoda zwróci listę wszystkich czcionek zainstalowanych w systemie.

#### P: Czy mogę filtrować listę dostępnych czcionek według określonych kryteriów w Aspose.Words?

O: Tak, możesz filtrować listę czcionek dostępnych w Aspose.Words przy użyciu określonych kryteriów. Można na przykład filtrować czcionki według rodziny, stylu lub języka.

#### P: Jak mogę skorzystać z listy dostępnych czcionek w dokumentach programu Word?

 O: Aby skorzystać z listy czcionek dostępnych w dokumentach programu Word, możesz przeglądać listę i wybierać odpowiednie czcionki, korzystając z metod i właściwości`FontSettings` klasa w Aspose.Words.