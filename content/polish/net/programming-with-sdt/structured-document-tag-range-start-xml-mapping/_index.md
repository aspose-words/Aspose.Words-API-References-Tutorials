---
title: Zakres znaczników dokumentu strukturalnego Rozpocznij mapowanie Xml
linktitle: Zakres znaczników dokumentu strukturalnego Rozpocznij mapowanie Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak skonfigurować mapowanie XML dla zakresu znaczników dokumentu strukturalnego rozpoczynającego się w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

W tym samouczku wyjaśniono, jak skonfigurować mapowanie XML dla zakresu znaczników dokumentu strukturalnego rozpoczynającego się w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Mapowanie XML umożliwia wyświetlanie określonych części źródła danych XML w ramach kontroli zawartości.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i utwórz część XML
 Załaduj dokument Word za pomocą`Document`konstruktor, przekazując ścieżkę do dokumentu jako parametr. Utwórz część XML zawierającą dane, które chcesz wyświetlić w znaczniku dokumentu strukturalnego.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Krok 3: Ustaw mapowanie XML dla znacznika dokumentu strukturalnego
Pobierz początek zakresu znaczników dokumentu strukturalnego z dokumentu. Następnie ustaw mapowanie XML dla znacznika dokumentu strukturalnego tak, aby wyświetlała określoną część niestandardowej części XML przy użyciu wyrażenia XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Krok 4: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Przykładowy kod źródłowy zakresu znaczników dokumentu strukturalnego Rozpocznij mapowanie Xml przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Utwórz część XML zawierającą dane i dodaj ją do kolekcji CustomXmlPart dokumentu.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Utwórz StructuredDocumentTag, który wyświetli zawartość naszego CustomXmlPart w dokumencie.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Jeśli ustawimy mapowanie dla naszego StructuredDocumentTag,
	//wyświetli tylko część CustomXmlPart, na którą wskazuje XPath.
	// Ta ścieżka XPath będzie wskazywała zawartość drugiego elementu „<text>” pierwszego elementu „<root>” naszego CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Otóż to! Pomyślnie skonfigurowałeś mapowanie XML dla zakresu znaczników dokumentu strukturalnego rozpoczynającego się w dokumencie programu Word przy użyciu Aspose.Words dla .NET.