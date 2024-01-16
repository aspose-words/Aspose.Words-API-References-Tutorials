---
title: Konfigurowanie łącza do treści
linktitle: Konfigurowanie łącza do treści
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konfigurowania linków do treści w dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/configuring-link-to-content/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby skonfigurować łącze do treści za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia utworzenie łącza do określonej treści w dokumencie.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Tworzenie dokumentu i konstruktora

W tym kroku utworzymy nowy dokument i zainicjujemy konstruktor. Użyj następującego kodu:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Utwórz zakładkę

Teraz utworzymy zakładkę w dokumencie. Użyj poniższego kodu, aby utworzyć zakładkę z tekstem w środku:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Ten kod tworzy zakładkę o nazwie „Moja zakładka” i dodaje do niej trochę tekstu.

## Krok 4: Konfigurowanie łącza do treści

Teraz skonfigurujemy link do treści korzystając z właściwości dokumentu. Użyj poniższego kodu, aby dodać i pobrać link do treści:

```csharp
// Uzyskaj listę wszystkich właściwości niestandardowych w dokumencie.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Dodaj właściwość związaną z treścią.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Ten kod dodaje właściwość związaną z treścią o nazwie „Zakładka” z zakładką „Moja zakładka”. Następnie pobiera informacje o właściwościach związanych z treścią, takie jak stan łącza, źródło łącza i wartość właściwości.

### Przykładowy kod źródłowy do konfigurowania łącza do treści przy użyciu Aspose.Words dla .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Pobierz z pliku listę wszystkich niestandardowych właściwości dokumentu.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Dodaj właściwość powiązaną z treścią.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Nauczyłeś się teraz, jak skonfigurować łącze do treści w dokumencie przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo tworzyć i konfigurować łącza do określonej treści we własnych dokumentach.