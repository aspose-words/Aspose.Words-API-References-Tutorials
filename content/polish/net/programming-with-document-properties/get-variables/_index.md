---
title: Pobierz zmienne
linktitle: Pobierz zmienne
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący pobierania zmiennych dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/get-variables/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby pobrać zmienne z dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia dostęp do zmiennych zdefiniowanych w dokumencie.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, z którego chcemy pobrać zmienne. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Pobieranie zmiennych

Teraz pobierzemy zmienne zdefiniowane w dokumencie. Użyj następującego kodu:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Ten kod wykonuje iterację po każdej parze klucz-wartość w zmiennych dokumentu i pobiera nazwę i wartość każdej zmiennej. Zmienne są następnie łączone w celu wyświetlenia informacji o każdej zmiennej.

### Przykładowy kod źródłowy funkcji Pobierz zmienne przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak pobierać zmienne z dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo uzyskać dostęp do zmiennych z własnych dokumentów i je przeglądać.