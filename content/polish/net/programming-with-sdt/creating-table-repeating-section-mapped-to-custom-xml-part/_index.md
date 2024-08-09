---
title: Tworzenie sekcji powtarzanej tabeli odwzorowanej na niestandardową część Xml
linktitle: Tworzenie sekcji powtarzanej tabeli odwzorowanej na niestandardową część Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć tabelę z powtarzającą się sekcją odwzorowaną na CustomXmlPart w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Wstęp

W tym samouczku omówimy proces tworzenia tabeli z powtarzającą się sekcją, która jest mapowana na niestandardową część XML za pomocą Aspose.Words dla .NET. Jest to szczególnie przydatne przy dynamicznym generowaniu dokumentów w oparciu o ustrukturyzowane dane.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Zainstalowana biblioteka Aspose.Words dla .NET. Można go pobrać z[Strona Aspose](https://releases.aspose.com/words/net/).
2. Podstawowa znajomość C# i XML.

## Importuj przestrzenie nazw

Pamiętaj o uwzględnieniu w projekcie niezbędnych przestrzeni nazw:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Krok 1: Zainicjuj dokument i narzędzie DocumentBuider

 Najpierw utwórz nowy dokument i zainicjuj plik`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Dodaj niestandardową część XML

Dodaj niestandardową część XML do dokumentu. Ten plik XML zawiera dane, które chcemy zmapować do naszej tabeli:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Krok 3: Utwórz strukturę tabeli

 Następnie użyj`DocumentBuilder` aby utworzyć nagłówek tabeli:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Krok 4: Utwórz sekcję powtarzalną

 Utwórz`StructuredDocumentTag` (SDT) dla sekcji powtarzalnej i zmapuj ją na dane XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Krok 5: Utwórz element sekcji powtarzalnej

Utwórz SDT dla elementu sekcji powtarzanej i dodaj go do sekcji powtarzanej:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Krok 6: Mapuj dane XML na komórki tabeli

Utwórz SDT dla tytułu i autora, zmapuj je do danych XML i dołącz je do wiersza:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Krok 7: Zapisz dokument

Na koniec zapisz dokument we wskazanym katalogu:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Wniosek

Wykonując te kroki, pomyślnie utworzyłeś tabelę z powtarzającą się sekcją odwzorowaną na niestandardową część XML przy użyciu Aspose.Words dla .NET. Pozwala to na dynamiczne generowanie treści w oparciu o dane strukturalne, dzięki czemu tworzenie dokumentów jest bardziej elastyczne i wydajne.

## Często zadawane pytania

### Co to jest tag dokumentu strukturalnego (SDT)?
SDT, znany również jako kontrola treści, to ograniczony region w dokumencie używany do przechowywania danych strukturalnych.

### Czy mogę używać innych typów danych w niestandardowej części XML?
Tak, możesz ustrukturyzować swoją niestandardową część XML za pomocą dowolnych typów danych i odpowiednio je zmapować.

### Jak dodać więcej wierszy do sekcji powtarzanej?
Sekcja powtarzana automatycznie replikuje strukturę wierszy dla każdego elementu w mapowanej ścieżce XML.