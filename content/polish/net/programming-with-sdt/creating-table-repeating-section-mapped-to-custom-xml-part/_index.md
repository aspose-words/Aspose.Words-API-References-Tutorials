---
title: Tworzenie sekcji powtarzanej tabeli odwzorowanej na niestandardową część Xml
linktitle: Tworzenie sekcji powtarzanej tabeli odwzorowanej na niestandardową część Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć tabelę z powtarzającą się sekcją odwzorowaną na CustomXmlPart w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

W tym samouczku pokazano, jak utworzyć tabelę z powtarzającą się sekcją odwzorowaną na niestandardową część Xml w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Sekcja powtarzania umożliwia dynamiczne dodawanie wierszy na podstawie danych XML przechowywanych w niestandardowej części Xml.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i narzędzie do tworzenia dokumentów
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` do zbudowania treści dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Dodaj niestandardowe dane XML do CustomXmlPart
 Stwórz`CustomXmlPart` i dodaj do niego niestandardowe dane XML. W tym przykładzie tworzymy ciąg XML reprezentujący zbiór książek wraz z ich tytułami i autorami.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Krok 4: Utwórz tabelę i strukturę tabeli
Rozpocznij tworzenie tabeli za pomocą`StartTable` metoda`DocumentBuilder` . Dodaj komórki tabeli i zawartość za pomocą`InsertCell`I`Write` metody.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Krok 5: Utwórz sekcję powtarzalną odwzorowaną na niestandardowy kod XML
 Stwórz`StructuredDocumentTag` z`SdtType.RepeatingSection` reprezentujący powtarzającą się sekcję. Ustaw mapowanie XML dla sekcji powtarzanej za pomocą`SetMapping` metoda`XmlMapping` nieruchomość. W tym przykładzie mapujemy sekcję powtarzaną na`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Krok 6: Utwórz element sekcji powtarzalnej i dodaj komórki
 Stwórz`StructuredDocumentTag` z`SdtType.RepeatingSectionItem` reprezentujący powtarzający się element sekcji. Dołącz go jako element podrzędny do sekcji powtarzanej.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Stwórz`Row` aby reprezentować każdy element sekcji powtarzanej i dołączać go do elementu sekcji powtarzanej.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Krok 7: Dodaj kontrolę treści w sekcji powtarzanej
 Tworzyć`StructuredDocumentTag` obiekty z`SdtType.PlainText`

  do reprezentowania kontroli treści tytułu i autora. Ustaw mapowanie XML dla każdej kontrolki zawartości za pomocą`SetMapping` metoda`XmlMapping` nieruchomość. W tym przykładzie mapujemy kontrolkę tytułu na`/books[1]/book[1]/title[1]` i kontrola autora do`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Krok 8: Zapisz dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save`metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Przykładowy kod źródłowy do tworzenia sekcji powtarzania tabeli odwzorowanej na niestandardową część Xml przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Otóż to! Pomyślnie utworzyłeś tabelę z powtarzającą się sekcją odwzorowaną na CustomXmlPart w dokumencie programu Word przy użyciu Aspose.Words dla .NET.