---
title: Powiąż SDT z niestandardową częścią Xml
linktitle: Powiąż SDT z niestandardową częścią Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak powiązać SDT z niestandardową częścią Xml za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

W tym samouczku pokazano, jak powiązać znacznik dokumentu strukturalnego (SDT) z niestandardową częścią Xml za pomocą Aspose.Words dla .NET. Zestawy SDT umożliwiają dodawanie formantów zawartości strukturalnej do dokumentu programu Word, a komponenty CustomXmlParts umożliwiają przechowywanie niestandardowych danych XML skojarzonych z dokumentem.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość C# i XML.

## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i plik CustomXmlPart
 Utwórz nową instancję`Document` klasa i A`CustomXmlPart` do przechowywania niestandardowych danych XML. Niestandardowy kod XML powinien być w prawidłowym formacie XML. W tym przykładzie używamy prostego ciągu XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Krok 3: Dodaj StructuredDocumentTag (SDT) do dokumentu
 Dodać`StructuredDocumentTag`do dokumentu, aby służyć jako kontrola zawartości. Określić`SdtType` Jak`PlainText` i`MarkupLevel` Jak`Block` aby utworzyć SDT na poziomie bloku.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Krok 4: Ustaw mapowanie XML dla SDT
 Zamapuj SDT na`CustomXmlPart` za pomocą`SetMapping` metoda`XmlMapping` nieruchomość. Określić`CustomXmlPart` , wyrażenie XPath służące do zlokalizowania żądanego węzła XML i, jeśli to konieczne, przedrostek przestrzeni nazw. W tym przykładzie mapujemy SDT na`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Krok 5: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.BindSDTtoCustomXmlPart.doc”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Przykładowy kod źródłowy dla Bind Sd Tto Custom Xml Part przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Otóż to! Pomyślnie powiązałeś SDT z CustomXmlPart w dokumencie Word przy użyciu Aspose.Words dla .NET.