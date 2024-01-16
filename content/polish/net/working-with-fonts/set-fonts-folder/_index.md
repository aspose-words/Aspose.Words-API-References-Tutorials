---
title: Ustaw folder czcionek
linktitle: Ustaw folder czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić katalog czcionek w Aspose.Words dla .NET i zapewnić dostępność czcionek używanych w dokumentach.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folder/
---
W tym samouczku pokażemy, jak ustawić katalog czcionek w Aspose.Words dla .NET. Dowiesz się, jak określić katalog zawierający czcionki używane w dokumencie programu Word.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie

## Krok 1: Zdefiniuj katalog dokumentów
 Zacznij od ustawienia ścieżki katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Ustaw katalog czcionek
 Utwórz instancję`FontSettings` klasę i użyj`SetFontsFolder` metoda określenia katalogu zawierającego czcionki. Zastępować`"Fonts"` z nazwą aktualnego katalogu czcionek.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Krok 3: Załaduj dokument z ustawieniami czcionek
 Użyj`LoadOptions` class, aby określić ustawienia czcionki w pliku`FontSettings` opcja. Następnie użyj`Document` class, aby załadować dokument przy użyciu tych opcji.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Przykładowy kod źródłowy dla folderu Ustaw czcionki przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Wniosek
Gratulacje! Teraz wiesz, jak ustawić katalog czcionek w Aspose.Words dla .NET. Możesz użyć tej funkcji, aby zapewnić dostępność czcionek używanych w dokumencie i spójność wyświetlania czcionek.

### Często zadawane pytania

#### P: Jak mogę ustawić niestandardowy folder czcionek w Aspose.Words?

 Odp.: Aby ustawić niestandardowy folder czcionek w Aspose.Words, możesz użyć`FontsFolder` klasa i`SetFontsFolders` metoda określająca ścieżkę do folderu zawierającego czcionki.

#### P: Czy mogę ustawić wiele folderów czcionek w Aspose.Words?

 O: Tak, możesz ustawić wiele folderów czcionek w Aspose.Words, wywołując metodę`SetFontsFolders` metodę wielokrotnie ze ścieżkami różnych folderów czcionek, których chcesz użyć.

#### P: Co się stanie, jeśli czcionka użyta w dokumencie nie będzie znajdować się w zdefiniowanych folderach czcionek?

Odp.: Jeśli czcionka użyta w dokumencie nie występuje w folderach czcionek zdefiniowanych w Aspose.Words, zamiast niej zostanie użyta czcionka zastępcza. Dzięki temu tekst w dokumencie będzie zawsze wyświetlany poprawnie, nawet jeśli oryginalna czcionka nie jest dostępna.

#### P: Czy foldery czcionek zdefiniowane w Aspose.Words mają pierwszeństwo przed czcionkami zainstalowanymi w systemie?

O: Tak, foldery czcionek zdefiniowane w Aspose.Words mają pierwszeństwo przed czcionkami zainstalowanymi w systemie. Oznacza to, że jeśli czcionka o tej samej nazwie występuje zarówno w zdefiniowanych folderach czcionek, jak i czcionkach systemowych, przy przetwarzaniu dokumentów Worda używana będzie wersja z folderu czcionek.