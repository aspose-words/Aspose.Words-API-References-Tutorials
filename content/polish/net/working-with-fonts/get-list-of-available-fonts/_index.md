---
title: Uzyskaj listę dostępnych czcionek
linktitle: Uzyskaj listę dostępnych czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać listę dostępnych czcionek za pomocą Aspose.Words dla .NET w tym szczegółowym samouczku krok po kroku. Zwiększ swoje umiejętności zarządzania czcionkami.
type: docs
weight: 10
url: /pl/net/working-with-fonts/get-list-of-available-fonts/
---
## Wstęp

Czy kiedykolwiek miałeś trudności z zarządzaniem czcionkami w dokumentach programu Word? Jeśli jesteś programistą .NET, Aspose.Words dla .NET jest tutaj, aby Cię uratować! Ta potężna biblioteka nie tylko pomaga programowo tworzyć dokumenty programu Word i manipulować nimi, ale także oferuje rozbudowane możliwości zarządzania czcionkami. W tym przewodniku przeprowadzimy Cię przez samouczek krok po kroku, jak uzyskać listę dostępnych czcionek za pomocą Aspose.Words dla .NET. Podzielimy go na zrozumiałe etapy, dzięki którym będziesz mógł z łatwością je śledzić. Przejdźmy więc do rzeczy i sprawmy, aby zarządzanie czcionkami było proste!

## Warunki wstępne

Zanim zaczniemy, potrzebujesz kilku rzeczy:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/words/net/).
- Visual Studio: w tym przykładzie zastosowano Visual Studio jako środowisko programistyczne.
- .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.
- Katalog dokumentów: Ścieżka katalogu, w którym przechowywane są dokumenty.

## Importuj przestrzenie nazw

Najpierw zaimportuj niezbędne przestrzenie nazw do swojego projektu:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Krok 1: Zainicjuj ustawienia czcionek

Pierwszym krokiem jest zainicjowanie ustawień czcionki. Umożliwi to zarządzanie źródłami czcionek w dokumentach.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: Ta klasa służy do określania ustawień podstawiania czcionek i źródeł czcionek.
- FontSources: Tworzymy listę istniejących źródeł czcionek na podstawie bieżących ustawień czcionek.

## Krok 2: Zdefiniuj katalog dokumentów

Następnie określ ścieżkę do katalogu dokumentów. Tutaj Aspose.Words będzie szukać czcionek.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Ta zmienna łańcuchowa przechowuje ścieżkę do katalogu, w którym znajdują się czcionki. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką.

## Krok 3: Dodaj niestandardowy folder czcionek

Teraz dodaj nowe źródło folderu, aby poinstruować Aspose.Words, aby przeszukał ten folder w poszukiwaniu czcionek.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: Ta klasa reprezentuje źródło czcionek folderowych. Drugi parametr (`true`) wskazuje, czy rekurencyjnie wyszukiwać czcionki w podfolderach.

## Krok 4: Zaktualizuj źródła czcionek

Dodaj folder niestandardowych czcionek do listy istniejących źródeł czcionek i zaktualizuj ustawienia czcionek.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- FontSources.Add(folderFontSource): Dodaje niestandardowy folder czcionek do istniejących źródeł czcionek.
- zaktualizowanyFontSources: Konwertuje listę źródeł czcionek na tablicę.

## Krok 5: Pobierz i wyświetl czcionki

Na koniec pobierz dostępne czcionki i wyświetl ich szczegóły.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): pobiera listę dostępnych czcionek z pierwszego źródła czcionek na zaktualizowanej liście.
-  FontInfo: Instancja`PhysicalFontInfo` zawierający szczegółowe informacje na temat każdej czcionki.

## Wniosek

Gratulacje! Pomyślnie pobrałeś listę dostępnych czcionek przy użyciu Aspose.Words dla .NET. Ten samouczek przeprowadził Cię przez każdy krok, od inicjowania ustawień czcionek po wyświetlenie szczegółów czcionek. Dzięki tej wiedzy możesz teraz z łatwością zarządzać czcionkami w dokumentach programu Word. Pamiętaj, Aspose.Words dla .NET to potężne narzędzie, które może znacznie zwiększyć możliwości przetwarzania dokumentów. Zatem śmiało poznaj więcej funkcji, dzięki którym proces programowania będzie jeszcze wydajniejszy.

## Często zadawane pytania

### Czy mogę używać Aspose.Words dla .NET z innymi frameworkami .NET?
Tak, Aspose.Words dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET 5+.

### Jak zainstalować Aspose.Words dla .NET?
Można go zainstalować za pomocą Menedżera pakietów NuGet w programie Visual Studio, wyszukując „Aspose.Words”.

### Czy można dodać wiele niestandardowych folderów czcionek?
 Tak, możesz dodać wiele niestandardowych folderów czcionek, tworząc ich wiele`FolderFontSource` wystąpienia i dodanie ich do listy źródeł czcionek.

### Czy mogę pobrać szczegóły czcionki z określonego źródła czcionek?
 Tak, możesz pobrać szczegóły czcionki z dowolnego źródła czcionek, określając indeks źródła czcionki w pliku`updatedFontSources` szyk.

### Czy Aspose.Words dla .NET obsługuje podstawianie czcionek?
Tak, obsługuje podstawianie czcionek, aby zapewnić prawidłowe renderowanie tekstu, nawet jeśli oryginalna czcionka nie jest dostępna.