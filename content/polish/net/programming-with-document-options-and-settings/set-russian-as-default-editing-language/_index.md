---
title: Ustaw rosyjski jako domyślny język edycji
linktitle: Ustaw rosyjski jako domyślny język edycji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku, jak ustawić rosyjski jako domyślny język edycji dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby ustawić rosyjski jako domyślny język edycji w Aspose.Words dla .NET. Ta funkcja umożliwia ustawienie domyślnego języka podczas ładowania dokumentu.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, dla którego chcemy ustawić rosyjski jako domyślny język edycji. Aby załadować dokument, użyj poniższego kodu:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Sprawdzanie domyślnego języka

Po przesłaniu dokumentu sprawdzimy, czy domyślny język został poprawnie ustawiony na rosyjski. Użyj poniższego kodu, aby uzyskać domyślny identyfikator języka:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Kod sprawdza, czy identyfikator języka jest zgodny z identyfikatorem języka rosyjskiego. W zależności od wyniku wyświetla odpowiedni komunikat.

### Przykładowy kod źródłowy dla Ustaw rosyjski jako domyślny język edycji przy użyciu Aspose.Words dla .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak ustawić rosyjski jako domyślny język edycji dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie z instrukcją krokową