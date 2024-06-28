---
title: Ustaw domyślną instancję folderów czcionek
linktitle: Ustaw domyślną instancję folderów czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania domyślnego folderu czcionek podczas renderowania dokumentu przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-fonts-folders-default-instance/
---

W tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania domyślnego folderu czcionek podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak ustawić domyślny folder czcionek, który będzie używany podczas renderowania dokumentów przy użyciu Aspose.Words dla .NET.

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany, wyrenderowany dokument. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Ustaw domyślny folder czcionek
 Następnie możesz ustawić domyślny folder czcionek za pomocą`FontSettings.DefaultInstance` klasa i`SetFontsFolder()`metoda. Określ ścieżkę do folderu czcionek, którego chcesz używać jako folderu domyślnego.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Krok 3: Załaduj dokument do renderowania
 Teraz możesz załadować dokument do renderowania za pomocą`Document` klasa. Pamiętaj, aby określić poprawną ścieżkę dokumentu.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 4: Zapisz wyrenderowany dokument
 Na koniec możesz zapisać wyrenderowany dokument do pliku za pomocą`Save()` metoda`Document` klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Przykładowy kod źródłowy dla domyślnej instancji Ustaw foldery czcionek przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić domyślny folder czcionek podczas renderowania dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo określić, który folder czcionek ma być używany jako folder domyślny podczas renderowania dokumentów. Aspose.Words oferuje potężny i elastyczny interfejs API do przetwarzania tekstu z czcionkami w dokumentach. Dzięki tej wiedzy możesz kontrolować i dostosowywać źródła czcionek używanych podczas renderowania dokumentów do swoich konkretnych potrzeb.

### Często zadawane pytania

#### P: Jak mogę ustawić domyślne foldery czcionek w Aspose.Words?

 Odp.: Aby ustawić domyślne foldery czcionek w Aspose.Words, musisz użyć`Fonts` klasa i`SetFontsFolders` metoda określania niestandardowych lokalizacji folderów czcionek.

#### P: Czy ustawienie domyślnych folderów czcionek wpływa na wszystkie dokumenty programu Word przetwarzane za pomocą Aspose.Words?

O: Tak, ustawienie domyślnych folderów czcionek wpływa na wszystkie dokumenty programu Word przetwarzane za pomocą Aspose.Words. Po ustawieniu domyślnych folderów czcionek Aspose.Words użyje tych lokalizacji do wyszukiwania czcionek we wszystkich dokumentach.

#### P: Czy mogę ustawić wiele domyślnych folderów czcionek w Aspose.Words?

 O: Tak, możesz ustawić wiele domyślnych folderów czcionek w Aspose.Words. Wystarczy określić lokalizacje niestandardowych folderów czcionek za pomocą`SetFontsFolders` metoda`Fonts` klasa.

#### P: Jak mogę sprawdzić domyślne foldery czcionek aktualnie ustawione w Aspose.Words?

 O: Aby sprawdzić domyślne foldery czcionek aktualnie zdefiniowane w Aspose.Words, możesz użyć metody`GetFolders` metoda`Fonts` class, aby uzyskać lokalizacje skonfigurowanych folderów czcionek.

#### P: Czy ustawienie domyślnych folderów czcionek pozwala mi używać niestandardowych czcionek w dokumentach programu Word?

Odp.: Tak, ustawiając domyślne foldery czcionek, możesz używać niestandardowych czcionek w dokumentach programu Word. Wystarczy umieścić czcionki w określonych folderach, a Aspose.Words użyje ich podczas generowania dokumentów lub manipulowania nimi.