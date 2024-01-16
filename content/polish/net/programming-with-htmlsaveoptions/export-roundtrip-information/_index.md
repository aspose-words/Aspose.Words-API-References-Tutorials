---
title: Eksportuj informacje o podróży w obie strony
linktitle: Eksportuj informacje o podróży w obie strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący eksportowania informacji w obie strony podczas zapisywania dokumentu w formacie HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyeksportować informacje w obie strony z dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia dołączenie informacji o podróży w obie strony do wyeksportowanego pliku HTML, co ułatwia odnalezienie zmian wprowadzonych w oryginalnym dokumencie.

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

Teraz skonfigurujemy opcje zapisywania HTML, aby wyeksportować informacje o dokumencie w obie strony. Użyj następującego kodu:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Ten kod tworzy instancję`HtmlSaveOptions` ustawia`ExportRoundtripInformation` opcja`true` aby uwzględnić informacje o podróży w obie strony podczas eksportowania.

## Krok 4: Konwertowanie i zapisywanie dokumentu do formatu HTML

Na koniec skonwertujemy dokument do formatu HTML, korzystając ze skonfigurowanych wcześniej opcji zapisywania HTML. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Ten kod konwertuje dokument do formatu HTML, łącznie z informacjami dotyczącymi podróży w obie strony, i zapisuje wyeksportowany plik HTML w określonym katalogu.

### Przykładowy kod źródłowy eksportu informacji o podróży w obie strony przy użyciu Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów w pliku`dataDir` zmienny.