---
title: Ustaw foldery czcionek z priorytetem
linktitle: Ustaw foldery czcionek z priorytetem
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania folderów czcionek z priorytetem podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-with-priority/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania folderów czcionek z priorytetem podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak określić wiele folderów czcionek z niestandardowym priorytetem wyszukiwania podczas renderowania dokumentów przy użyciu Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany, wyrenderowany dokument. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Ustaw priorytet folderów czcionek
 Następnie możesz ustawić priorytet folderów czcionek za pomocą`FontSettings` klasa i`SetFontsSources()`metoda. Można określić wiele źródeł czcionek, korzystając z instancji`SystemFontSource`I`FolderFontSource`. W tym przykładzie zdefiniowaliśmy dwa źródła czcionek: domyślne źródło czcionek systemowych i niestandardowy folder czcionek z priorytetem 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Krok 3: Załaduj dokument do renderowania
 Teraz możesz załadować dokument do renderowania za pomocą`Document` klasa. Pamiętaj, aby określić poprawną ścieżkę dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Zapisz wyrenderowany dokument
 Na koniec możesz zapisać wyrenderowany dokument do pliku za pomocą`Save()` metoda`Document` klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Przykładowy kod źródłowy dla Ustawiaj foldery czcionek z priorytetem przy użyciu Aspose.Words dla .NET 
```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić foldery czcionek z priorytetem podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym szczegółowym przewodnikiem, możesz łatwo określić wiele folderów czcionek z niestandardowym priorytetem wyszukiwania podczas renderowania dokumentów. Aspose.Words oferuje potężny i elastyczny interfejs API do przetwarzania tekstu z czcionkami w dokumentach. Dzięki tej wiedzy możesz kontrolować i dostosowywać źródła czcionek używanych podczas renderowania dokumentów do swoich konkretnych potrzeb.

### Często zadawane pytania

#### P: Jak mogę ustawić foldery czcionek z priorytetem w Aspose.Words?

 Odp.: Aby ustawić priorytet folderów czcionek w Aspose.Words, możesz użyć opcji`SetFontsFoldersWithPriority` metoda`Fonts` class, określając lokalizację folderów czcionek i ich kolejność.

#### P: Co się stanie, jeśli czcionka znajduje się w kilku folderach o różnym priorytecie?

Odp.: Jeśli czcionka znajduje się w wielu folderach o różnym priorytecie, Aspose.Words podczas przetwarzania dokumentów użyje wersji z folderu o najwyższym priorytecie.

#### P: Czy mogę określić wiele folderów czcionek z tym samym priorytetem w Aspose.Words?

O: Tak, możesz określić wiele folderów czcionek z tym samym priorytetem w Aspose.Words. Aspose.Words uwzględni je wszystkie z równym priorytetem podczas wyszukiwania czcionek w dokumentach.

#### P: Jak mogę sprawdzić foldery czcionek zdefiniowane z priorytetem w Aspose.Words?

 O: Aby sprawdzić foldery czcionek zdefiniowane jako priorytetowe w Aspose.Words, możesz użyć metody`GetFolders` metoda`Fonts` class, aby uzyskać listę skonfigurowanych folderów czcionek, w tym ich kolejność.

#### P: Jaki jest pożytek z ustawienia priorytetu folderów czcionek w Aspose.Words?

Odp.: Ustawienie priorytetu folderów czcionek w Aspose.Words pozwala kontrolować kolejność wyszukiwania czcionek w dokumentach Word. Dzięki temu możesz mieć pewność, że użyte zostaną żądane czcionki, i uniknąć niepożądanych problemów z zastępowaniem czcionek.