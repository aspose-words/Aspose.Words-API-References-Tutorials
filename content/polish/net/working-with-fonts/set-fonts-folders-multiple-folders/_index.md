---
title: Ustaw foldery czcionek w wielu folderach
linktitle: Ustaw foldery czcionek w wielu folderach
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania wielu folderów czcionek podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania wielu folderów czcionek podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak określić wiele folderów czcionek do użycia podczas renderowania dokumentów za pomocą Aspose.Words dla .NET.

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

## Krok 3: Ustaw foldery czcionek
 Teraz możesz ustawić wiele folderów czcionek za pomocą`FontSettings` klasa i`SetFontsFolders()` metoda. Możesz określić ścieżki do folderów czcionek, których chcesz używać w tablicy. W tym przykładzie określiliśmy dwa foldery czcionek: „C:\MyFonts\" i "D:\Różne\Fonts\„.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Krok 4: Zastosuj ustawienia czcionek
 Następnie musisz zastosować ustawienia czcionki do swojego dokumentu za pomocą`FontSettings` własność`Document` klasa.

```csharp
doc.FontSettings = fontSettings;
```

## Krok 5: Zapisz wyrenderowany dokument
 Na koniec możesz zapisać wyrenderowany dokument do pliku za pomocą`Save()` metoda`Document` klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Przykładowy kod źródłowy dla Ustawiaj foldery czcionek w wielu folderach przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Należy pamiętać, że to ustawienie zastąpi wszystkie domyślne źródła czcionek, które są domyślnie przeszukiwane. Teraz będą wyszukiwane tylko te foldery
// czcionki podczas renderowania lub osadzania czcionek. Aby dodać dodatkowe źródło czcionek, zachowując źródła czcionek systemowych, użyj zarówno FontSettings.GetFontSources, jak i
// Zamiast tego FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Wniosek
tym samouczku nauczyliśmy się, jak ustawić wiele folderów czcionek podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym szczegółowym przewodnikiem, możesz łatwo określić wiele folderów czcionek, które będą używane podczas renderowania dokumentów. Aspose.Words oferuje potężny i elastyczny interfejs API do przetwarzania tekstu z czcionkami w dokumentach. Dzięki tej wiedzy możesz kontrolować i dostosowywać źródła czcionek używanych podczas renderowania dokumentów do swoich konkretnych potrzeb.

### Często zadawane pytania

#### P: Jak mogę ustawić wiele folderów czcionek w Aspose.Words?

 Odp.: Aby ustawić wiele folderów czcionek w Aspose.Words, możesz użyć`SetFontsFolders` metoda`Fonts` klasa udostępniająca listę niestandardowych lokalizacji folderów czcionek.

#### P: Czy ustawienie wielu folderów czcionek wpływa na wszystkie dokumenty przetwarzane za pomocą Aspose.Words?

Odp.: Tak, ustawienie wielu folderów czcionek wpływa na wszystkie dokumenty przetwarzane za pomocą Aspose.Words. Po zdefiniowaniu folderów czcionek Aspose.Words użyje tych lokalizacji do wyszukiwania czcionek we wszystkich dokumentach.

#### P: Ile folderów czcionek mogę zdefiniować w Aspose.Words?

Odp.: Możesz zdefiniować dowolną liczbę folderów czcionek w Aspose.Words. Nie ma określonego limitu liczby folderów czcionek, które można zdefiniować.

#### P: Jak mogę sprawdzić foldery czcionek zdefiniowane w Aspose.Words?

 O: Aby sprawdzić foldery czcionek zdefiniowane w Aspose.Words, możesz użyć metody`GetFolders` metoda`Fonts` class, aby uzyskać lokalizacje skonfigurowanych folderów czcionek.

#### P: Czy foldery czcionek muszą zawierać określone czcionki?

Odp.: Tak, foldery czcionek powinny zawierać czcionki, których chcesz używać w dokumentach programu Word. Aspose.Words będzie wyszukiwał czcionki w określonych folderach podczas przetwarzania dokumentów.