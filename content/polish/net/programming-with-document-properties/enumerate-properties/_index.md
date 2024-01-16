---
title: Wylicz właściwości
linktitle: Wylicz właściwości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący wyliczania właściwości dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/enumerate-properties/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby wyliczyć właściwości dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia dostęp do wbudowanych i niestandardowych właściwości dokumentu.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, którego właściwości chcemy wyświetlić. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Wyliczanie właściwości

Wymieńmy teraz właściwości dokumentu, zarówno wbudowane, jak i niestandardowe. Użyj następującego kodu:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Ten kod wyświetla nazwę dokumentu, a następnie wyświetla listę wbudowanych i niestandardowych właściwości, wyświetlając ich nazwę i wartość.

### Przykładowy kod źródłowy wyliczenia właściwości przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak wyliczać właściwości dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo uzyskać dostęp do właściwości własnych dokumentów i przeglądać je.

