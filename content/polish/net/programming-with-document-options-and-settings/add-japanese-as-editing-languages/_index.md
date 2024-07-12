---
title: Dodaj japoński jako języki edycji
linktitle: Dodaj japoński jako języki edycji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku, jak dodać język japoński jako język edycji za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

W tym samouczku przeprowadzimy Cię krok po kroku, aby zrozumieć i wdrożyć funkcjonalność dodawania języka japońskiego jako języka edycji za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia ustawienie preferencji językowych podczas ładowania dokumentu i dodanie języka japońskiego jako języka edycji.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Worda, który nie zawiera domyślnego języka edycji i do którego chcemy dodać język japoński. Aby załadować dokument, użyj poniższego kodu:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Ustaw preferencje językowe, które będą używane podczas ładowania dokumentu.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Krok 3: Sprawdzanie domyślnego języka

Po załadowaniu dokumentu sprawdzimy, czy domyślny język edycji został poprawnie ustawiony na język japoński. Użyj poniższego kodu, aby uzyskać identyfikator języka Dalekiego Wschodu:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Kod sprawdza, czy identyfikator języka Dalekiego Wschodu jest zgodny z identyfikatorem języka japońskiego. W zależności od wyniku wyświetla odpowiedni komunikat.

### Przykładowy kod źródłowy dla opcji Dodaj język japoński jako języki edycji przy użyciu Aspose.Words dla .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Ustaw preferencje językowe, które będą używane podczas ładowania dokumentu.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

