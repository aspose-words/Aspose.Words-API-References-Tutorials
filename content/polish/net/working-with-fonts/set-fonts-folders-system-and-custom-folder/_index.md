---
title: Ustaw system folderów czcionek i folder niestandardowy
linktitle: Ustaw system folderów czcionek i folder niestandardowy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania systemowych i niestandardowych folderów czcionek podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania folderów czcionek systemowych i folderu niestandardowego podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak określić wiele folderów czcionek, w tym folder systemowy i folder niestandardowy, do użycia podczas renderowania dokumentów przy użyciu Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany, wyrenderowany dokument. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument do renderowania
 Następnie możesz załadować dokument do renderowania za pomocą`Document` klasa. Pamiętaj, aby określić poprawną ścieżkę dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Ustaw foldery systemowe i niestandardowe czcionek
 Teraz możesz ustawić foldery czcionek systemowych i folder niestandardowy za pomocą`FontSettings` klasa i`SetFontsSources()` metoda. Najpierw musisz pobrać listę używanych źródeł czcionek zależnych od środowiska`GetFontsSources()` i zapisz go na liście. Następnie możesz utworzyć nową instancję`FolderFontSource` określając ścieżkę do niestandardowego folderu zawierającego czcionki. Dodaj to wystąpienie do listy istniejących źródeł czcionek. Wreszcie użyj`SetFontsSources()` aby zaktualizować źródła czcionek o nową listę.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Krok 4: Zastosuj ustawienia czcionek
 Następnie musisz zastosować ustawienia czcionki do swojego dokumentu za pomocą`FontSettings` własność`Document` klasa.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Zapisz wyrenderowany dokument
Na koniec możesz zapisać wyrenderowany dokument do pliku

   używając`Save()` metoda`Document` klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Przykładowy kod źródłowy systemu ustawiania folderów czcionek i folderu niestandardowego przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Pobierz tablicę źródeł czcionek zależnych od środowiska, które są domyślnie przeszukiwane.
// Na przykład będzie to zawierać źródło „Windows\Fonts” na komputerach z systemem Windows.
// Dodajemy tę tablicę do nowej listy, aby znacznie ułatwić dodawanie lub usuwanie wpisów czcionek.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Dodaj nowe źródło folderu, które poinstruuje Aspose.Words, aby przeszukał następujący folder w poszukiwaniu czcionek.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//Dodaj niestandardowy folder zawierający nasze czcionki do listy istniejących źródeł czcionek.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić foldery czcionek systemowych i folder niestandardowy podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym szczegółowym przewodnikiem, możesz łatwo określić wiele folderów czcionek, w tym folder systemowy i folder niestandardowy, do użycia podczas renderowania dokumentów. Aspose.Words oferuje potężny i elastyczny interfejs API do przetwarzania tekstu z czcionkami w dokumentach. Dzięki tej wiedzy możesz kontrolować i dostosowywać źródła czcionek używanych podczas renderowania dokumentów do swoich konkretnych potrzeb.

### Często zadawane pytania

#### P: Jak mogę ustawić foldery czcionek systemowych w Aspose.Words?

O: Aby ustawić foldery czcionek systemowych w Aspose.Words, nie musisz nic robić. Aspose.Words automatycznie używa czcionek systemowych zainstalowanych w systemie operacyjnym.

#### P: Jak mogę ustawić niestandardowe foldery czcionek w Aspose.Words?

 Odp.: Aby ustawić niestandardowe foldery czcionek w Aspose.Words, możesz użyć`SetFontsFolders` metoda`Fonts` class określająca lokalizacje niestandardowych folderów czcionek.

#### P: Czy mogę określić wiele niestandardowych folderów czcionek w Aspose.Words?

 Odp.: Tak, możesz określić wiele niestandardowych folderów czcionek w Aspose.Words za pomocą`SetFontsFolders` metoda`Fonts` class z listą lokalizacji folderów.

#### P: Jak mogę sprawdzić foldery czcionek zdefiniowane w Aspose.Words?

 Aby sprawdzić foldery czcionek zdefiniowane w Aspose.Words, możesz użyć`GetFolders` metoda`Fonts` class, aby uzyskać listę skonfigurowanych folderów czcionek.

#### P: Czy niestandardowe czcionki folderów mają pierwszeństwo przed czcionkami systemowymi w Aspose.Words?

O: Tak, niestandardowe czcionki folderów mają pierwszeństwo przed czcionkami systemowymi w Aspose.Words. Jeśli czcionka jest obecna zarówno w folderach niestandardowych, jak i czcionkach systemowych, Aspose.Words użyje wersji z folderu niestandardowego.