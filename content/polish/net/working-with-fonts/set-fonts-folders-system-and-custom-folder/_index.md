---
title: Ustaw system folderów czcionek i folder niestandardowy
linktitle: Ustaw system folderów czcionek i folder niestandardowy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić systemowe i niestandardowe foldery czcionek w dokumentach programu Word przy użyciu Aspose.Words dla .NET, zapewniając prawidłowe wyświetlanie dokumentów w różnych środowiskach.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Wstęp

Wyobraź sobie, że tworzysz dokument z unikalnym stylem czcionki i okazuje się, że czcionki te nie wyświetlają się poprawnie na innym komputerze. Frustrujące, prawda? W tym miejscu wchodzi w grę konfigurowanie folderów czcionek. Dzięki Aspose.Words dla .NET możesz definiować systemowe i niestandardowe foldery czcionek, aby mieć pewność, że Twoje dokumenty zawsze wyglądają zgodnie z zamierzeniami. Przyjrzyjmy się, jak możesz to osiągnąć.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

-  Aspose.Words dla biblioteki .NET: Jeśli jeszcze tego nie zrobiłeś, pobierz ją[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: IDE takie jak Visual Studio.
- Podstawowa znajomość języka C#: Znajomość języka C# pomoże Ci postępować zgodnie z przykładami kodu.

## Importuj przestrzenie nazw

Najpierw zaimportuj niezbędne przestrzenie nazw do swojego projektu:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Teraz podzielmy proces na proste kroki.

## Krok 1: Załaduj dokument

 Aby rozpocząć, załaduj dokument programu Word do pliku Aspose.Words`Document` obiekt. Ten dokument będzie tym, w którym chcesz ustawić foldery czcionek.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 2: Zainicjuj ustawienia czcionek

 Utwórz nową instancję`FontSettings`. Obiekt ten pozwoli Ci zarządzać źródłami czcionek.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Krok 3: Pobierz źródła czcionek systemowych

Pobierz domyślne źródła czcionek systemowych. Na komputerze z systemem Windows zazwyczaj obejmuje to plik „Windows\Fonts\„katalog.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Krok 4: Dodaj niestandardowy folder czcionek

Dodaj niestandardowy folder zawierający dodatkowe czcionki. Jest to przydatne, jeśli w katalogu czcionek systemowych nie zainstalowano określonych czcionek.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Krok 5: Zaktualizuj źródła czcionek

 Przekonwertuj listę źródeł czcionek z powrotem na tablicę i ustaw ją na`FontSettings` obiekt.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Krok 6: Zastosuj ustawienia czcionki do dokumentu

 Na koniec zastosuj skonfigurowane`FontSettings` do dokumentu i zapisz go w wybranym formacie, np. PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Wniosek

masz to! Wykonując poniższe kroki, możesz mieć pewność, że w dokumentach programu Word używane są prawidłowe czcionki, niezależnie od tego, czy są to czcionki systemowe, czy niestandardowe, przechowywane w określonym katalogu. Ta konfiguracja pomaga zachować spójność wyglądu dokumentu w różnych środowiskach.

## Często zadawane pytania

### Co się stanie, jeśli brakuje czcionki zarówno w folderze systemowym, jak i niestandardowym?

Aspose.Words użyje domyślnej czcionki, aby zastąpić brakującą czcionkę, zapewniając czytelność dokumentu.

### Czy mogę dodać wiele niestandardowych folderów czcionek?

 Tak, możesz dodać wiele niestandardowych folderów czcionek, powtarzając proces tworzenia`FolderFontSource` obiektów i dodanie ich do listy źródeł czcionek.

### Czy można używać ścieżek sieciowych dla niestandardowych folderów czcionek?

 Tak, możesz określić ścieżkę sieciową w pliku`FolderFontSource` konstruktor.

### Jakie formaty plików obsługuje Aspose.Words do zapisywania dokumentów?

Aspose.Words obsługuje różne formaty, w tym DOCX, PDF, HTML i inne.

### Jak obsługiwać powiadomienia o zamianie czcionek?

 Powiadomienia o zamianie czcionek można obsługiwać za pomocą opcji`FontSettings` klasa`FontSubstitutionWarning`wydarzenie.