---
title: Eksportuj pole formularza wprowadzania tekstu jako tekst
linktitle: Eksportuj pole formularza wprowadzania tekstu jako tekst
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania pól formularzy wprowadzania tekstu jako zwykłego tekstu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyeksportować pola formularzy wprowadzania tekstu jako zwykły tekst za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia eksportowanie pól formularzy wprowadzania tekstu jako czytelnego tekstu zamiast eksportowania ich jako elementów wejściowych HTML.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument do eksportu. Użyj poniższego kodu, aby załadować dokument z określonego katalogu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ten kod tworzy instancję`Document` poprzez załadowanie dokumentu z określonego katalogu.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych HTML

Teraz skonfigurujemy opcje zapisywania HTML, aby eksportować pola formularzy wprowadzania tekstu jako zwykły tekst. Użyj następującego kodu:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Określony folder musi istnieć i być pusty.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Ten kod tworzy instancję`HtmlSaveOptions` i ustawia`ExportTextInputFormFieldAsText` opcja`true` aby wyeksportować pola formularza wprowadzania tekstu jako zwykły tekst. Ponadto określa folder, w którym zostaną zapisane wyodrębnione obrazy.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML, eksportując pola formularza wprowadzania tekstu jako zwykły tekst i zapisując wyeksportowany plik HTML w określonym katalogu.

### Przykładowy kod źródłowy eksportu pola formularza wprowadzania tekstu jako tekstu przy użyciu Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Określony folder musi istnieć i powinien być pusty.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Ustaw opcję eksportowania pól formularza jako zwykły tekst, a nie jako elementy wejściowe HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.