---
title: Pokaż błędy gramatyczne i ortograficzne
linktitle: Pokaż błędy gramatyczne i ortograficzne
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku umożliwiający wyświetlanie błędów gramatycznych i ortograficznych w dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby umożliwić wyświetlanie błędów gramatycznych i ortograficznych w Aspose.Words dla .NET. Ta funkcja umożliwia przeglądanie błędów gramatycznych i ortograficznych w dokumencie.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

tym kroku załadujemy dokument Word, dla którego chcemy wyświetlić błędy gramatyczne i ortograficzne. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Włącz wyświetlanie błędów

Teraz umożliwimy wyświetlanie błędów gramatycznych i ortograficznych w dokumencie. Użyj poniższego kodu, aby włączyć wyświetlanie błędów:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Kod ten umożliwia wyświetlanie błędów gramatycznych (`ShowGrammaticalErrors`) i błędy ortograficzne (`ShowSpellingErrors`) w dokumencie.

### Przykładowy kod źródłowy dla Pokaż błędy gramatyczne i ortograficzne przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak włączyć wyświetlanie błędów gramatycznych i ortograficznych w dokumencie przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo włączyć tę funkcję we własnych dokumentach.