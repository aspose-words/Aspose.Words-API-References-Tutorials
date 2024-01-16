---
title: Usuń niestandardowe właściwości dokumentu
linktitle: Usuń niestandardowe właściwości dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący usuwania niestandardowych właściwości z dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/remove-custom-document-properties/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby usunąć niestandardowe właściwości z dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia usunięcie określonej niestandardowej właściwości z dokumentu.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

W tym kroku załadujemy dokument Word, z którego chcemy usunąć niestandardowe właściwości. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Usuwanie właściwości niestandardowych

Teraz usuńmy określoną właściwość niestandardową z dokumentu. Użyj następującego kodu:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Ten kod usuwa niestandardową właściwość „Data autoryzacji” z dokumentu. Możesz zastąpić „Datę autoryzacji” nazwą niestandardowej właściwości, którą chcesz usunąć.

### Przykładowy kod źródłowy do usuwania niestandardowych właściwości dokumentu przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak usuwać niestandardowe właściwości z dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo usunąć niestandardowe właściwości z własnych dokumentów.